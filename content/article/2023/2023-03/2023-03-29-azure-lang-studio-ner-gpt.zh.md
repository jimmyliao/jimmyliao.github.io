---
title: "在 Azure Language Studio 使用 GPT 模型加速 Labeling 工作"
date: 2023-03-29T00:18:36+08:00
description: "在 Azure Language Studio 使用 GPT 模型加速 Labelling 工作"
featured: false
draft: false
toc: false
shareImage: "/images/fb_share.jpg"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: true
categories:
  - Azure
  - Cognitive
  - GPT
---


兩周前 Azure Language Studio 公告了一個預覽的新功能: [利用 GPT 模型來加速 Labeling 的過程](https://techcommunity.microsoft.com/t5/ai-cognitive-services-blog/accelerate-labelling-with-gpt-models-in-language-cognitive/ba-p/3769264)，我們就來試試看吧。

(P.S. 此功能目前是支援文字部分)

<!--more-->

1. 記得在 Azure OpenAI 中先佈署 text-davinci-002 模型，然後在 Access Control (IAM) 中設定好權限，這樣才能在 Azure Language Studio 中使用。

  ![](/images/2023/2023-03/2023-03-29/01.png)

2. 然後從 [Language Studio](https://language.cognitive.azure.com/) 建立 Custom named entity recognition 專案。

  ![](/images/2023/2023-03/2023-03-29/02.png)

將 label 檔案上傳到 Language Studio 的 Blob 中，記得準備至少 10 個 label 檔案，這樣才能使用 GPT 模型。這陣子剛好在看 Reid Hoffman 的 [Impromptu](https://www.linkedin.com/pulse/impromptu-my-new-book-possible-podcast-reid-hoffman/)，就拿他的一段來當 label 檔案。

3. 終於可以開始使用 GPT 模型了，點選 `Data labeling`，然後右側的 `Auto-label`。

  ![](/images/2023/2023-03/2023-03-29/03.png)

4. 這時候可以直接選取對應的 Azure OpenAI，以及 GPT 模型，照推薦的 text-davinci-002 來選擇，然後選擇要使用的 label 檔案，新增 Entity 　(或是選取現有的 Entity)，最後點選 Start labeling job。

  ![](/images/2023/2023-03/2023-03-29/04.png)

5. 等待一段時間，就可以看到 Labeling Job 完成了。

  ![](/images/2023/2023-03/2023-03-29/05.png)


6. 上傳的檔案會自動被 GPT 模型標記，然後還是需要人工檢查，確認標記的正確性。
  ![](/images/2023/2023-03/2023-03-29/06.png)

是不是很方便呢!

Reference: https://techcommunity.microsoft.com/t5/ai-cognitive-services-blog/accelerate-labelling-with-gpt-models-in-language-cognitive/ba-p/3769264

 