---
title: js基础-数据类型
tags:
  - 前端
  - js基础
  - 类型
abbrlink: 6f0e
date: 2022-07-25 15:22:54
---
**天下万般兵刃，唯有过往伤人最深**
<!--more-->
##### 原始值

- Number  

  var age = 18;
  var money = 100.1;
- Boolean
  ```
  true
  false
  ```
- String  
  ```
  var str1 = 'hello'
  var str2 = "world"
  ```
- undefined  
声明未赋值的变量
- null  
  空值，占位  

- **原始值是存入栈空间里面的(先进后出)**

   <img src="http://img.buxiaoxing.com/uPic/2022/07/25164551-b8zMvc-image-20220725164549846.png" alt="image-20220725164549846" style="zoom: 33%;" />

##### 引用值
```
array
Object
function
...
```

**引用值存入堆里面**
<img src="http://img.buxiaoxing.com/uPic/2022/07/25164519-k4uiNI-image-20220725164518244.png" alt="image-20220725164518244" style="zoom: 33%;" />