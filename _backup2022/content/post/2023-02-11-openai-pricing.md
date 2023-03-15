---
title: "Azure OpenAI Part 5: 從 OpenAI 收費與 Token 計算方式，看看 ChatGPT Plus 的收費合理嗎？"
date: 2023-02-11T00:18:36+08:00
description: "Azure OpenAI Part 5: 從 OpenAI 收費與 Token 計算方式，看看 ChatGPT Plus 的收費合理嗎？"
featured: true
draft: false
toc: false
shareImage: "/images/fb_share.jpg"
thumbnail: "/images/2023/2023-02/2023-02-11/01.png"
# shareImage: "/images/2023/2023-01/2023-01-11/openai_logo.jpg"
# thumbnail: "/images/2023/2023-01/2023-01-11/openai_logo.jpg"
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

今年 (2023) 二月一日時，OpenAI 推出 [ChatGPT Plus](https://openai.com/blog/chatgpt-plus/)，一個月 $20 USD。更在二月十日時推出台灣也可以加入 ChatGPT Plus(有誠意!)，到底這個價格是不是合理？這一篇就從 OpenAI 收費與 Token 計算方式，看看 ChatGPT Plus 的收費到底合不合理。

<!--more-->

首先先設定一下背景知識：ChatGPT 跟 GPT-3 的差異。
- GPT-3 則是一個通用的語言模型，可以用來做各種任務，例如：翻譯、搜尋、產生文章、產生程式碼等等，而 ChatGPT 是基於 GPT-3 模型建立的一個專門應用，目的是用聊天機器人的方式展示 GPT-3 的能力。

(問一下 ChatGPT 好了 XD)
  ![](/images/2023/2023-02/2023-02-11/02.png)


第二個題目就是，原本如果你是直接使用 OpenAI 的 Playground，或是 API 方式串接 GPT-3 模型，你會發現免費額度只有前 100K tokens。之後就是照 [pricing plan](https://openai.com/api/pricing) 以 tokens 單位開始計算。啥？什麼是 tokens？tokens 是 OpenAI 計算 GPT-3 模型使用量的單位，而每個 token 的[計算方式](https://openai.com/api/pricing/#faq-token)是：
- 以英文字來說，每一個 token 約為 4 個字元或 0.75 個單字。
- 以中文字 (DBCS) 來說，每一個 token 約為 2 個字元或 0.5 個單字。

那如果純粹以 ChatGPT Plus: USD $20 反推使用 Inference capacity 最好的 Davinci 模型來看：
USD $20 = 1000,000 token
- 英文 約有 750,000 英文字
- 中文 (DBCS) 約有 37,500 個單字

另外根據[統計](https://www.linkedin.com/business/learning/blog/career-success-tips/you-speak-at-least-7-000-words-a-day-here-s-how-to-make-them)，一個人一天大約會說 7,000 個單字，也就是說，一個月的單字數應該是 210,000 個單字。由於 Token 計算是提問與回答，所以我們將數量乘以 2，也就是說，約需產生 420,000 個單字，如果中文使用是再 Double 計算 token 用量。單純將 ChatGPT 當作 GPT-3 的 Text-davinci 模型來使用，應該是用不完，而且加上宣稱的尖峰時刻快樂使用、優先使用新功能，還有更快的回應時間，這個價格其實蠻划算的。

另外再附上 OpenAI 的 token 計算機，可以讓你自行估算。只需要貼上你的問題與回答，就可以看到字元數，與實際 token 數。
[tokenizer](https://platform.openai.com/tokenizer)
  ![](/images/2023/2023-02/2023-02-11/03.png)


那回頭來看看，以開發者的角度來看，如果你是要使用 GPT-3 來做產品，那你應該會考慮使用 [OpenAI API](https://openai.com/blog/openai-api/)，而不是使用 ChatGPT。因為 OpenAI API 可以讓你根據需求，自行設定模型與參數，而且 Pay-as-you-go 的計價方式，可以讓你更精準的控管成本。

而且如果以企業級的角度，如何評估 OpenAI 是否與企業原有的服務整合，必須考慮到 compliance、地域性、安全性等等，那你應該會選擇使用 [Azure OpenAI](https://azure.microsoft.com/zh-tw/services/openai/)，這樣你就可以在 Azure 上使用 OpenAI API，並且可以享有 Azure 整合方便。其他關於企業如何評估如何整合雲端服務，請參考 Azure 雲端採用架構 [Cloud Adoption Framework](https://docs.microsoft.com/zh-tw/azure/cloud-adoption-framework/)。
