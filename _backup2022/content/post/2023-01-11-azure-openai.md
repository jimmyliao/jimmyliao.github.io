---
title: "Azure OpenAI Part 1: 初探 OpenAI Studio"
date: 2023-01-11T00:18:36+08:00
description: "Azure OpenAI Part 1: 初探 OpenAI Studio"
featured: false
draft: false
toc: false
# shareImage: "/images/fb_share.jpg"
shareImage: "/images/2023/2023-01/2023-01-11/openai_logo.jpg"
thumbnail: "/images/2023/2023-01/2023-01-11/openai_logo.jpg"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: true
categories:
  - Azure
  - OpenAI
tags:
  - Azure
  - OpenAI
---

最近 OpenAI 因為 ChatGPT 引起更多的關注, 加上今天這個新聞 [傳微軟計劃向 OpenAI 投資 100 億美元](https://technews.tw/2023/01/10/chatgpt-openai-microsoft/), 還有一年多之前這篇: [微軟新推Azure OpenAI服務，企業使用GPT-3的門檻更低了！](https://www.ithome.com.tw/news/147645). 覺得可以介紹如何在 Azure 上結合 OpenAI 服務到原有的企業使用情境. 這篇主要是先介紹 Azure 上針對 OpenAI 管理的工具 : Azure OpenAI Studio (https://oai.azure.com/portal).

<!--more-->

1. 首先, 先到 Azure Portal > Cognitive Services, 底下有個 Azure OpenAI.
  ![](/images/2023/2023-01/2023-01-11/01.png)

2. 因為還是 preview, 所以需要先申請 access, 基本上就是填線上表單. 通常 5-10 天 (但我好像隔天就收到了) 
  ![](/images/2023/2023-01/2023-01-11/02.png)

3. 收到申請通過信之後, 回到 Portal 建立 OpenAI resource. 建立時注意一下 [Pricing Page](https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/) (不過看了一下好像現在都一樣) 

4. 點 Explore 進入 OpenAI Studio 頁面 (https://oai.azure.com/portal), 選 `Go to playground`
  ![](/images/2023/2023-01/2023-01-11/03.png)

  ![](/images/2023/2023-01/2023-01-11/04.png)

5. 第一次進 Playground 還沒部署任何 OpenAI Model, 我們先到 Model Page 部署任一個來玩玩看吧!
  ![](/images/2023/2023-01/2023-01-11/05.png)

6. 回到 Playgound Page, 選取剛剛的 Deployment, 選取 Example
  ![](/images/2023/2023-01/2023-01-11/06.png)

   都英文沒感覺? 來試試中文

7. 仔細看一下摘要, 好像還算符合內容大意?
  ![](/images/2023/2023-01/2023-01-11/07.png)

下一篇就來看一下如何用 Python 串接 Azure OpenAI 吧~
