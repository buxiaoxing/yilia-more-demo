---
title: hexo创建博客并部署到github上
date: 2022-01-08 15:13:25
tags:
    - hexo
    - yilia
description: hexo创建博客并部署到github上
keyword: hexo yilia
---

##### 准备环境
- 下载安装nodejs  
cmd中输入node -v出现版本号则安装成功
<!--more-->
- 下载安装git，并配置环境变量
- npm淘宝镜像包管理器  
`npm install -g cnpm --registry=https://registry.npm.taobao.org`
##### 安装hexo
`cnpm install -g -hexo-cli`  

- 验证  
`hexo -v`
##### 搭建博客
- 创建一个文件夹，所有博客文件都会放在这个文件夹中，出错了，就删掉这个文件夹重来即可
- 在该目录下运行cmd
- 初始化博客  
`hexo init`
- 启动博客  
`hexo s`  
默认端口为4000
- 创建新的博客  
`hexo n "filename"`  
也可以直接在source文件夹下直接创建md文件

##### 部署到github
- github上创建一个仓库

- 安装git部署插件  
  `cnpm install --save hexo-deployer-git`

- 修改_config.yml文件  
  文件最底部

  ```
  deploy:
    type: git
    repo: https://github.com/buxiaoxing/buxiaoxing.github.io.git
    branch: master
  ```

- 部署  
  `hexo d`  
  输入github用户名和密码

- 输入仓库的地址就能访问

##### 修改主题
- 添加主题到themes文件夹下
  - 可以克隆github上的主题  
  `git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia`
  
- 修改_config.yaml文件  
  `theme: yilia`

- 清理缓存，重新生成，预览，部署

  ```
  hexo clean
  hexo g
  hexo s
  hexo d
  ```

##### hexo常用命令
- 初始化  
`hexo init`
- 本地启动服务器  
`hexo s`
- 新建文件  
`hexo n`
- 清理缓存  
`hexo clean`
- 修改后重新生成  
`hexo g`



##### 可能会遇到的问题

- `yilia` 主题分页乱码

  > hexo 版本过高，推荐 3.9.0

- `hexo g` 生成 `index.html`  文件为空

  > node 版本过低，更新node，推荐使用 nvm 管理 node 版本