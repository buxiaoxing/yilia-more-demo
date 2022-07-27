---
title: js基础-typeof与类型转化
abbrlink: e2f7
date: 2022-07-26 16:37:50
tags:
   - 前端
   - js基础
   - 类型
---
**是谁多事种了芭蕉，风也萧萧，雨也萧萧。是君心绪太无聊，种了芭蕉，又怨芭蕉**
<!--more-->
1. typeof(数据)

   - 返回数据类型  
     `number string object boolean undefined function`

   - typeof(未定义的变量，定义未赋值的变量)  ->  undefined

   - 返回的字符串

2. Number(数据) -> 将数据转化为number类型

   ```
       Number(true)	->	1
       Number(null)	->	0
       Number(undefined)	-> NaN
       Number("a")		->	NaN
       Number("11a")	->	NaN
   ```

   

3. parseInt(数据,[进制]) -> 将数据化为整数

   ```
       parseInt(true)	->	NaN
       parseInt(null)	->	NaN
       parseInt(undefined)	-> NaN
       parseInt("a")		->	NaN
       parseInt("11a")	->	11			//从不包括小数点数字位看到非数字位
   ```

   

4. parseFloat(数据)    ->  将数据化为浮点数

   > 从包括小数点的数字位看到非数字位

5. String(数据)  - > 将数据化为字符串类型

6. Boolean(数据)

7. 数据.toString([进制])

   将数据转化为字符串类型(undefined和null不能使用，因为原型上没有Object.prototype，String()都能适用)

   > parseInt()		目标进制 -> 十进制
   > toString()		十进制   -> 目标进制

8. 隐式类型转化

   ```
           i.isNaN(数据)	
   		(1).Number(数据)
   		(2).和NaN比对
   		
   	ii.a++	+a	-a ++a a-- --a
   		(1).Number(a)
   		(2).a++
   	iii.- * / %
   		(1).Number()
   		(2).运算
   	iiii.	+
   		计算到字符串时字符串链接
   		boolean+number = Number(boolean)+number
   	|| && !
   		自动转化为boolean值
   	== !=
   		自动类型转化	
   	> < 	a.字符串与number比，字符串->number，比较值
   			b.数字与boolean比较，boolean-->number
   			c.字符串与字符串比较第一位ASCII值
   			d.其他比较都返回false
   	
   	NaN == NaN	->	false
   			NaN与任何值比较都返回false
   ```

   

9. 不发生类型转化

   ```
       ===         !== 
   ```

