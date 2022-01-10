---
title: flex布局中between的布局问题
date: 2022-01-10 15:57:07
tags:
    - flex
    - css
---
> 当出现多行数量不同时，显示问题很大

<!--more-->
grid 布局可以很好解决该问题

```css
.wrap {
    width: 100px;
    display: grid;
    grid-template-columns: repeat(3, 20px);
    /* grid-column-gap: 20px; */
    row-gap: 20px;
    /* justify-items: start center end; */
    justify-content: space-between;
    border: 1px solid #eee;
}

.wrap>div {
    width: 20px;
    height: 20px;
    background: red;
    text-align: center;
    line-height: 20px;
}
```

 ![image-20211026143939097](https://gitee.com/buxiaoxing/image-bed/raw/master/img/image-20211026143939097.png)

