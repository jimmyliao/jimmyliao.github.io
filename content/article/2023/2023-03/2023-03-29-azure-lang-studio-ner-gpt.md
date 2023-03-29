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


Two weeks ago, Azure Language Studio announced a new preview feature: [Accelerate Labelling with GPT Models in Language Cognitive Services](https://techcommunity.microsoft.com/t5/ai-cognitive-services-blog/accelerate-labelling-with-gpt-models-in-language-cognitive/ba-p/3769264). Let's try it out. 

<!--more-->

1. Remember to deploy the text-davinci-002 model in Azure OpenAI first, and then set up the permissions in Access Control (IAM), so that you can use it in Azure Language Studio. 

  ![](/images/2023/2023-03/2023-03-29/01.png)

2. Then create a Custom named entity recognition project from [Language Studio](https://language.cognitive.azure.com/). 
  ![](/images/2023/2023-03/2023-03-29/02.png)

Upload the label file to the Blob in Language Studio, remember to prepare at least 10 label files, so that you can use the GPT model. I'm just reading Reid Hoffman's [Impromptu](https://www.linkedin.com/pulse/impromptu-my-new-book-possible-podcast-reid-hoffman/) these days, so I'll use a section of it as a label file.

3. Finally, you can start using the GPT model. Click on `Data labeling`, and then `Auto-label` on the right.

  ![](/images/2023/2023-03/2023-03-29/03.png)

4. Now you can directly select the corresponding Azure OpenAI, as well as the GPT model, choose text-davinci-002 according to the recommendation, and then select the label file to use, add Entity (or select an existing Entity), and finally click Start labeling job. 

  ![](/images/2023/2023-03/2023-03-29/04.png)

5. Wait for a while, you can see that the Labeling Job is completed. 

  ![](/images/2023/2023-03/2023-03-29/05.png)


6. The uploaded files will be automatically labeled by the GPT model, but they still need to be manually checked for accuracy.
  ![](/images/2023/2023-03/2023-03-29/06.png)

Mission accomplished.

Reference: https://techcommunity.microsoft.com/t5/ai-cognitive-services-blog/accelerate-labelling-with-gpt-models-in-language-cognitive/ba-p/3769264

 