---
title: How to start a free blog
date: 2021-12-08 13:20:00 +0100
categories: [General]
tags: [jekyll, github pages]     # TAG names should always be lowercase
---

This is my first post ever on a personal blog page. Why now? 

I am working on a new project and I have some trouble finding information to help solve some challenges. I really like when someone takes the time to write a helpfull article. So I figured, this time maybe it is my turn to create some blog posts about my challenges and how I solved it. 

My first challenge to write about is how to get a free blog site. You can publish on a site like Medium really ease, but the problem is, you have no influence over this site and what they do with your post. 

Then I discovered **Github Pages**. You can start a free blog on Github really easy. 
1. Create a Github account
2. Find a Jekyll template you like with a theme starter
3. Create Github Pages Site with the theme starter
5. Learn some Markdown and write your first blog
6. Some tips

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/Github.png){: width="150" height="150" }

[**Github**](https://github.com/) is a place where people all over the world store and share there software and work together on software. **Github Pages** is for hosting websites for your project information on Github. But you can do other things like hosting a blog website for personal use.

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/Jekyll.png){: width="150" height="150"} 

[**Jekyll**](https://jekyllrb.com/) is a blog-aware static site generator. Yehhh! It means it spits out plain text and shows it on a website. You do not have to be a developer to make nice websites!

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/markdown.png){: width="150" height="150"} 

Plain text is a bit boring. So some styling would be nice! [**Markdown**](https://www.markdownguide.org/) is a lightweight markup language that you can use to add formatting elements to plaintext text documents.

---

## Step 1. Create a Github account 

Go to [https://github.com](https://github.com/) and make an GitHub Free account. Pay attention to your username, because this will be visible in your blog url. 

My accountname is anniekvandijk and my final blog url is https://anniekvandijk.github.io

## Step 2. Find a Jekyll template

A nice starting point is [jekyllthemes.io](https://jekyllthemes.io). You need to find a theme which is easy to install, like a theme with a theme starter. This installs a template on a new created repository and you can start writing in no time. 

Nice themes with a theme starter:
- [**Minimal Mistakes**](https://jekyllthemes.io/theme/minimal-mistakes), one of the most populair themes. Minimal Mistakes theme starter is a bit hard to find. When you go to their Github via the link at the bottom and scroll through their readme you can find a link to the theme starter somewhere half way the readme. Or, you just go to it by clicking [here](https://github.com/mmistakes/mm-github-pages-starter). In the readme of the theme starter you find a link to start the installation.
- [**Chirpy**](https://github.com/cotes2020/jekyll-theme-chirpy), my theme, has a starter too. You can find it [here](https://github.com/cotes2020/chirpy-starter).

## Step 3. Create Github Pages Site with a Theme starter

When you click on the theme starter link you are asked to create a new repository.

Important about this step. The name of the repository must be in a special format: \<username>.github.io. Because my username is anniekvandijk, I make a repository with the name anniekvandijk.github.io. It has to be a public repository.

Github has a build in publish functionality. It automaticaly publishes your changes on the main branch. Some starters have their own publish strategy. You will recognize these by the .nokekyll file in the root directory. My theme has that file and uses Github actions to publish the site on a seperate branch. If you follow the theme manual all will be ok :).

Your site should be running on https://\<username>.github.io/. In my case on https://anniekvandijk.github.io/. 

## Step 5. Learn some Markdown and write your first blog

Markdown is really great by its powerfull but minimal easy to learn functionality. Best is just to learn it by writing your first blog. This is a nice [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) you can use. 

To write your first blog create a new file in the _posts folder with this format: YEAR-MONTH-DAY-title.MD (2021-12-16-my-first-blog.md). This is all default for a Jekyll site. 

Then first add this to the file

```
---
layout: post
title:  "This is my first blog!"
---
```
And after that you can start writing in markdown. 

```
# Welcome

**Hello world**, this is my first Jekyll blog post.

I hope you like it!
```
If you commit this post. It will be saved and published on your new site. 

## 6. Some tips

- Make a good decission about the template you want to use. Changing it later is not always easy. So it needs to fit your needs as good as possible. 
- Installation instructions are all different. If you are more technical, you can try some advanced installs, else, really try to get a theme with a theme starter. 
- When you start a new post. Use a seperate 'branch' untill you think the post is good enough and then merge it with your main branch. 
- You can clone the repository to your local machine and run your website there until you are satisfied and then push the changes to the main branch. you need a IDE like [Visual Studio Code](https://code.visualstudio.com/) and some local installation of Ruby and Jekyll. Don't forget to install a Markdown extension in VS Code. You can find information for local running and more on the official [Jekyll site](https://jekyllrb.com/docs/)

