---
title: "Using Crane to Build Custom Image with 1-Click PrimeHub"
date: 2021-11-12T23:50:16+08:00
description: "Using Crane to Build Custom Image with 1-Click PrimeHub"
featured: true
draft: false
toc: false
# menu: main
shareImage: "https://raw.githubusercontent.com/InfuseAI/crane/main/public/images/Logo_hori.png"
featureImage: "https://raw.githubusercontent.com/InfuseAI/crane/main/public/images/Logo_hori.png"
thumbnail: "https://raw.githubusercontent.com/InfuseAI/crane/main/public/images/Logo_hori.png"
codeMaxLines: 10
codeLineNumbers: false
figurePositionShow: true
categories:
  - Kubernetes
  - Linux
tags:
  - Kubernetes
  - Linux
---

**先快速來個中文版**

[Crane](https://medium.com/infuseai/crane-the-minimalist-container-image-builder-68253722be8c) 是 InfuseAI 剛推出的[ Open Source Project](https://github.com/InfuseAI/crane)，簡言之就是可以在已經[裝好 Docker](https://docs.docker.com/engine/install/) 的電腦上，免除撰寫 Dockerfile ，也免除透過 Command 方式編譯 Docker Image。另外也提供快速把自己在 Docker Hub 編譯好的 Image 加入 PrimeHub 環境裡，以下的範例，就以之前介紹的 [1-Click 環境](http://localhost:1313/post/2021-09-24-primehub-oneclick/)，[客製化 Docker Image](https://docs.primehub.io/docs/guide_manual/admin-image#build-custom-image)，裡面包含 PrimeHub 新推出的 [SDK](https://github.com/InfuseAI/primehub-python-sdk) 。來看看吧～


<!--more-->

[下載 Crane](https://github.com/InfuseAI/crane/releases/tag/v1.0.0) 安裝之後，有兩個資訊需要先準備：
- Docker Hub 的登入帳號/密碼

![](/images/2021-11-12-001.png)

- PrimeHub 的 `API TOKEN` (總之就是點下 `Request API Token` 並且另外記錄下來，因為只會出現一次)
![](/images/2021-11-12-002.png)

- 打開裝好的 Crane，點選設定圖示，分別設定 Docker Hub 以及 1-Click PrimeHub 的資訊。如果還沒有用過 [1-Click](https://one.primehub.io/)，這邊也還有按鈕可以快速新增！
![](/images/2021-11-12-003.png)

- 點選新增，開始建立 Image，因為 Docker Hub 可以 push 的權限是以自己的 username，這邊記得填 `<docker_username>/<image-name>`
![](/images/2021-11-12-003-2.png)

- 點 `Build` 成功之後，會在 `Images` > `LOCAL` 底下看到
![](/images/2021-11-12-004.png)

- 在 `REMOTE REPOSITORIES`，記得點選左方的 `+` 展開，點選 `ADD`，就可以快速新增剛剛建好的 Image 到 PrimeHub 環境。
![](/images/2021-11-12-005.png)

- 設定在 PrimeHub 裡面會看到的 Image Description (群組/名稱/支援 CPU/GPU/Universal)
![](/images/2021-11-12-006.png)

- 點選 `Create` 之後，如果成功會看到這個。 
![](/images/2021-11-12-007.png)

- 接著切換到 PrimeHub 介面，確認已經透過 Crane 新增 Image 成功！
![](/images/2021-11-12-008.png)

- 打開 Notebook 確認一下～
![](/images/2021-11-12-009.png)


**Enjoy!**

