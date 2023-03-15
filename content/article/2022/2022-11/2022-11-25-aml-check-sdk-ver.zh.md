---
title: "Azure 的五十個小劇場...之 Azure ML SDK 版本檢查"
date: 2022-11-25T08:10:36+08:00
description: "取個自己記得住的連載標題好難 >_<"
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
tags:
  - Azure
---

Azure ML SDK 兩個版本共存，就寫個檢查版號當作 Azure 學習筆記開頭吧。

<!--more-->


因為要 Demo Azure ML SDK 的環境有 [v1](https://learn.microsoft.com/en-us/azure/machine-learning/v1/introduction) and [v2](https://learn.microsoft.com/en-us/python/api/overview/azure/ai-ml-readme?view=azure-python)，為了快速檢查就先弄個 bash shell 。

```bash
# Install Azure ML SDK v1
# pip install -U azureml-core

# Install Azure ML SDK v2
pip install -U azure-ai-ml

wget https://raw.githubusercontent.com/jimmyliao/amlworkshop/main/util/check_sdk.sh -O ./check_sdk.sh

chmod a+x ./check_sdk.sh

./check_sdk.sh
```

Jupyter Notebook [連結](https://github.com/jimmyliao/amlworkshop/blob/main/lab_checkenv/aml_env_check.ipynb)

