---
title: "Azure 的五十個小劇場...之 用 Colab 透過 Azure ML SDK (v1) submit job"
date: 2022-11-29T00:10:36+08:00
description: "看看怎麼使用 Azure ML ScriptRunConfig Submit Job"
featured: true
draft: false
toc: false
# shareImage: "/images/fb_share.jpg"
thumbnail: "https://code.benco.io/icon-collection/other/azure-ml.svg"
# shareImage: "https://branditechture.agency/brand-logos/wp-content/uploads/wpdm-cache/Azure-Machine-Learning-Service-900x0.png"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: true
categories:
  - Azure
tags:
  - Azure
---

底下透過 SDK v1 的 ScriptRunConfig，來 Submit 一個 training job。另外也透過 Colab 的環境展示一下快速整合 AML SDK。

<!--more-->


準備動作：
- Azure Subscription ID
- AML Workspace name
- AML Resource group name

過程會需要透過 Azure Device login 取得 credential。

Jupyter Notebook [連結](https://github.com/jimmyliao/amlworkshop/blob/main/lab01/azureml-sdk-v2.ipynb)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jimmyliao/amlworkshop/blob/main/lab01/azureml-sdk-v2.ipynb)

