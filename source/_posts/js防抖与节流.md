---
title: js防抖与节流
date: 2022-01-10 16:13:09
tags:
    - 性能
    - js
    - 前端
---
- 防抖
<!--more-->
  > 触发高频事件后n秒内函数只会执行一次，如果n秒内高频事件再次被触发，则重新计算时间

- 节流

  > 高频事件触发，但在n秒内只会执行一次，所以节流会稀释函数的执行频率

  ```js
  // 节流
  function throttle(fn, delay) {
      let valid = true
      return function () {
          if (!valid) {
              return false
          }
          valid = false
          setTimeout(() => {
              fn()
              valid = true
          }, delay)
      }
  }
  // 防抖
  function debounce(fn, delay) {
      let timer = null
      return function () {
          if (timer) {
              clearTimeout(timer)
          }
          timer = setTimeout(fn, delay)
      }
  }
  
  function showTop() {
      var scrollTop = document.body.scrollTop || document.documentElement.scrollTop
      console.log("滚动条位置" + scrollTop)
  }
  window.onscroll = throttle(showTop, 1000)
  ```

