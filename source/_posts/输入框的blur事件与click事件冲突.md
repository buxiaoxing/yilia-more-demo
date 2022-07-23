---
title: 输入框的blur事件与click事件冲突
date: 2022-01-10 16:05:35
tags:
    - js
    - 前端
---
> 原因：blur 事件在 click 之前触发

<!--more-->
**solution**
- 延时

- 可以在mousedown上阻止blur事件发生，然后再在click事件上触发blur事件
