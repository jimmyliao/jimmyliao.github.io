---
title: "Got Host key verification failed while SSH"
date: 2022-01-18T03:10:36+08:00
description: "Got Host key verification failed while SSH"
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
  - SSH
  - Command
tags:
  - SSH
  - Command
---

Got Host key verification failed while SSH

```
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!

The fingerprint for the ECDSA key sent by the remote host is SHA256:xxx. Please contact your system administrator. 
Add correct host key in xxx/.ssh/known_hosts to get rid of this message. Offending ECDSA key in xxx/.ssh/known_hosts:12 ECDSA host key for xxx.yyy.zzz.aaa has changed and you have requested strict checking. Host key verification failed.
```

<!--more-->
```
ssh-keygen -R <YOUR_TARGET_HOST>
# Host <YOUR_TARGET_HOST> found: line 200
xxx/.ssh/known_hosts updated.
```

