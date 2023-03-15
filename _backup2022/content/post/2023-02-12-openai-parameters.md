---
title: "Azure OpenAI Part 6: GPT-3 裡面的微調參數 - 溫度 (temperature)"
date: 2023-02-12T00:18:36+08:00
description: "Azure OpenAI Part 6: GPT-3 裡面的微調參數 - 溫度 (temperature)"
featured: true
draft: false
toc: false
shareImage: "/images/fb_share.jpg"
# thumbnail: "/images/2023/2023-02/2023-02-11/01.png"
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

上週瞄到某個討論串的內容：(略 1000 字)...「溫度真的有用嗎？」，覺得這個問題不如直接動手實驗看看，順便把結果分享一下。

<!--more-->

你可以看到 GPT-3 的預設參數是：

```json
{
  "engine": "davinci",
  "prompt": "This is a test",
  "max_tokens": 5,
  "temperature": 0.9,
  "top_p": 1,
  "n": 1,
  "stream": false,
  "logprobs": null,
  "stop": "\n"
}
```

從 Azure OpenAI Studio Playground (或是 OpenAI Playgound 也可以) 看到關於 `temperature` 的說明：
簡單來說，`temperature` 越高，模型輸出的結果就會越隨機，越低就會越有規律。

  ![](/images/2023/2023-02/2023-02-12/02.png)

原來這就是虎爛程度產生器的原理嘛(誤)。

我們可以把 `temperature` 調到 1，看看結果：
  ![](/images/2023/2023-02/2023-02-12/01.png)

先不論加菲貓是不是屬於貓的品種，這回答重複的答案還有夠多。

再把 `temperature` 調到 0，看看結果：
  ![](/images/2023/2023-02/2023-02-12/03.png)

雖然沒有回答到所有答案，但是看起來至少合理而且不重複。

另外根據文件， `temperature` 跟 `top_p` 通常是不建議一起使用的，因為 `top_p` 本身就是一種概率分佈，所以 `temperature` 會讓分佈更加隨機。

總之，利用 OpenAI 的 API 開發時，記得根據你的使用情境，調整 `temperature` 的值。

附上 ChatGPT 的回答，看起來至少比 GPT-3 原生的模型好一點點，有調整過有差！
  ![](/images/2023/2023-02/2023-02-12/00.png)

