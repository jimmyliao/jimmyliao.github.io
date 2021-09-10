---
title: "Daily fitness log with Obsidian"

date: 2021-09-10T22:00:28+08:00

description: "Daily fitness log with Obsidian"

featured: true

draft: false

toc: false

shareImage: "https://avatars.githubusercontent.com/u/65011256?s=200&v=4"

codeMaxLines: 10

codeLineNumbers: false

figurePositionShow: true

categories:

- Obsidian
- Tracker
- Fitness

tags:

- Obsidian
- Tracker
- Fitness
---

**看看用這種方式記錄的習慣，能維持多久**

<!--more-->


大多數的 Obsidian 用法都是用來當做 PKM, 還在慢慢把之前散落各地的筆記統整回自己可以備份的 Vault, 今天就來介紹另一種用法：用來當做個人身體指數的記錄。

最近睡眠週期相當混亂，頭痛加上眼壓高造成的眼周圍疼痛也快一個禮拜。前兩天在與同事開會時，開始頭昏冒冷汗，習慣性的看一下手錶 (Garmin Fenix 5s)，心率還好 (66)，但是就是一直冒汗，開完會之後覺得還是量一下血壓好了： 149/100 差點沒嚇暈，只能乖乖請假躺著先補眠，然後這兩天調整一下床、燈光、冷氣等等的外在因素，今天總算是恢復不少。

前兩週可能也是剛開始研究 Obsidian 記錄體重，想說 5-8 月體重也上升不少，才開始先手動記錄，看來加入監控血壓也是必要。

好，目前透過 Obsidian 跟 [Tracker plugin](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/WeightTracker.md)，可以達到以上身體數值記錄跟監控目的了。

### 體重
![](/images/2021-09-10-weight.png)


### 血壓
![](/images/2021-09-10-blood.png)


首先先確定 Obsidian 關閉 Safe mode，透過 Community plugin 安裝 Tracker plugin。然後根據 Examples\diary 裡面[範例](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/diary/2021-01-01.md) 看一下 Blood 相關的 logging，我的紀錄方式是:

```
---
tags: blood
bp:
    systolic: 149
    diastolic: 100
heart: 69
---

```

圖表的部份:

```
searchType: frontmatter
searchTarget: bp.systolic, bp.diastolic
datasetName: systolic, diastolic
folder: log/blood
startDate: 2021-09-03
endDate: 2021-09-10
line:
    title: Blood Pressures
    yAxisLabel: Systolic, Diastolic
    yAxisUnit: mmHg
    yMin: 110, 80
    yMax: 160, 120
    yAxisLocation: left, right
    yAxisColor: yellow, green
    yAxisLabelColor: yellow, green
    lineColor: yellow, green
    showLegend: true
    legendPosition: right
```

至少今天數值看起來還算安心，也該來早點上床睡覺了。
