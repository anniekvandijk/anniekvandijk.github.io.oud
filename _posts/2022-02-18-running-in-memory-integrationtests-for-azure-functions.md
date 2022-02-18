---
title: Running in-memory Integrations Tests for Azure Function on Github
date: 2022-02-18 10:00:00 +0100
categories: [Azure Functions, Test Automation]
tags: [github, in-memory, github actions, integration tests]
---

This post is about running Integration Tests for an Azure Function with http endpoint on Github. Making use of in-memory running the function and testing with Github Actions.

Software development teams know: Integration Testing is hard! They are slow and have dependencies which make it difficult to run. But, This is not always true!

## What are we testing?

I am developping an Azure Fuction with one HTTP endpoint (POST, form data) which returns a json. I use the Github actions to test and deploy it to Azure. 

This is my endpoint:

```C#
[Function("plantcheck")]
public async Task<HttpResponseData> Run(
    [HttpTrigger(AuthorizationLevel.Function, "post", Route = "v1/plantcheck")] HttpRequestData request,
    FunctionContext executionContext)
{
    await _handleRequest.CollectData(request.Body);
    var result = _matchData.MatchToxicPlantsForAnimals();
    return await _handleResponse.SetResponse(request, result);
}
```        

I am working in Visual Studio. When you run the Azure Function Locally (Without debug) you see it running on `localhost:7071/api/v1/plantcheck`

![markdown](/assets/img/blog-images/2022-02-18/RunWithoutDebug.png)

![markdown](/assets/img/blog-images/2022-02-18/FunctionLocalRun.png)

If you post a request with Postman. You get a **200 OK** response with a response body.

![markdown](/assets/img/blog-images/2022-02-18/Postman.png)

Ok, so this all looks great, let's automate the request and response. 

> I do notice that the response body is not as expected. Direct proof that only running Unit Test is not enough. This you only see of you hit the endpoint.

## Creating first automated Integration Test

For the Integration Tests, I make a seperate project and call it `Function.IT`. In my case, it is a .NET5 NUnit Testproject. 

![markdown](/assets/img/blog-images/2022-02-18/SolutionScreen.png)

> I think I should rename `Function.Tests` to `Function.UT`. Because that project is not containing all tests anymore ... maybe I do rename it later :smile: 

For now, the project has one class file `IntegrationTests`. I did make the example class a bit more compact than the real one.  

```c#
public class IntegrationTests
{
    private static HttpClient _http;
    private const string Url = "http://localhost:7071/api/v1/plantcheck";

    [SetUp]
    public void Setup()
    {
        _http = new HttpClient();
    }
    
    [TearDown]
    public void Cleanup()
    {
        _http.Dispose();
    }

    [Test]
    public async Task PlantcheckApi_ValidRequest_Returns200()
    {

        var request = new HttpRequestMessage
        {
            RequestUri = new Uri(Url),
            Method = HttpMethod.Post,
            Content = <somecontent>
        };

        var response = await _http.SendAsync(request);
        var statusCode = (int)response.StatusCode;
        Assert.AreEqual(200, statusCode);
    }
}
```

The important parts are:
- a Setup for a new httpClient
- a tearDown to dispose the client
- a Test which posts something to the endpoint `http://localhost:7071/api/v1/plantcheck` that should return a http response code 200. 

When you run this test, it should return the same result as the test run in Postman.

![markdown](/assets/img/blog-images/2022-02-18/TestExplorer.png)

If all is green we go to the next step. 

## Adding the Integration Test to the Github Actions workflow

I already have a Test workflow in Github Actions. For the Integration Tests I added the last 3 steps. 
1. Setup Azure Functions Core Tools, with a shell script to install Azure Functions Core Tools to run the Azure Function.
2. Start function, with a shell script to run the Azure Function.
3. Integration test, To run the Integration Tests.

```yml
name: Test

on:
  push:
    branches:
        - main
        - develop

jobs:
  test:
    name: Test
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout
        uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis
      - name: Setup .NET
        uses: actions/setup-dotnet@v1
        with:
          dotnet-version: 5.0.x
      - name: Dotnet Restore
        run: dotnet restore
      - name: Dotnet clean
        run: dotnet clean --configuration Debug
      - name: Dotnet Build
        run: dotnet build 
            --no-restore 
            --configuration Debug
      - name: Dotnet Unit test
        run: dotnet test 
            Function.Test/Function.Tests.csproj 
            --no-build 
            --no-restore 
            --verbosity normal
            --configuration Debug
      - name: Setup Azure Functions Core Tools
        shell: pwsh
        run: npm install -g azure-functions-core-tools@3 --unsafe-perm true
      - name: Start function
        shell: pwsh
        run: |
            dir
            $rootDir = $pwd.Path
            cd ./Function
            Start-Process -NoNewWindow func @("start","--verbose","false")
            Start-Sleep -s 60
            cd ..
      - name: Integration test
        run: dotnet test 
            Function.IT/Function.IT.csproj 
            --no-build
            --no-restore 
            --verbosity normal
            --configuration Debug
```

After all Tests are passed the next workflow will start deploying the Function on Azure. 

I hope this example will help with your tests! If you have any questions, please contact me or post a reaction to this post.  