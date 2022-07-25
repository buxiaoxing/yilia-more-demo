---
title: nodejs中的模块化
date: 2022-07-25 14:29:34
tags:
  - 后端
  - nodejs
---
**少年是元气淋漓的颓唐和春心荡漾的忧伤**
<!--more-->
### 什么是模块化

指解决一个复杂问题时，自顶向下逐层把系统划分成若干模块的过程。对于整个系统来说，模块是可组合，分解和更换的单元

- 编程中的模块化

  ![image-20220714142227229](http://img.buxiaoxing.com/uPic/2022/07/25142520-005mkX-14142228-qZxZoL-image-20220714142227229.png)

- 模块化规范

  ![image-20220714142145758](http://img.buxiaoxing.com/uPic/2022/07/25142606-usBX5K-14142147-YgHPPE-image-20220714142145758.png)

### Node.js中的模块化

#### Node.js中模块的分类

![image-20220714150807741](http://img.buxiaoxing.com/uPic/2022/07/25142625-6fnHeA-14150809-7NEHxc-image-20220714150807741.png)

#### 加载模块

- 使用 `require()`

  ![image-20220714150956206](http://img.buxiaoxing.com/uPic/2022/07/25142640-GTNeQe-14150957-nB1UQZ-image-20220714150956206.png)

  - 加载内置模块和第三方模块都直接写模块名即可
  - 加载自定义模块需要写路径
  - 加载其他模块时，会执行被加载模块中的代码
  - 可以省略 `.js` 后缀名

#### 模块作用域

- 什么是模块作用域

  ![image-20220714165907279](http://img.buxiaoxing.com/uPic/2022/07/25142657-K0RwRA-14165909-AN9Mtv-image-20220714165907279.png)

- 模块作用域的好处

  ![image-20220714170037806](http://img.buxiaoxing.com/uPic/2022/07/25142718-atalhT-14170045-a5gEgO-image-20220714170037806.png)

  

#### 向外共享

![image-20220714170743884](http://img.buxiaoxing.com/uPic/2022/07/25142744-lUBkBc-14170745-85BzhQ-image-20220714170743884.png)

![image-20220714171250096](http://img.buxiaoxing.com/uPic/2022/07/25142758-fp7I9d-14171251-ynNxgo-image-20220714171250096.png)

![image-20220714172207506](http://img.buxiaoxing.com/uPic/2022/07/25142810-qkeKR3-14172209-hIFFKc-image-20220714172207506.png)

![image-20220714172712318](http://img.buxiaoxing.com/uPic/2022/07/25142823-Zf0nX0-14172714-u9dBc8-image-20220714172712318.png)

- 直接往对象上挂载属性是没有问题的
- 如果直接给对象赋值，exports 就无法导出了，因为exports 的指向改变了，不再指向module.exports指向的对象了
- 为了防止混乱，尽量只使用module.exports

- Node.js 的模块化规范

  ![image-20220714174836121](http://img.buxiaoxing.com/uPic/2022/07/25142845-pcCor2-14174837-vFKtap-image-20220714174836121.png)

