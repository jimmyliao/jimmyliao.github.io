---
title: "Azure 的五十個小劇場...之 Kusto Detective Agency 2022"
date: 2022-12-23T00:10:36+08:00
description: "Kusto Detective Agency 2022"
featured: true
draft: false
toc: false
# shareImage: "/images/fb_share.jpg"
thumbnail: "https://miro.medium.com/max/1226/1*cYOq7tOU2a6S9gwwY8hjJQ.webp"
shareImage: "https://images.credly.com/size/680x680/images/84201552-025f-4b97-81c4-55be4ba896ff/image.png"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: true
categories:
  - Azure
tags:
  - Azure
  - ADX
  - Kusto
---

之前的案子接觸了 Azure Data Explorer 跟 SDK 開發，想說把之前理解的整理一下，發現這個有趣的 Challenge ，透過案例方式熟悉跟釐清基本的 KQL 觀念。
(先預告一下，接下來會講如何用 SDK 開發。)

<!--more-->

1. 先到 https://detective.kusto.io/ ，點選 Inbox。



2. 依照指示建立 free cluster
https://dataexplorer.azure.com/publicfreecluster
    ![](/images/2022/2022-12/2022-12-23/2022-12-23-01.png)

3. 建立好 free cluster 之後會自動帶到 ADX 畫面，記得將 Cluster URI 複製，待會會填入到 Challenge

    ![](/images/2022/2022-12/2022-12-23/2022-12-23-02.png)

4. 將前一個步驟的 Cluster URI 填入
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-03.png)


5. 接著依照指示打開 Query 工具，將底下 Onboarding 的 Database 建起來。
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-04.png)
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-05.png)

6. 先用個簡單的 KQL 找 Score 加總吧！
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-06.png)


7. 回到 Challenge 畫面填入答案跟你的 free cluster URL.
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-07.png)

8. 答案正確的話，會需要你的 Credly 資訊。
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-08.png)
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-09.png)

9. 恭喜！開始你的 Azure Data Explorer (Kusto) 挑戰吧～
  ![](/images/2022/2022-12/2022-12-23/2022-12-23-10.png)




