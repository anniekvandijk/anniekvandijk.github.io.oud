---
title: How to start a free blog
date: 2021-12-08 13:20:00 +0100
categories: [General]
tags: [jekyll, github pages]     # TAG names should always be lowercase
---

This is my first post ever on a personal blog page. Why now? 

I am working on a new project and I have some trouble finding information to help solve some challenges. I really like when someone takes the time to write a helpfull article. So I figured, this time maybe it is my turn to create some blog posts about my challenges and how I solved it. 

You can go to a site like Medium and start a blog there. I first thought this was the best way. But the problem is, you have no influence over this site. If they take your blog down, there is nothing you can do. 

Then I discovered Github Pages. You can start a free blog on Github really easy. 
1. Create a Github account
2. Get a Jekyll template
3. Create Github Pages repository
4. Learn some Markdown and write your first blog
5. Publish
6. Some tips

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/Github.png){: width="150" height="150" }

**Github** is a place where people all over the world store and share there software and work together on software. **Github Pages** is for hosting websites for your project information on Github. But you can do other things like hosting a blog website for personal use.

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/Jekyll.png){: width="150" height="150"} 

**Jekyll** is a blog-aware static site generator. Yehhh! It means it spits out plain text and shows it on a website. You do not have to be a developer to make nice websites!

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/markdown.png){: width="150" height="150"} 

Plain text is a bit boring. So some styling would be nice! **Markdown** is a lightweight markup language that you can use to add formatting elements to plaintext text documents.

---

## Step 1. Create a Github account 

Go to [https://github.com](https://github.com/) and make an GitHub Free account. Pay attention to your username, because this will be visible in your blog url. 

My accountname is anniekvandijk and my final blog url is https://anniekvandijk.github.io

## Step 2. Get a Jekyll template

Now you could follow the Guthub tutorial like I did first. You end up with little choice of templates, all focussed op project pages and not on blog websites.

So a better approach is looking for a nice blog template with a 'theme starter'. This installs a template on a new created repository and you can start right away. 

A nice starting point is [Jekyll templates free section](https://jekyllthemes.io/free) Most themes have a theme starter to get you up and running in no time. 

Minimal Mistakes is a very populair theme and they have a theme starter. It is a bit hard to find. Their normal template is [Mistakes Jekyll theme](https://jekyllthemes.io/theme/minimal-mistakes). When you go to their site on Github via the link at the bottom and scroll through their readme you can find a link to the theme starter somwhere half way the readme. Or, you just go to it by clicking [here](https://github.com/mmistakes/mm-github-pages-starter). In the readme of the theme starter you find a link to start the installation. When you click on it you are asked to create a new repository.

Important about this step. The name of the repository must be in a special format: \<username>.github.io. Because my username is anniekvandijk, I make a repository with the name anniekvandijk.github.io. It has to be a public repository.
![repo](/assets/img/blog-images/2021-12-08-First-post/Screenshot4.jpg)

Your site should be running after creating the repository!!!
In my case on https://anniekvandijk.github.io/.

### My template
![Chirpy](/assets/img/blog-images/2021-12-08-First-post/Screenshot1.jpg) 
I forgot how I found the template I use. But the name is Chirpy and it sounds kinda cute. A nice clean template. This is the link to the template. Follow the github link to Github and you can get the starter installer there.

[Chirpy Jekyll template](https://chirpy.cotes.info/)

## Step 4. Learn some Markdown and write your first blog

Markdown is really great by its powerfull but minimal easy to learn functionality. Best is just to learn it by writing your first blog. This is a nice [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) you can use. 

To write your first blog, follow the manual of the theme you installed. 

## 6. Some tips

- Make a good decission about the template you want to use. Changing it later is not always easy. So it needs to fit your needs as good as possible. 
- when you start a new post. Use a seperate 'branch' untill you think the post is good enough and then merge it with your main branch. 
- You can clone the repository to your local machine and run your website there until you are satisfied and then push the changes to the main branch. you need a IDE like [Visual Studio Code](https://code.visualstudio.com/) and some local installation of Ruby and Jekyll. Don't forget to install a Markdown extension in VS Code. You can find information for local running and more on the official [Jekyll site](https://jekyllrb.com/docs/)

