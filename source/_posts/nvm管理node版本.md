---
title: nvm管理node版本
date: 2022-01-06 15:48:18
tags:
    - node
    - 前端
description: nvm管理node版本
keyword: nvm node版本
---

> nvm 是一个node版本的管理工具，可以随意切换node版本
<!--more-->
1. 先将本地的nodejs卸载

   > 控制面板卸载后删除nodejs目录下的所有文件

2. 安装 `nvm`

   https://github.com/coreybutler/nvm-windows/releases

   下载安装包后安装，需要指定nvm地址和nodejs地址

3. `nvm v`

   检测是否安装成功

4. `nvm ls available`

   查看所有可用nodejs版本号

5. `nvm install version`

   安装指定版本nodejs

6. `nvm ls`

   查看已安装的node版本

7. `nvm use version`

   切换node版本