---
title: "HOWTO: connect to remote 1-click PrimeHub"
date: 2021-09-24T23:35:28+08:00
description: "HOWTO: connect to remote 1-click PrimeHub"
featured: true
draft: false
toc: false
# menu: main
featureImage: "https://media-exp1.licdn.com/dms/image/C5622AQGy4L3zDziIxQ/feedshare-shrink_2048_1536/0/1631541656531?e=1635984000&v=beta&t=kPWgK-Mq21n6zO1rTJ4lM1S6npq8qyvywNGV2EN4OqU"
# shareImage: "/images/fb_share.jpg"
shareImage: "https://media-exp1.licdn.com/dms/image/C5622AQGy4L3zDziIxQ/feedshare-shrink_2048_1536/0/1631541656531?e=1635984000&v=beta&t=kPWgK-Mq21n6zO1rTJ4lM1S6npq8qyvywNGV2EN4OqU"
codeMaxLines: 10
codeLineNumbers: false
figurePositionShow: true
categories:
  - Kubernetes
tags:
  - Kubernetes
  - K9S
  - MicroK8s
---


**How to connect to remote [1-click PrimeHub](https://one.primehub.io) instance**

<!--more-->

PrimeHub [3.8](https://medium.com/infuseai/whats-new-in-primehub-3-8-40f107035fbc) 開始提供了 1-click to AWS 的快速部屬 PrimeHub 方式，點下 `1-Click Install on AWS` 之後，填入你的 email 並點下 Deploy 之後，就可以先去喝杯咖啡等待郵件通知 PrimeHub on AWS 部屬完成。

![](/images/2021-09-24-01.png)

不過從系統管理角度，如何透過 kubectl 連到遠端的 1-click PrimeHub 呢？

很簡單，在收到的 email 裡面有個連結，會先 redirect 到 AWS CloudFormation 畫面。

![](/images/2021-09-24-02.png)

裡面有幾個提示，主要把紅色這段複製貼上到 Terminal 即可。(該裝的 AWS cli 跟 credential 什麼的還是要設定一下)

![](/images/2021-09-24-03.png)

又可以快快樂樂使用 K9S 啦！

![](/images/2021-09-24-04.png)

![](/images/2021-09-24-05.png)
