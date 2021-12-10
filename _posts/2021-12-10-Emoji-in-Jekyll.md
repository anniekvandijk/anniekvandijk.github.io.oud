---
title: How to get emoji on your Jekyll Github pages
date: 2021-12-10 15:20:00 +0100
categories: [General, Blog]
tags: [jekyll, emoji, jemoji, github pages]
---

I am used to the emoji short text where you can put something like `: blush :` in your text and it pops up like a nice emoij :blush:. When I first did this on my blog, nothing happened. 

Apparently, you need to install a special compatible plugin **jemoji** to get the emoji working on Github pages. The short manual:

## Steps

---

Add the following to your site's Gemfile
```
gem 'jemoji'
```
And add the following to your site's _config.yml
```
plugins:
  - jemoji
```
If you are working on a local machine, run
```
$ bundle install
```
If not, just do a new commit to your Jekyll repository and it will trigger the new plugin to be build. 

## Links

 ---
 - [*About GitHub Pages and Jekyll*](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll) 
 - [*Jemoji Github repository*](https://github.com/jekyll/jemoji)
 - [*Emoji Cheat Sheet*](http://www.iemoji.com/emoji-cheat-sheet/all)


