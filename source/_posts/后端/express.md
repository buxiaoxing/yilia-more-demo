---
title: express
tags:
  - 后端
  - express
  - node
abbrlink: '711'
date: 2022-07-25 14:46:37
---
**关于你的记忆，就像18岁那年的蝉鸣，点燃了整个夏天，却又消无声息的湮灭**
<!--more-->

#### Express简介

- 什么是Express

  ![image-20220715153905228](http://img.buxiaoxing.com/uPic/2022/07/25144904-yeUVyx-15153906-fOAZ89-image-20220715153905228.png)

- 进一步理解Express

  ![image-20220715154020043](http://img.buxiaoxing.com/uPic/2022/07/25144913-DXyLCz-15154021-53Uxjc-image-20220715154020043.png)

- Express能做什么

  ![image-20220715154116658](http://img.buxiaoxing.com/uPic/2022/07/25144921-K9qaEm-15154118-6EwCqU-image-20220715154116658.png)

#### Express基本使用

- 安装

  ```shell
  npm i express@4.17.1
  ```

- 创建最基本的web服务器

  ![image-20220715154315034](http://img.buxiaoxing.com/uPic/2022/07/25144926-r10y4L-15154316-q2R9GE-image-20220715154315034.png)

- 监听Get请求

  ![image-20220715154928751](http://img.buxiaoxing.com/uPic/2022/07/25144931-xWMURa-15154930-ST8hUV-image-20220715154928751.png)

- 监听Post请求

  ![image-20220715154953068](http://img.buxiaoxing.com/uPic/2022/07/25144939-0P4XEA-15154954-keF3ru-image-20220715154953068.png)

- 把内容响应给客户端

  ![image-20220715155053801](http://img.buxiaoxing.com/uPic/2022/07/25144944-nxMXFr-15155055-miL1B6-image-20220715155053801.png)

- 获取URL中携带的查询参数

  ![image-20220715155450858](http://img.buxiaoxing.com/uPic/2022/07/25144949-QqzMcy-15155452-qbdIcz-image-20220715155450858.png)

- 获取URL中的动态参数

  ![image-20220715155818997](http://img.buxiaoxing.com/uPic/2022/07/25144955-1yhTIH-15155820-2GMNk9-image-20220715155818997.png)

  

#### 托管静态资源

- express.static()

  ![image-20220715160450570](http://img.buxiaoxing.com/uPic/2022/07/15160451-VDoOdD-image-20220715160450570.png)

- 托管多个静态资源目录

  ![image-20220715161255655](http://img.buxiaoxing.com/uPic/2022/07/15161257-0AV1IN-image-20220715161255655.png)

- 挂载路径前缀

  ![image-20220715161444860](http://img.buxiaoxing.com/uPic/2022/07/15161446-UqMsxc-image-20220715161444860.png)

  

#### nodemon

- 为什么使用nodemon

  ![image-20220715161755523](http://img.buxiaoxing.com/uPic/2022/07/15161757-1r2K0Q-image-20220715161755523.png)

- 安装nodemon

  ```shell
  npm i nodemon -g
  ```

- 使用nodemon

  ![image-20220715161938250](http://img.buxiaoxing.com/uPic/2022/07/15161939-XfrMHP-image-20220715161938250.png)

#### express路由

- 路由的概念

  - 生活中的路由

    ![image-20220715162216947](http://img.buxiaoxing.com/uPic/2022/07/15162218-kajbjY-image-20220715162216947.png)

  - Express 中的路由

    ![image-20220715162440325](http://img.buxiaoxing.com/uPic/2022/07/15162441-FeJKHH-image-20220715162440325.png)

    ![image-20220715162454145](http://img.buxiaoxing.com/uPic/2022/07/15162455-sSkY7n-image-20220715162454145.png)

  - 路由的匹配过程

    ![image-20220715162758368](http://img.buxiaoxing.com/uPic/2022/07/15162800-8JhvMZ-image-20220715162758368.png)

  - 模块化路由

    ![image-20220715163054750](http://img.buxiaoxing.com/uPic/2022/07/15163056-qpRMCO-image-20220715163054750.png)

    - 创建路由模块

      ![image-20220715163126892](http://img.buxiaoxing.com/uPic/2022/07/15163134-5z4JDX-image-20220715163126892.png)

    - 注册路由模块

      ![image-20220715163613304](http://img.buxiaoxing.com/uPic/2022/07/15163614-m0PI4n-image-20220715163613304.png)

    - app.use()

      注册全局中间件，这里的router和前面的static都是中间件

    - 为路由模块添加前缀

      ![image-20220715164253908](http://img.buxiaoxing.com/uPic/2022/07/15164255-VRNzpi-image-20220715164253908.png)

#### express中间件

- 什么是中间件

  中间件(Middleware)，特指业务流程的`中间处理环节`

  - 现实中的例子

    ![image-20220715164632920](http://img.buxiaoxing.com/uPic/2022/07/15164634-JaG2C7-image-20220715164632920.png)

- express中间件调用流程

  ![image-20220715164733660](http://img.buxiaoxing.com/uPic/2022/07/15164734-m08cBj-image-20220715164733660.png)

  

- express中间件格式

  ![image-20220715165055802](http://img.buxiaoxing.com/uPic/2022/07/15165057-uP91PS-image-20220715165055802.png)

- next函数作用

  ![image-20220715165221756](http://img.buxiaoxing.com/uPic/2022/07/15165223-jQqpVY-image-20220715165221756.png)

- 定义中间件函数

  ![image-20220715165329865](http://img.buxiaoxing.com/uPic/2022/07/15165330-5GmnpW-image-20220715165329865.png)

- 全局生效的中间件

  ![image-20220715165648380](http://img.buxiaoxing.com/uPic/2022/07/15165649-JM4vki-image-20220715165648380.png)

- 定义全局中间件的简化形式

  ![image-20220715170230804](http://img.buxiaoxing.com/uPic/2022/07/15170232-LzjAnJ-image-20220715170230804.png)

- 中间件的作用

  ![image-20220715170516920](http://img.buxiaoxing.com/uPic/2022/07/15170518-igccsx-image-20220715170516920.png)

- 定义多个全局中间件

  ![image-20220715171023312](http://img.buxiaoxing.com/uPic/2022/07/15171024-yXUMuI-image-20220715171023312.png)

- 局部生效的中间件

  ![image-20220715171356413](http://img.buxiaoxing.com/uPic/2022/07/15171357-dzgFYv-image-20220715171356413.png)

- 定义多个局部中间件

  ![image-20220715171729504](http://img.buxiaoxing.com/uPic/2022/07/15171730-l2qtAH-image-20220715171729504.png)

- 中间件使用的5个注意事项

  ![image-20220718095637386](http://img.buxiaoxing.com/uPic/2022/07/18095638-yUUvdZ-image-20220718095637386.png)

- 中间件的分类

   ![image-20220718095758842](http://img.buxiaoxing.com/uPic/2022/07/18095800-5Vlnen-image-20220718095758842.png)

- 应用级别中间件

  ![image-20220718095842711](http://img.buxiaoxing.com/uPic/2022/07/18095844-jzD0LW-image-20220718095842711.png)

- 路由级别中间件

  ![image-20220718095959079](http://img.buxiaoxing.com/uPic/2022/07/18100000-TQOmLZ-image-20220718095959079.png)

- 错误级别中间件

  ![image-20220718100131119](http://img.buxiaoxing.com/uPic/2022/07/18100132-jpVvat-image-20220718100131119.png)

- express 内置的中间件

  ![image-20220718104840412](http://img.buxiaoxing.com/uPic/2022/07/18104841-R9G5p2-image-20220718104840412.png)

- 第三方中间件

  ![image-20220718112203572](http://img.buxiaoxing.com/uPic/2022/07/18112204-im0lx1-image-20220718112203572.png)

- 自定义中间件

  ![image-20220718112348419](http://img.buxiaoxing.com/uPic/2022/07/18112350-SRpd8U-image-20220718112348419.png)

  ![image-20220718142348344](http://img.buxiaoxing.com/uPic/2022/07/18142349-3pPzHh-image-20220718142348344.png)

  ![image-20220718113130433](http://img.buxiaoxing.com/uPic/2022/07/18113132-bkLCJt-image-20220718113130433.png)

  ![image-20220718113739745](http://img.buxiaoxing.com/uPic/2022/07/18113741-voXkal-image-20220718113739745.png)

  ![image-20220718114039354](http://img.buxiaoxing.com/uPic/2022/07/18114040-CSxyJ1-image-20220718114039354.png)

  ![image-20220718142506904](http://img.buxiaoxing.com/uPic/2022/07/18142508-oq8cvp-image-20220718142506904.png)

  ![image-20220718142919506](http://img.buxiaoxing.com/uPic/2022/07/18142921-K7sMTJ-image-20220718142919506.png)



#### 使用express写接口

- 创建基本的web服务器

- 注册路由模块

- 编写GET请求

  ![image-20220718152440136](http://img.buxiaoxing.com/uPic/2022/07/18152441-H1FXEk-image-20220718152440136.png)

- 编写POST请求

  ![image-20220718153027758](http://img.buxiaoxing.com/uPic/2022/07/18153029-4lH3CM-image-20220718153027758.png)

- CORS跨域共享

  - 接口的跨域问题

    ![image-20220718154333387](http://img.buxiaoxing.com/uPic/2022/07/18154334-RvV4nu-image-20220718154333387.png)

  - 使用cors中间件解决跨域问题

    ![image-20220718154442316](http://img.buxiaoxing.com/uPic/2022/07/18154443-hLk3YD-image-20220718154442316.png)

- Cors

  - 什么是cors

    ![image-20220718154920768](http://img.buxiaoxing.com/uPic/2022/07/18154922-zjIywe-image-20220718154920768.png)

  - cors的注意事项

    ![image-20220718155015799](http://img.buxiaoxing.com/uPic/2022/07/18155017-iKxjAP-image-20220718155015799.png)

  - cors响应头部 Access-Control-Allow-Origin

    ![image-20220718155203821](http://img.buxiaoxing.com/uPic/2022/07/18155205-sRaUcA-image-20220718155203821.png)

    ![image-20220718155241403](http://img.buxiaoxing.com/uPic/2022/07/18155243-2ZvIYF-image-20220718155241403.png)

  - cors响应头部 Access-Control-Allow-Origin

    ![image-20220718155424641](http://img.buxiaoxing.com/uPic/2022/07/18155426-7VBbdE-image-20220718155424641.png)

  - cors响应头部 Access-Control-Allow-Methods

    ![image-20220718155524332](http://img.buxiaoxing.com/uPic/2022/07/18155525-2bJ7nt-image-20220718155524332.png)

  - cors请求分类

    ![image-20220718155625543](http://img.buxiaoxing.com/uPic/2022/07/18155627-wj9pOJ-image-20220718155625543.png)

    - 简单请求

      ![image-20220718155653201](http://img.buxiaoxing.com/uPic/2022/07/18155655-DVhAkr-image-20220718155653201.png)

    - 预检请求

      ![image-20220718155834169](http://img.buxiaoxing.com/uPic/2022/07/18155835-r5MOPO-image-20220718155834169.png)

    - 简单请求与预检请求的区别

      ![image-20220718155922671](http://img.buxiaoxing.com/uPic/2022/07/18155924-C5Pvbw-image-20220718155922671.png)

      ![image-20220718160950587](http://img.buxiaoxing.com/uPic/2022/07/18160952-uDoB9k-image-20220718160950587.png)

- jsonp

  - 概念与特点

    ![image-20220718161121457](http://img.buxiaoxing.com/uPic/2022/07/18161122-xUfIFj-image-20220718161121457.png)

  - 创建jsonp接口注意事项

    ![image-20220718161239658](http://img.buxiaoxing.com/uPic/2022/07/18161240-PCNjFP-image-20220718161239658.png)

  - 实现jsonp接口步骤

    ![image-20220718161419127](http://img.buxiaoxing.com/uPic/2022/07/18161421-gueo9O-image-20220718161419127.png)

  - 在网页中使用jquery发送JSONP请求

    ![image-20220718162216210](http://img.buxiaoxing.com/uPic/2022/07/18162217-4ctX01-image-20220718162216210.png)

