---
title: node-sass的安装
date: 2021-08-06 09:16:22
tags:
    - node
    - npm
description: node-sass安装报错
---

> node-sass 我从来没有见过这么难安装的模块，网上一搜答案很多，大部分都是给 npm 设置镜像就可以解决，但我 npm 试了很多设置镜像的方法，最后还是会报错，设置镜像方法具体如下

- 将所有依赖设置会淘宝镜像

  `npm config set registry https://registry.npm.taobao.org/`

- 对当前安装依赖设置拉取地址

  `npm install node-sass --sass-binary-site=https://npm.taobao.org/mirrors/node-sass`

- `npm config` 设置

  `npm config set sass_binary_site https://npm.taobao.org/mirrors/node-sass`

- 项目目录新建 `.npmrc` 文件

最后还是通过 `yarn` 安装成功的，添加了 `.yarnrc` 文件

```
registry="https://registry.npm.taobao.org"

sass_binary_site="https://npm.taobao.org/mirrors/node-sass/"
phantomjs_cdnurl="http://cnpmjs.org/downloads"
electron_mirror="https://npm.taobao.org/mirrors/electron/"
sqlite3_binary_host_mirror="https://foxgis.oss-cn-shanghai.aliyuncs.com/"
profiler_binary_host_mirror="https://npm.taobao.org/mirrors/node-inspector/"
chromedriver_cdnurl="https://cdn.npm.taobao.org/dist/chromedriver"

```

具体的安装

1. `npm i yarn -g`
2. `yarn add node-sass@version`