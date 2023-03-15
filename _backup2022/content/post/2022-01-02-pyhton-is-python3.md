---
title: "Change the default python to Python3.8 on Ubuntu 20.04 fresh install"
date: 2022-01-02T22:10:36+08:00
description: "Change the default python to Python3.8 on Ubuntu 20.04 fresh install"
featured: false
draft: false
toc: false
shareImage: "/images/fb_share.jpg"
thumbnail: "https://symbols.getvecta.com/stencil_92/73_python-icon.3d49e95599.svg"
codeMaxLines: 10
codeLineNumbers: false
figurePositionShow: true
categories:
  - Ubuntu
tags:
  - Ubuntu
---


Just realized there is a specific package to resolve.

<!--more-->

When got the fresh installed Ubuntu Focal Fossa server edition, you can use python3 but the default python has not set yet.

```
ubuntu@prime:~$ python

Command 'python' not found, did you mean:

  command 'python3' from deb python3
  command 'python' from deb python-is-python3

ubuntu@prime:~$ python3
Python 3.8.10 (default, Nov 26 2021, 20:14:08)

```

Follow the official doc to `update-alternatives` then got this:

```
ubuntu@prime:~$ sudo update-alternatives --set python /usr/bin/python3.8

update-alternatives: error: no alternatives for python

```

There are two methods to resolve:

Method 1: 
```
ubuntu@prime:~$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8 1

ubuntu@prime:~$ sudo update-alternatives --config python
There is only one alternative in link group python (providing /usr/bin/python): /usr/bin/python3
Nothing to configure.

```

Method 2: use the `python-is-python3` package
```
ubuntu@prime:~$ sudo apt install -y python-is-python3
```

```
ubuntu@prime:~$ python -V
Python 3.8.10
```

**Enjoy!**

