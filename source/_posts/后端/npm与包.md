---
title: npm与包
toc: true
tags:
  - 前端
  - 后端
  - npm
  - nodejs
abbrlink: c377
date: 2022-07-25 14:36:59
---
**用你的生活来定义浪漫，不要用浪漫来填充它**
<!--more-->
#### 概述

- 什么是包

  ![image-20220714175059163](http://img.buxiaoxing.com/uPic/2022/07/25143830-ublowa-14175100-Kvq5Jg-image-20220714175059163.png)

- 包的来源

  ![image-20220714175153137](http://img.buxiaoxing.com/uPic/2022/07/25143842-W8sKr2-14175154-MrSpan-image-20220714175153137.png)

-  为什么需要包

  ![image-20220714175318444](/Users/peter/img-bed/25143956-ezIctp-14175319-tarm8J-image-20220714175318444.png)

- 在哪里下载包

  ![image-20220714175606266](http://img.buxiaoxing.com/uPic/2022/07/25144008-5lDlbK-14175607-JiWcHc-image-20220714175606266.png)



- npm 初次装包后多了那些文件

  ![image-20220715102504900](http://img.buxiaoxing.com/uPic/2022/07/25144030-zeljfl-15102506-reE53v-image-20220715102504900.png)

- 安装指定版本包

  ![image-20220715102753161](http://img.buxiaoxing.com/uPic/2022/07/25144040-lEqREz-15102754-bldc8i-image-20220715102753161.png)

- 包的语义化版本规范

  ![image-20220715103015133](http://img.buxiaoxing.com/uPic/2022/07/25144049-lv0BEL-15103016-NOz6gM-image-20220715103015133.png)

- 包管理配置文件

  ![image-20220715103132932](http://img.buxiaoxing.com/uPic/2022/07/25144059-BJJjNL-15103134-ZEvYYx-image-20220715103132932.png)

- 快速创建package.json

  ![image-20220715103551857](http://img.buxiaoxing.com/uPic/2022/07/25144112-yo9woy-25144107-uD0dVC-15103553-lwhXIa-image-20220715103551857.png)

- 卸载包

  ![image-20220715104400938](http://img.buxiaoxing.com/uPic/2022/07/25144122-o5B19N-15104402-eC7Wti-image-20220715104400938.png)

- devDependencies

  ![image-20220715104659836](http://img.buxiaoxing.com/uPic/2022/07/25144227-QbuXZU-15104701-2GSoJs-image-20220715104659836.png)

  - 可以在npm看安装示例，来确定安装到哪个节点中

- 淘宝NPM镜像服务器

  ![image-20220715105128257](http://img.buxiaoxing.com/uPic/2022/07/25144237-7pBYZu-15105129-Dv4TpC-image-20220715105128257.png)

- 切换npm下包镜像源

  ![image-20220715105401888](http://img.buxiaoxing.com/uPic/2022/07/25144241-CVf3N9-15105403-sMZofM-image-20220715105401888.png)

- 全局包

  ![image-20220715110240414](http://img.buxiaoxing.com/uPic/2022/07/25144247-b0NIyc-15110242-mbyNqa-image-20220715110240414.png)

- I5ting-doc

  ![image-20220715110832034](http://img.buxiaoxing.com/uPic/2022/07/25144259-QhUtGu-15110833-59fSVb-image-20220715110832034.png)

- 规范的包结构

  ![image-20220715111128960](http://img.buxiaoxing.com/uPic/2022/07/25144304-v0VAuK-25144250-E6iAyQ-15111130-wHNPAv-image-20220715111128960.png)


#### 开发自己的包

- 初始化包结构

  ![image-20220715113336159](http://img.buxiaoxing.com/uPic/2022/07/25144309-r2ZcnT-15113338-yXK9rj-image-20220715113336159.png)

- 初始化package.json

  ![image-20220715113215104](http://img.buxiaoxing.com/uPic/2022/07/25144314-vOA81x-15113216-l23hl1-image-20220715113215104.png)

- 登陆npm账号

  ![image-20220715145818024](http://img.buxiaoxing.com/uPic/2022/07/25144320-JBkDll-15145819-EKPc47-image-20220715145818024.png)

- 把包发布到npm上

  ![image-20220715150056995](http://img.buxiaoxing.com/uPic/2022/07/25144345-FiwfyH-15150058-8mswqC-image-20220715150056995.png)

- 删除已发布的包

  ![image-20220715150246910](http://img.buxiaoxing.com/uPic/2022/07/25144349-MoEu1L-15150248-9Kp3T1-image-20220715150246910.png)

#### 模块加载机制

- 优先从缓存中加载

  ![image-20220715151102266](http://img.buxiaoxing.com/uPic/2022/07/25144355-41D8NB-15151104-Wa5pWS-image-20220715151102266.png)

- 内置模块加载机制

  ![image-20220715151202220](http://img.buxiaoxing.com/uPic/2022/07/25144400-nlilEm-15151203-qJXgpm-image-20220715151202220.png)

- 自定义模块加载机制

  ![image-20220715151655183](http://img.buxiaoxing.com/uPic/2022/07/25144404-A0WMnL-15151656-juvJOJ-image-20220715151655183.png)

- 第三方模块的加载机制

  ![image-20220715151902920](http://img.buxiaoxing.com/uPic/2022/07/25144412-cMNSlt-15151906-pFhHdz-image-20220715151902920.png)

- 目录作为路径加载模块

  ![image-20220715152214950](http://img.buxiaoxing.com/uPic/2022/07/25144418-00dAZX-15152216-O4nQiE-image-20220715152214950.png)

#### npm 常用命令