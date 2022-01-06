---
title: Bom对象
date: 2022-01-06 15:08:24
tags: 
    - js
    - 浏览器
---
- `location` ：当前页面 URL 信息
    <!--more-->
  ```js
  href		//返回或设置当前文档 URL
  search		//返回 URL 中查询字符串部分，即'?'后面的部分
  hash		//返回 URL '#'后的部分
  host		//返回 URL 域名部分，例如"www.baidu.com"
  hostname	//返回 URL 主域名部分，例如"baidu.com"
  pathname	//返回 URL 域名后的部分
  port		//返回端口号
  protocal	//返回 URL 协议部分，例如 Http: Https:
  assign		//返回当前文档 URL
  replace()	//设置当前文档 URL ，并在 history 对象地址列表中移除这个 URL
  reload()	//重载当前页面
  ```

  

- history` ：该对象保存了浏览器的历史记录

  ```js
  go()		//前进或后退的页面数，history.go(num) 
  back()		//后退一次
  forward()	//前进一次
  ```

    ![image-20201020031027453](https://gitee.com/buxiaoxing/image-bed/raw/master/img/20201020111030.png)

- `navigator` ：对象表示浏览器信息

  ```js
  appName			//浏览器名称
  appVersion		//浏览器版本
  language		//浏览器设置语言
  platform		//操作系统类型
  userAgent		//返回用户代理头的字符串表示（就是包括浏览器版本信息的字符串）
  cookieEnabled	//返回浏览器是否支持 cookie
  ```

    ![image-20201020031103645](https://gitee.com/buxiaoxing/image-bed/raw/master/img/20201020111106.png)

- `window` ：不但可以充当全局作用域，还可以表示浏览器窗口

  ```js
  innerWidth		//获取浏览器窗口的内部宽度（去掉菜单栏、工具栏、边框等占位元素）
  innerHeight		//高度
  ```

- `screen`: 对象表示屏幕信息

  ```js
  width		//屏幕宽度，以像素为单位
  height		//屏幕高度，以像素为单位
  colorDepth	//返回颜色位数，如8、16、24
  ```


