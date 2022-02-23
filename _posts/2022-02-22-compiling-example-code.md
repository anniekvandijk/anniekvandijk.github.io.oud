---
title: How to embed small compiling .NET code examples in your blog
date: 2022-02-23 08:00:00 +0100
categories: [Blog, Styling]
tags: [.NET Fiddle, compiling, C#, .NET, dotnetfiddle.net, embedding code]
---

All you need is a **.NET Fiddle account** and a saved Fiddle. A Fiddle is like a Github Gist, but only for .NET code. 

There are more tools online that can compile code. I chose .NET Fiddle, because it has nice code completion, Code Highlighting and can be embedded.

![markdown](/assets/img/blog-images/2022-02-22/Fiddle.png)

## How is this different from embedding a Github Gists?

It is not very different. But, it will only show a nice block of code, which does not compile. 

<script src="https://gist.github.com/anniekvandijk/53bed85ec375805cbf4727285635528a.js"></script>

Microsoft is developing a tool (Try .NET) that can run Gists in the browser. But it is not released to the public (yet). See [**Try .NET**](https://dotnet.microsoft.com/en-us/platform/try-dotnet).

## Embed the Fiddle

In the .NET Fiddle menu you press the 'Share Button' and copy the 'Embed on Your Page code'. 
![markdown](/assets/img/blog-images/2022-02-22/FiddleShare.png)

Then you paste the code block in your editor. It looks like this:  
```HTML
<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/pCv8Ik" frameborder="0"></iframe>
```
And now you have a running code block on your site :sunglasses:

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/pCv8Ik" frameborder="0"></iframe>
