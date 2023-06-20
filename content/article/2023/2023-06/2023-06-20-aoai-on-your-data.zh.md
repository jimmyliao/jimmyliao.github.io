---
title: "在 Azure OpenAI Studio 使用你自己的資料集"
date: 2023-06-19T00:18:36+08:00
description: "在 Azure OpenAI Studio 使用你自己的資料集"
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
  - LLM
  - RAG
  - Azure
  - OpenAI
  - BYOD
---

今天 Azure 推出了 [Azure OpenAI Service On Your Data](https://techcommunity.microsoft.com/t5/ai-cognitive-services-blog/introducing-azure-openai-service-on-your-data-in-public-preview/ba-p/3847000)，[官方說明文件](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/use-your-data-quickstart?tabs=command-line&pivots=programming-language-studio) 也在幾小時前推出了。
這次的介紹文會直接以一個自己準備的中文文件 (特斯拉車主手冊)作為範例。

<!--more-->

1. 選擇 Upload files，選擇新增一個預備放文件的 Blob Storage，透過 AOAI 直接存取 Blob 需要打開 CORS。
    ![](/images/2023/2023-06/2023-06-19/01.png)

2. 新增或是選擇現有的 Azure Cognitive Search (之後會有另外的文章介紹)，並自行定義一個索引名稱，這邊我用的是 `reading-pdf-idx`。從電腦上傳準備好的文件 (這裡以中文 pdf 當作範例)，等待上傳完成，並點選下一步
    ![](/images/2023/2023-06/2023-06-19/02.png)

3. 檢視一下設定並點選 `Save and close`
    ![](/images/2023/2023-06/2023-06-19/03.png)

4. 等待 Azure Cognitive Search 針對文件建立索引。
    ![](/images/2023/2023-06/2023-06-19/04.png)
    ![](/images/2023/2023-06/2023-06-19/05.png)

5. 索引建立完成之後，就可以開始從 Azure OpenAI Studio chat preview 驗證囉
    ![](/images/2023/2023-06/2023-06-19/06.png)

