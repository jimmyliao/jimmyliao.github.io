---
title: "解決 WSL help prompt 出現自動翻譯的問題"
date: 2022-12-30T00:18:36+08:00
description: "解決 WSL help prompt 出現自動翻譯的問題"
featured: false
draft: false
toc: false
shareImage: "/images/2022/2022-12/2022-12-30-wsl/2022-12-30-01.png"
thumbnail: "/images/2022/2022-12/2022-12-30-wsl/2022-12-30-01.png"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: false
categories:
  - Windows
tags:
  - Windows
---

這幾天在 Windows 上面跟 Terminal 和 WSL 套交情，昨天踩了這個[地雷](https://jimmyliao.net/post/2022-12-25-windows-command-prompt/)。後來發現一個 workaround。

然後突然發現 Terminal/Powershell 何時開始有內建 Tab 功能了？ 

<!--more-->

1. 設定 > 時間與語言 > 語言與地區 > 慣用語言 > **把英文移到第一個**
  ![](/images/2022/2022-12/2022-12-30-wsl/2022-12-30-02.png)

2. 成功！
  ![](/images/2022/2022-12/2022-12-30-wsl/2022-12-30-03.png)

