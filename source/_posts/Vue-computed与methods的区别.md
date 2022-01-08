---
title: Vue computed与methods的区别
date: 2022-01-08 15:22:51
tags:
    - vue
---
请看下面代码
<!--more-->
```html
<div id="app">
    <p>{{getFullName()}}</p>
    <p>{{fullName}}</p>
</div>

<script src="js/vue.js"></script>
<script>
    let vue = new Vue({
        el: '#app',
        data: {
            firstName: '张',
            lastName: '三'
        },
        methods: {
            getFullName(){
                return this.firstName+" "+this.lastName
            }
        },
        computed: {
            fullName(){
                return this.firstName+" "+this.lastName
            }
        }
    })
```


```html
<div id="app">
    <p>{{getFullName()}}</p>
    <p>{{fullName}}</p>
    <p>{{getFullName()}}</p>
    <p>{{fullName}}</p>
    <p>{{getFullName()}}</p>
    <p>{{fullName}}</p>
    <p>{{getFullName()}}</p>
    <p>{{fullName}}</p>
</div>

<script src="js/vue.js"></script>
<script>
    let vue = new Vue({
        el: '#app',
        data: {
            firstName: '张',
            lastName: '三'
        },
        methods: {
            getFullName(){
                console.log('methods')
                return this.firstName+" "+this.lastName
            }
        },
        computed: {
            fullName(){
                console.log('computed')
                return this.firstName+" "+this.lastName
            }
        }
    })
</script>
```

![](https://img2020.cnblogs.com/blog/1747833/202008/1747833-20200809174442006-1164143714.png)

1. 从上面例子中很容易看出，虽然两者都能通过双括号引用，但 methods 需要加括号。

2. 当多次调用时，computed 有缓存，如果没有改变，多次引用只会调用一次

   而 methods 没有缓存，每次引用都会调用一次

   所有就对属性计算方面来看， computed 优于 methods