---
title: js基础-call和apply
date: 2022-07-27 01:01:02
tags:
---
**少年心动，是仲夏夜的荒原，割不完，烧不尽，长风一吹，野草就连了天**
<!--more-->
- call apply的作用

  改变this指向

- call
  - 每个函数执行时都会都会调用call  
    `test();        ->      test.call();`

  - call里面第一参数是方法this的指向，后面的参数是方法的参数

    ```
    function Person(name, age){
        this.name = name;
        this.age = age;
    }
    var obj = {}
    Person.call(obj,'zs',24)
    ```

- call 与 apply 的区别

  apply的实参列表必须是数组  
  `Person.apply(obj,['zs',24])`

