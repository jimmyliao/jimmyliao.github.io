---
title: "Sign-off for previous git commit"
date: 2022-01-11T03:10:36+08:00
description: "Sign-off for previous git commit"
featured: false
draft: false
toc: false
shareImage: "/images/fb_share.jpg"
# featureImage: "https://mac.getutm.app/images/logo@2x.png"
# thumbnail: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/56/UTM_Logo.png/440px-UTM_Logo.png"

codeMaxLines: 10
codeLineNumbers: false
figurePositionShow: true
categories:
  - Git
tags:
  - Git
---

To signoff the previous commit, use amend option. 

<!--more-->
```
git commit --amend --no-edit --signoff
git push --force-with-lease origin <your-feature-branch>
```


**Enjoy!**
