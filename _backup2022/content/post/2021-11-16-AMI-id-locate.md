---
title: "Amazon EC2 AMI Locator for Ubuntu"
date: 2021-11-16T22:10:36+08:00
description: "Amazon EC2 AMI Locator for Ubuntu"
featured: false
draft: false
toc: false
# menu: main
shareImage: "https://assets.ubuntu.com/v1/1be42010-cof_orange_hex.jpg"
featureImage: "https://assets.ubuntu.com/v1/1be42010-cof_orange_hex.jpg"
thumbnail: "https://assets.ubuntu.com/v1/1be42010-cof_orange_hex.jpg"
codeMaxLines: 10
codeLineNumbers: false
figurePositionShow: true
categories:
  - AWS
tags:
  - AWS
---

今天在找對應的 Ubuntu 官方支援 EC2 的 AMI-ID，記錄一下找的方式。

<!--more-->

- 首先, [Ubuntu 官網](https://cloud-images.ubuntu.com/locator/ec2/) 就有提到在各個 region 提供的 AMI，目標是要找到 Ubuntu 20.04 LTS
。 Version 就先選到 `20.04 LTS`，結果出現先筆記一下 AMI: `ami-036d0684fc96830ca`
![](/images/2021-11-16-ami.png)

- 用以上的 AMI 來確定 Ubuntu Cloud Account id:

  ```
  aws ec2 describe-images --region ap-northeast-1 --image-ids ami-036d0684fc96830ca

  {
      "Images": [
          {
              "Architecture": "x86_64",
              "CreationDate": "2021-10-22T00:40:31.000Z",
              "ImageId": "ami-036d0684fc96830ca",
              "ImageLocation": "099720109477/ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20211021",
              "ImageType": "machine",
              "Public": true,
              "OwnerId": "099720109477",
              "PlatformDetails": "Linux/UNIX",
              "UsageOperation": "RunInstances",
              "State": "available",
              "BlockDeviceMappings": [
      ...
  ```

  "OwnerId": "099720109477"

- 接著透過以下方式找最新的前十個

  ```
  aws ec2 describe-images --owners 099720109477 \
	--region ap-northeast-1 --output table \
	--filters "Name=name,Values=*ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server*" \
	--query 'reverse(sort_by(Images,&CreationDate))[:10].[ImageId,Name,CreationDate]'
  ```

  結果:
```
-------------------------------------------------------------------------------------------------------------------------
|                                                    DescribeImages                                                     |
+-----------------------+------------------------------------------------------------------+----------------------------+
|  ami-0b3882952fc4fae89|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20211115  |  2021-11-16T00:17:22.000Z  |
|  ami-036d0684fc96830ca|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20211021  |  2021-10-22T00:40:31.000Z  |
|  ami-0adcb4f170c975f15|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20211015  |  2021-10-16T00:09:34.000Z  |
|  ami-074d4d6a02df638da|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20211001  |  2021-10-01T22:12:45.000Z  |
|  ami-02a56e430b32bc0ba|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20210927  |  2021-09-28T00:25:26.000Z  |
|  ami-09ac3ab1b7a1e9444|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20210907  |  2021-09-08T01:40:47.000Z  |
|  ami-0b75e38f5a56ada82|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20210825  |  2021-08-25T23:54:47.000Z  |
|  ami-025e3bcccb9d8d2b4|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20210820  |  2021-08-21T00:03:37.000Z  |
|  ami-0647fa5c7c07a3385|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20210816  |  2021-08-18T17:08:40.000Z  |
|  ami-0b0ccc06abc611fa0|  ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20210720  |  2021-07-21T13:27:05.000Z  |
+-----------------------+------------------------------------------------------------------+----------------------------+
```


**Enjoy!**

