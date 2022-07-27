---
title: 免费的ssl证书
tags:
  - 后端
  - SSL
  - https
abbrlink: b320
date: 2022-07-25 17:01:24
---

**天生我材必有用，千金散尽还复来**

<!--more-->

- 证书购买

  使用的是阿里云的SSL证书服务，具体参照下面的教程
  [阿里云ssl免费证书获取](https://developer.aliyun.com/article/875508?spm=5176.21213303.J_6704733920.15.1b1753c9yTaqcs&scm=20140722.S_community%40%40%E6%96%87%E7%AB%A0%40%40875508._.ID_community%40%40%E6%96%87%E7%AB%A0%40%40875508-RL_ssl%E5%85%8D%E8%B4%B9%E8%AF%81%E4%B9%A6-LOC_main-OR_ser-V_2-P0_3)

- 我申请证书的主要是因为Chrome无法访问到我在七牛云上配置的图库，导致博客内的图片无法加载，其中的主要原因就是Chrome版本81开始对混合内容进行警告，83开始阻止混合内容的加载和下载，

  简单说就是网站用的https访问，图片却是使用http加载的。于是这里Chrome会做一件事：自动将http加载的数据升格成https进行加载，但是我们知道如果没有配置证书，使用https是没法加载图片的。于是出现了Console中一堆的红色报错`Failed to load resource: net::ERR_CERT_COMMON_NAME_INVALI`,即`资源加载失败，证书错误`。

- 证书拿到后将证书下载下来

   <img src="https://img.buxiaoxing.com/uPic/2022/07/25171312-AipKS6-image-20220725171310937.png" alt="image-20220725171310937" style="zoom: 33%;" />

- 其中包含两个文件

   ![image-20220725171406704](http://img.buxiaoxing.com/uPic/2022/07/25171408-CL1ZlZ-image-20220725171406704.png)

- 然后上传到平台上就行，我这边使用的是七牛云，其他平台应该也是大同小异

  ![image-20220725171518574](http://img.buxiaoxing.com/uPic/2022/07/25171520-AVB0Ul-image-20220725171518574.png)

- 备注名随便填，将下载的两个文件的内容分别填入
  - *.pem-->证书内容
  - *.key--->证书密钥
- 然后部署，托管就行了
