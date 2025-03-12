---
layout: post
title: "octopress from zero"
date: 2013-11-19T22:07:46:00+08:00
comments: true
categories: 
- Blog
- Markdown
---
How to use rake & git with your octopress.

Reference: 
http://octopress.org/docs/blogging/
http://zerodie.github.io/blog/2012/01/19/octopress-github-pages/

<!--more-->

1. How to new post
rake new_post
Enter a title for your post: "Octopress from zero...again!"
Creating new post: source/_posts/2014-03-15-octopress-from-zero-dot-dot-dot-again.markdown

2. Edit the markdown file

3. Generate & Preview
-> rake generate
-> rake watch 
-> rake preview (preview on localhost:4000)

4. Push & Deploy
-> git add .
-> git commit -m "..."
-> git push origin master
-> rake deploy


