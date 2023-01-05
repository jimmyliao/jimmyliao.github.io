---
title: "Azure 的五十個小劇場...之 Kusto.Explorer: Desktop Application for Azure Data Explorer/ADX"
date: 2023-01-05T02:18:36+08:00
description: "Azure 的五十個小劇場...之 Kusto.Explorer: Desktop Application for Azure Data Explorer/ADX"
featured: false
draft: false
toc: false
shareImage: "/images/2023/2023-01/2023-01-05/2023-01-05-adx-01.png"
thumbnail: "/images/2023/2023-01/2023-01-05/2023-01-05-adx-01.png"
codeMaxLines: 10
codeLineNumbers: false

# Override global value for showing the figure label.
figurePositionShow: false
categories:
  - Windows
tags:
  - Windows
---

According to [previous post](https://jimmyliao.net/post/2022-12-23-kusto-detective-agency/), you can create a free adx/kusto cluster on https://dataexplorer.azure.com/publicfreecluster. Also, the [online ADX explorer](https://dataexplorer.azure.com) is good for beginner to start. 

However the experimental KQL syntax only exists on your browser cache, cannot sharable, visualize, or versioning. I would like to introduce this desktop application to empower the data engineering performance.


<!--more-->

1. Reference from [online doc](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/tools/kusto-explorer), Download and install the Kusto.Explorer tool from:

    https://aka.ms/ke (CDN location)

    https://aka.ms/ke-mirror (Non-CDN location)

2. The normal KQL operation.

  ![](/images/2023/2023-01/2023-01-05/2023-01-05-adx-02.png)

3. There is `Analize Query` button.

  ![](/images/2023/2023-01/2023-01-05/2023-01-05-adx-03.png)

4. Can visualize the Query Plan, with Statistics. :-)

  ![](/images/2023/2023-01/2023-01-05/2023-01-05-adx-04.png)


Reference: 

- https://learn.microsoft.com/en-us/azure/data-explorer/kusto/tools/kusto-explorer

- https://xhinker.medium.com/understand-kusto-inside-out-and-why-kusto-is-so-fast-54697e6648d7





