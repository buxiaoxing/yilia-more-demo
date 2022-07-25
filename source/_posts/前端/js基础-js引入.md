---
title: js基础-js引入
date: 2022-07-25 15:17:57
tags:
  - js
  - 前端
---
**穷且益坚，不坠青云之志；老当益壮，宁移白首之心**
<!--more-->
1. 内部引入

   ```html
   <script>
   	js代码
   </script>	
   ```

   

2. 外部引入

   ```html
   <script src="js文件路径"></script>
   ```

   

- script标签的位置
  - 语法而言script>标签可以放在head下面，也可以放在body下面
  - 就效率而言，推荐script标签放在body最后  
    **注意：要获取html中的dom元素，script必须放在该dom元素的后面(页面按顺序加载，或者代码在页面加载完后执行)**
- `defer` 和 `async`
  - 同：都是异步加载 js 文件
  - 异：
    - `async`：没有执行顺序，谁先下载完就先执行谁，并停止页面的渲染
    - `defer`：有执行顺序，下载完成后也要等到页面渲染完成才执行
