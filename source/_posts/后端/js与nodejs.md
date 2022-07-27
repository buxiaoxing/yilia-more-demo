---
title: js与nodejs
tags:
  - js
  - 后端
  - nodejs
abbrlink: ce0e
date: 2022-07-25 14:15:40
---
**歧视者总是躲在阴暗角落拉帮结派，却终见不得光**
<!--more-->
### 浏览器js工作原理

- 浏览器中js组成部分![image-20220713110410531](http://img.buxiaoxing.com/uPic/2022/07/25142020-Au4Rwe-13110412-lYEIQi-image-20220713110410531.png)

- 浏览器js解释引擎

  | 浏览器  | 解释引擎           |
  | ------- | ------------------ |
  | Chrome  | V8                 |
  | Firefox | OdinMonkey(奥丁猴) |
  | Safari  | JsCore             |
  | IE      | Chakra(查克拉)     |

- js怎么操作浏览器api ![image-20220713110306732](http://img.buxiaoxing.com/uPic/2022/07/25142115-h7D0cs-13110308-CLMee2-image-20220713110306732.png)

- 浏览器中js运行环境

  ![image-20220713110839731](http://img.buxiaoxing.com/uPic/2022/07/25142129-hBQvow-13110841-qHjyDS-image-20220713110839731.png)

  - V8引擎负责解析和执行JS代码
  - 内置api是运行环境提供的特殊接口，只能在所属的运行环境中被调用

### Node.js工作原理

> Node.js 是一个基于Chrome V8 引擎的 JS 运行环境

- https://nodejs.org
- Node.js 中的 JS 运行环境 ![image-20220713112207695](http://img.buxiaoxing.com/uPic/2022/07/25142146-88vzfI-13112209-XJKD7y-image-20220713112207695.png)

- Node.js可以做什么

  - 基于express，构建web应用
  - 基于Electron，构建跨平台桌面应用
  - 基于testify，构建 API 接口项目
  - 读写数据库，创建命令行工具辅助开发，etc... 

- Node学习路径
  - JS基础语法+Node.js内置API(fs, path, http等等)+第三方API模块(express, mysql等等)