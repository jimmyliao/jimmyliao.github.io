---
title: "使用 Redis Client - RedisInsight 管理 Azure Redis Cache"
date: 2023-04-30T00:18:36+08:00
description: "使用 Redis Client - RedisInsight 管理 Azure Redis Cache"
featured: false
draft: false
toc: false
shareImage: "/images/fb_share.jpg"
thumbnail: "/images/fb_share.jpg"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: true
categories:
  - Azure
  - Redis
---

最近需要利用 Azure Redis Enterprise 進行專案整合，但是發現原本在使用的 Another Redis Desktop Manager 怎麼設定都沒成功，找了一下，發現 Redis 官方有提供一個 Redis Client - [RedisInsight](https://redis.com/redis-enterprise/redis-insight/)，花了點時間設定之後，發現其實就是江湖一點訣，記錄一下，免得之後又忘記。


<!--more-->

1. 首先記下 Azure Redis Cache 的連線資訊，基本上就是 Endpoint, Port 跟 Access Key。然後 Advanced Settings 中的 Non-TLS access only 勾勾記得不要打開。


2. 打開 RedisInsight，使用 `Add Database Manually` 新增，Host = Endpoint，Port = <port>，Password = Access Key，然後記得 `Use TLS` 勾一下。點選 Add。

  ![](/images/2023/2023-04/2023-04-30/01.png)

3. 搞定！

  ![](/images/2023/2023-04/2023-04-30/02.png)


 