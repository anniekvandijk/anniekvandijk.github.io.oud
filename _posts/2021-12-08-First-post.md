---
title: How I started a free blog with Github, Jekyll and Chirpy in 10 minutes
date: 2021-12-08 13:20:00 +0100
categories: [General, Blog]
tags: [jekyll, github, github pages, chirpy, markdown, yekyll theme starter]
---

This is my first post ever on a personal blog page. Why now? 

I am working on a new project, and I have some trouble finding information to help solve some challenges. I really like when someone takes the time to write a helpful article. So, I figured, this time maybe it is my turn to create some blog posts about my challenges and how I solved it. 

My first challenge to write about is how to get a free blog site. You can publish on a site like Medium really ease, but the problem is, you have no influence over this site and what they do with your post. 

Then I discovered **Github Pages**. You can start a free blog on Github really easy. What I did:
1. Login to my a Github account
2. Find a Jekyll theme I liked with a Theme Starter
3. Create Github Pages Site with the Theme Starter
5. Learn some Markdown and made my first blog
6. Publish the blog
7. Change site settings
8. Things I did afterwards and some tips

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/Github.png){: width="150" height="150" }

[**Github**](https://github.com/) is a place where people all over the world store and share their software and work together on software. **Github Pages** is for hosting websites for your project information on Github. But you can do other things like hosting a blog website for personal use.

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/Jekyll.png){: width="150" height="150"} 

[**Jekyll**](https://jekyllrb.com/) is a blog-aware static site generator. Yehhh! It means it spits out plain text and shows it on a website. You do not have to be a developer to make nice websites!

---

![Chirpy](/assets/img/blog-images/2021-12-08-First-post/chirpy.jpg){: width="150" height="150"} 

[**Chirpy**](https://chirpy.cotes.info/), my theme with a nice Theme starter. 

---

![markdown](/assets/img/blog-images/2021-12-08-First-post/markdown.png){: width="150" height="150"} 

Plain text is a bit boring. So some styling would be nice! [**Markdown**](https://www.markdownguide.org/) is a lightweight markup language that you can use to add formatting elements to plaintext text documents.

---

## Step 1. Login to my a Github account

So I have a github account, but if you do not have an account, go to [https://github.com](https://github.com/) and make a GitHub Free account. Pay attention to your username, because this will be visible in your blog url. 

My accountname is anniekvandijk and my final blog url is https://anniekvandijk.github.io

## Step 2. Find a Jekyll theme I liked with a Theme Starter

A nice starting point I found is [**jekyllthemes.io**](https://jekyllthemes.io). There I found [**Minimal Mistakes**](https://jekyllthemes.io/theme/minimal-mistakes), one of the most popular themes with a starter. But,  after some googling, I found [**Chirpy**](https://github.com/cotes2020/jekyll-theme-chirpy). Also a nice theme with a Theme Starter which I liked more. This theme has a starter too. You can find it [**here**](https://github.com/cotes2020/chirpy-starter).

## Step 3. Create Github Pages Site with the Theme Starter

So I clicked on the Theme Starter link and it redirected me to the page where you can create a new repository. The Heading of the page:

```
Create a new repository from chirpy-starter
The new repository will start with the same files and folders as cotes2020/chirpy-starter.
```

To make a Github Pages repository, 
the name of the repository must be in a special format: 
```
<username>.github.io.
```
Because my username is anniekvandijk, I make a repository with the name anniekvandijk.github.io. Also, it has to be a public repository. When I pressed the *Create repository from template* button. After a few seconds I had a new repository with one branch (main) and all files I needed in it. 

> Github has a **build in publish functionality for Jekyll**. It automatically publishes your changes on the main branch. Some starters have their own publish strategy. You will recognize these by the .nojekyll file in the root directory. Which blocks building the site by Github.

Chirpy has that .nojekyll and uses Github actions to publish the site on a separate branch named gh-pages. This branch is created when saving the first blog. 

## Step 5. Learn some Markdown and made my first blog

Markdown is great by its powerful but minimal and easy to learn functionality. Best is just to learn it by writing your first blog. This is a nice [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) I used.

To write my first blog I created a new file in the `_posts` folder with this format: `YEAR-MONTH-DAY-title.md`, example: 2021-12-16-my-first-blog.md. This is all default for a Jekyll site. 

Then first add this to the top of the file:

```
---
title: TITLE
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [TAG]     # TAG names should always be lowercase
---
```
These are my first lines:
```
---
title: How I started a free blog with Github and Jekyll in 10 minutes
date: 2021-12-08 13:20:00 +0100
categories: [General, Blog]
tags: [jekyll, github, github pages, chirpy, markdown, yekyll theme starter]
---
```

And after that you can start writing in markdown. 

```
# Welcome

**Hello world**, this is my first Jekyll blog post.

I hope you like it!
```
So after some time I was satisfied and commited the blog at the bottom of the page.

## Step 6. Publish the blog

If you commit the first post (at the bottom of the page). It will be saved in the _post directory, but there is happening more! In the background, a process runs to create all files for the blog site. This files are put into a new branch named gh-pages.

The last thing I have to do to get my site online is switching the default Github Pages branch from main to gh-pages. 
- Go to the Settings of your repository to the Pages section and change the Source branch from main to gh-pages. 

![Repo](/assets/img/blog-images/2021-12-08-First-post/change-source.jpg)

After hitting save my site should be running on 
[https://anniekvandijk.github.io](https://anniekvandijk.github.io), and it it!

## 7. Change site settings

My blog is posted and it looks fine. But to get all in place, I have to edit some settings in the config file and some other files. Things you can - or need to edit -  is different for every theme. But most of the time things like social media names and urls need to be changed to point to your information.

 I found 3 settings files I changed:

```
_config.yml
_data/contact.yml
_data/share.yml
```
I changed things like this in the _config.yml. The other files speak for themselves. 

I did have some trouble with getting my avatar in the right place. I made a new folder in the root, named `assets` and put my avatar in there. When building, it will be merged in the `_site/assets folder`. And I changed the avatar path like this:

```yaml
# the avatar on sidebar, support local or CORS resources
avatar: '/assets/avatar.jpg'
```
In the assets folder you can also put your images you use in the blogs. My blog images I put in a directory `/assets/img/blog-images/\<blogpagename>/`, now I know which images belong to which blog. 

One of the things I do not like about this theme is the integration with Discus. I kept it disabled. I am looking for another Comments system. Also I want some other styling for the pictures and a heading picture in the posts section. And Emoji, which do not seem to work right now. But first, publish this and then move on do other fun stuff :smile:

## Things I did afterwards and some tips

- I cloned the repository locally to run it on my computer to see the results better in (a real browser) without publishing. You can clone the repository to your local machine and run your website there until you are satisfied and then push the changes to the main branch. you need a IDE like [Visual Studio Code](https://code.visualstudio.com/) and some local installation of Ruby and Jekyll. Don't forget to install a Markdown extension in VS Code. You can find information for local running and more on the official [Jekyll site](https://jekyllrb.com/docs/).

- I work in a separate branch for a new post, to save more often without publishing. Use a separate 'branch' until you think the post is good enough and then 'merge' it with your main branch with a 'pull request'. When you start commit a post, you can choice to save it to a different branch.

- Make a good decission about the template you want to use. Changing it afterwards is not always easy. So it needs to fit your needs as good as possible. 

- Installation instructions are all different. If you are more technical, you can try some advanced installs, else, really try to get a theme with a Theme Starter.
