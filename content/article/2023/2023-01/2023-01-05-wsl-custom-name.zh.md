---
title: "How to custom your WSL distro name"
date: 2023-01-05T00:18:36+08:00
description: "How to custom your WSL distro name"
featured: false
draft: false
toc: false
shareImage: "/images/2023/2023-01/2023-01-05/2023-01-05-wsl-01.png"
thumbnail: "/images/2023/2023-01/2023-01-05/2023-01-05-wsl-01.png"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: false
categories:
  - Windows
tags:
  - Windows
---

There is no options of WSL command to achive this, I can only do with...

<!--more-->

1. WSL Export -> Import

    ```bash
    wsl --export Ubuntu-22.04 .\thinkpad-wsl-ubuntu2204.tar  

    wsl --import ubuntu .\ .\thinkpad-wsl-ubuntu2204.tar  
    ```


2. check by `wsl -l -v`
  ![](/images/2023/2023-01/2023-01-05/2023-01-05-wsl-02.png)


![](/images/2023/2023-01/2023-01-05/2023-01-05-wsl-03.png)


