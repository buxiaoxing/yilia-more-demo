---
title: js基础-错误
tags:
  - js
  - 前端基础
abbrlink: e4b
date: 2022-07-25 15:25:40
---
**我知道你总有一天会想我**
<!--more-->
- 错误分两种
  - 低级错误(语法解析错误)  
    程序在执行前会扫面所有代码，看是否有语法错误，如果有语法错误，代码一行也不会执行
    一个代码块的语法错误不会影响另一个代码块的运行，代码块：一个script标签，不同代码块能互相应用变量
  - 逻辑错误  
    执行到该行报错，后面的代码不会执行
  
- `Error` 实例对象

  ```js
  var err = new Error("出错了")
  //这个对象有3个属性
  //1. message	错误提示信息
  //2. name		错误名称
  //3. stack		错误的堆栈
  ```

  - 原生错误类型

    - `SyntaxError`	

      语法错误

    - `ReferenceError`     

      引用不存在变量

    - `RangeError`

      值超出有效范围，数组长度，Number值的范围，函数堆栈

    - `TypeError`

      类型错误

    - `URIError`

      URI相关函数的参数不正确

    - `EvalError`

      `eval` 函数没有被正确的执行

  - 自定义错误

    继承 Error对象

    ```js
    myError.prototype = new Error()
    ```

  - `throw`

    手动中断程序执行，抛出一个错误

    ```js
    throw new Error('出错了')
    ```

  - `try……catch`

    出现错误，对错误进行处理，程序不会中断

  - `finally`

    可以在 `try……catch` 后添加 `finally` 代码块，不管是否出现错误，最后都会执行的语句

