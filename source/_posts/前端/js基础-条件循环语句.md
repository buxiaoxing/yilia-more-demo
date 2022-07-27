---
title: js基础-条件循环语句
abbrlink: 9bb8
date: 2022-07-26 16:35:53
tags:
  - 前端
  - js基础
---
**迎面走来一个很像你的人，我期待是你，又害怕是你，在看清不是你之后，庆幸不是你，又遗憾不是你**
<!--more-->
- 条件语句

  if/else

  ```
  if(条件1){
      满足条件执行的语句
  }else if(条件2){
      满足条件2执行的语句
  }else{
      上面条件都不满足才会执行的语句
  }
  ```

  

  **else if 条件互斥时才能使用**

  switch

  ```
  switch(value){
  		case 1:
  			语句1;
  			break;
  		case 2:
  			语句2;
  			break;
  		case 3:
  			语句3;
  			break;
  		default:
  			都不满足输出的语句;
  			break;
  	}
  ```

  

- 循环
  - for

    ```
    for(1;2;3){
    		循环语句
    }
    for循环执行顺序
    	先执行一遍1;
    	判断2	执行语句
    	执行3
    	判断2	执行语句
    	执行3
    	....
    	2为false时终止程序
    ```

    

  - while

    ```
        while(条件){
    		循环语句
    	}
    	
    	do{
    		循环语句
    	}while(条件)
    ```

    

  - break,continue  

    - break:跳出循环(多个循环，跳出最近的循环)
    - continue:跳出本次循环，不执行后面的语句，直接开始下一次循环
