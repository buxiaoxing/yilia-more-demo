---
title: 字符串匹配算法--BF
date: 2022-01-08 15:35:03
tags:
    - 算法
---
- BF算法又称暴力算法，非常容易理解，同时效率也很低
- 实现步骤
<!--more-->
(1) 给定子串与主串
(2) 在主串上从头开始选取与子串等长的模式串
(3) 比较模式串与字串，如果不相等，则模式串后移一位
(4) 当模式串移动到某个位置，每个字符都是匹配时，比较结束

- 代码示例
```java
    /**
     * @param s1 主串
     * @param s2 字串
     * @return  成功匹配第一个字符的位置，匹配失败返回 -1
     */
    public static int bF(String s1, String s2){
        char[] arr1 = s1.toCharArray();
        char[] arr2 = s2.toCharArray();
        for(int i=0;i<=arr1.length-arr2.length;i++){
            int pos = i;
            for(int j=0;j<arr2.length;j++){
                if(arr1[pos]!=arr2[j]){
                    break;
                }
                if(j==arr2.length-1){
                    return i;
                }
                pos++;
            }
        }
        return -1;
    }
```
