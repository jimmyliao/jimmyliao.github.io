---
title: "Azure OpenAI Part 2: Show me the code!"
date: 2023-01-1T02:18:36+08:00
description: "Azure OpenAI Part 2: Show me the code!"
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

[前一篇](https://jimmyliao.net/post/2023-01-11-azure-openai/) 介紹了申請以及使用 Azure OpenAI Studio (https://oai.azure.com/portal) 快速部署 Model 以及驗證. 這篇介紹如何使用 Python Code 整合進原本的應用程式.

<!--more-->

1. 在前一篇最後, 利用 Playground 測試 OpenAI 時, 不知道有沒有發現右上方有 `Code View` 這個按鈕?  
  ![](/images/2023/2023-01/2023-01-11/08.png)

2. 比對一下 Azure OpenAI 和 OpenAI 的範例.
 
    - Azure OpenAI 的範例

      ```python
      import os
      import openai
      openai.api_type = "azure"
      openai.api_base = "https://<YOUR-ENDPOINT-NAME>.openai.azure.com/"
      openai.api_version = "<OPENAI-API-VERSION>"
      openai.api_key = os.getenv("OPENAI_API_KEY")

      response = openai.Completion.create(
        engine="<MODEL-NAME>",
        prompt="..."
        temperature=0.7,
        max_tokens=60,
        top_p=1,
        frequency_penalty=0,
        presence_penalty=0,
        stop=None)    
      ```


    - OpenAI 官方網站的範例

      ```python
      import os
      import openai

      openai.api_key = os.getenv("OPENAI_API_KEY")

      start_sequence = "\nA:"
      restart_sequence = "\n\nQ: "

      response = openai.Completion.create(
        model="<MODEL-NAME>",
        prompt="...",
        temperature=0,
        max_tokens=100,
        top_p=1,
        frequency_penalty=0,
        presence_penalty=0,
        stop=["\n"]
      )
      ```

    看起來只需要 `OPENAI_API_KEY` 就可以了.

3. 回到 Azure Cognitive service 畫面, 點選 OpenAI 設定主畫面左方的選單 `Keys and Endpoint`. 將 Key1 的值複製作為 `OPENAI_API_KEY`
  ![](/images/2023/2023-01/2023-01-11/09.png)


4. 這次來試試 `code-davinci-002` 吧!

    ```python
    import os
    import openai
    openai.api_type = "azure"
    openai.api_base = "https://<ENDPOIND-NAME>.openai.azure.com/"
    openai.api_version = "2022-06-01-preview"
    openai.api_key = os.getenv("OPENAI_API_KEY")

    prompt = """Answer the question as truthfully as possible using the provided text, and if the answer is not contained within the text below, say "I don't know"

    Q: 幫我產生 ssh tunnel 的 bash script
    A:"""

    openai.Completion.create(
        engine="code-davinci-002",
        prompt=prompt,
        temperature=0,
        max_tokens=300,
        top_p=1,
        frequency_penalty=0,
        presence_penalty=0,
        model=COMPLETIONS_MODEL
    )["choices"][0]["text"].strip(" \n")    
    ```


    某種程度也算對...
  ![](/images/2023/2023-01/2023-01-11/09.png)



