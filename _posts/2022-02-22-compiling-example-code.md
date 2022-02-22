---
title: How to have small c# code examples in blog that compile
date: 2022-02-22 10:00:00 +0100
categories: [Blog, Styling]
tags: [github gists, online compiling C#, try.dot.net]
---

You need a Gist on Github like this one below. As the title says, it is a C# code Gist.

![markdown](/assets/img/blog-images/2022-02-22/Gist.png)

You can enbed a static Gist code block lke this

```js
<script src="https://gist.github.com/anniekvandijk/b3ec5c9d047b31668605dde9e1165b38.js"></script>
```
That will show a nice block of code, but this does not compile.
<script src="https://gist.github.com/anniekvandijk/b3ec5c9d047b31668605dde9e1165b38.js"></script>

bufferId: The filename of the Gist (UnixEpochCounter.cs)   
fromGist: The id from the Url (b3ec5c9d047b31668605dde9e1165b38)


<iframe class="editor" id="example-iframe" title="Online code editor" style="" src="https://trydotnet.microsoft.com/v2/editor?waitForConfiguration=true&amp;instanceId=example"></iframe>

<script>
function setCodeFromGist() {
    var message = {
        type: "setWorkspaceFromGist",
        gistId: "b3ec5c9d047b31668605dde9e1165b38",
        bufferId: "UnixEpochCounter.cs"
    };

    postMessageToEditor(message);
}

function postMessageToEditor(message) {
    document.getElementById('example-iframe').contentWindow
        .postMessage(message, "https://trydotnet.microsoft.com");
}

</script>

