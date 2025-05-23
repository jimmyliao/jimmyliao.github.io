---
title: "利用 Docker 建立 SQL Server 2022 開發版本環境"
date: 2023-05-10T00:18:36+08:00
description: "利用 Docker 建立 SQL Server 開發版本環境"
featured: false
draft: true
toc: false
shareImage: "/images/fb_share.jpg"
thumbnail: "/images/fb_share.jpg"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: true
categories:
  - Docker
  - SQL
---

在準備內部技術分享時，想說把這陣子玩 LangChain 的心得找個主題搭配強迫自己學點不一樣的，於是想到 SQL Server，有自家 Azure SQL，安裝的版本也有，但是我只求快速驗證，選了 Docker 版本，這篇順道介紹使用 Azure Data Studio 怎麼連結驗證，當作初心者的筆記吧。


<!--more-->

1. 使用 Docker command 手動下載 SQL Server 2022 開發版本
```
$ docker pull mcr.microsoft.com/mssql/server:2022-latest


$ docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=YourStrong-Passw0rd" -p 1433:1433 --name sql1 --hostname sql1 -d mcr.microsoft.com/mssql/server:2022-latest
```

2. 搞定！

  ![](/images/2023/2023-05/2023-05-10/01.png)


 