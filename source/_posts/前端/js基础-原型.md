---
title: js基础-原型
abbrlink: c096
date: 2022-07-26 17:27:45
tags:
  - 前端
  - js基础
  - 原型
---
**只是这一生冗长，我再难与你相见，难免哽咽**
<!--more-->
- 原型定义

  > **原型是function对象的一个属性，它定义了构造函数造出对象的公共祖先。**  
  > **通过该构造函数产生的对象，可以继承该原型的属性和方法。原型也是对象。**

- 查看原型

  隐式属性: `__proto__`

- 查看对象的构造函数

  `constructor`

- 访问一个属性，如果对象中没有，则去原型中找

  ```
  function Person(){}
  Person.prototype    ->  原型
  new.Person.__proto__    ->  原型
  ```

  

  创建对象隐式调用了

  ```
  var this = {__proto__:Person.prototype}
  ```

  

- 原型上有两个默认的属性
  - constructor 构造函数
  - `__proto__ `原型的原型

- Object.prototype是最终原型
  - Object 是构造函数
  - Object.prototype 是一个对象

- 对象.方法()

  方法里面的this指向调用对象

- Object.create() 创建对象

  `var obj = Object.create(原型)`

- 绝大多数对象最终都继承自Object.prototype

  Object.create(null) 创建的对象没有原型

- undefined.toString();null.toString()

  报错，因为undefined和null原型链上没有Object.prototype

- 原型.方法.call(对象)

  > 指定对象调用原型上的方法

- document.write()会隐式的调用toString方法

