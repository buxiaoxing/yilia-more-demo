---
title: css兼容问题
date: 2022-02-04 12:47:55
tags:
    - 浏览器
    - 前端
---
**而浮生若梦，为欢几何**
<!--more-->
- 浏览器兼容问题

  - hack

    1. 火狐浏览器hack写法

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

    2. safari浏览器hack写法

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

  - 样式覆盖

  - css前缀

- 移动端兼容问题

  - `@media`

  - 判断 `pc` 端还是移动端

    1. 
        ```javascript
        /Mobi|Android|iPhone/i.test(navigator.userAgent); //不可靠，userAgent字段可修改
        ```
    2. 
        ```javascript
        const isMobile = navigator.userAgentData.mobile; //safari，Firefox不支持
        ```
    3. 
        ```javascript
        /Android|iPhone|iPad|iPod/i.test(navigator.platform)// 已废弃，但所有浏览器都支持
        ```
    4. 
       ```javascript
       if(window.screen.width<500){
           // 通过屏幕宽度判断
           //移动设备（横屏无法识别）
       }
       ```
    5. 
        ```javascript
        if(typeof window.orientation !== 'undefined'){
            // 当前设备时移动设备（只有移动设备有orientation这个侦测屏幕方向的属性）
        }
        ```
    6. 
        ```javascript
        function isMobile(){
            return ('ontouchstart' in document.documentElement) // 只有移动设备有触摸事件
        }
        ```