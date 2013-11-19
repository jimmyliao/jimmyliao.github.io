---
layout: post
title: "my first octopress"
date: 2013-11-19 21:08:03 +0800
comments: true
sharing: true
footer: true
categories: 
- Blog
- Markdown
---

this page uses the [Markdown](http://daringfireball.net/projects/markdown/) syntax. (or refer: https://help.github.com/articles/github-flavored-markdo
wn)

#1. /README.md
```
This file is to describe the myconfig file structure and how to use
```

# Tweaks:
http://stackoverflow.com/questions/17609453/rake-gen-deploy-rejected-in-octopress
Edit the Rakefile and look for this line:
```
system "git push origin #{deploy_branch}"
```
Alter the line by adding a plus (+) before the #{deploy_branch} tag:
```
system "git push origin +#{deploy_branch}"
```
Run the command

```
rake deploy
```

## References:

http://zespia.tw/blog/2012/01/14/hello-octopress/
http://zerodie.github.io/blog/2012/01/19/octopress-github-pages/

git pull origin master

[Fast deploy post]
rake generate
rake preview

[Remember to push&deploy]
git add .
git commit -m "msg"
git push origin master

rake deploy

