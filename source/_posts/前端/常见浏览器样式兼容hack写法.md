---
title: 常见浏览器样式兼容hack写法
tags:
  - 浏览器
  - 前端
abbrlink: 66dc
date: 2022-01-10 15:52:55
---

**我一个人也不会孤独，说得浪漫些，我完全自由**
<!--more-->

- 火狐浏览器hack写法
    
    ```css
    // 火狐浏览器样式兼容
    @-moz-document url-prefix() {
        .vjs-slider-vertical .vjs-volume-level:before {
            left: -0.3em;
    
        }
    
        .video-js .vjs-play-progress::before {
            top: -0.1em;
            font-size: 1em
        }
    }
    ```

- safari浏览器hack写法

    ```css
    //safari浏览器样式兼容
    @media not all and (min-resolution:.001dpcm) {
        @supports (-webkit-appearance:none) {
    
            .vjs-slider-vertical .vjs-volume-level:before {
                left: -0.4em;
            }
        }
    }
    ```

