---
title: express+mysql
date: 2022-07-25 15:06:06
tags:
  - 后端
  - express
  - mysql
---
**杨意不逢，抚凌云而自惜；钟期既遇，奏流水以何惭**
<!--more-->
#### 步骤

![image-20220719150947386](http://img.buxiaoxing.com/uPic/2022/07/19150949-4qIZrS-image-20220719150947386.png)



#### 安装与配置mysql模块

- 安装mysql模块

  ![image-20220719151055731](http://img.buxiaoxing.com/uPic/2022/07/19151058-9PlvNa-image-20220719151055731.png)

- 配置mysql模块

  ![image-20220719151131981](http://img.buxiaoxing.com/uPic/2022/07/19151133-hgAfY9-image-20220719151131981.png)

- 测试mysql是否正常工作

  ![image-20220719152042516](http://img.buxiaoxing.com/uPic/2022/07/19152044-9pfv31-image-20220719152042516.png)

  - 默认端口为3306可以通过port属性指定端口

    ```js
    const db = mysql.createPool({
      host: '124.223.225.150',
      port: '3307',
      user: 'root',
      password: 'root',
      database: 'my_db_01'
    })
    ```

  - 如果测试报错

    `ER_NOT_SUPPORTED_AUTH_MODE: Client does not support authentication protocol requested by server; consider upgrading MySQL client`

    在mysql的命令行执行

    `ALTER USER 'root' IDENTIFIED WITH mysql_native_password BY 'password'`

#### 使用myql操作数据库

- 查询数据

  ![image-20220719153952299](http://img.buxiaoxing.com/uPic/2022/07/19153953-t40H05-image-20220719153952299.png)

- 插入数据

  ![image-20220719154329294](http://img.buxiaoxing.com/uPic/2022/07/19154330-ymqBv4-image-20220719154329294.png)

  **快速插入数据**

  ![image-20220719155326041](http://img.buxiaoxing.com/uPic/2022/07/19155327-kys86S-image-20220719155326041.png)

- 更新数据

  ![image-20220719155735471](http://img.buxiaoxing.com/uPic/2022/07/19155738-I6yAtP-image-20220719155735471.png)

  **更新数据的便捷方式**

  ![image-20220719160256703](http://img.buxiaoxing.com/uPic/2022/07/19160258-n1QzyA-image-20220719160256703.png)

- 删除数据

  ![image-20220719160505613](http://img.buxiaoxing.com/uPic/2022/07/19160507-7s2yEa-image-20220719160505613.png)

- 标记删除

  ![image-20220719161113272](http://img.buxiaoxing.com/uPic/2022/07/19161114-AcN6ZF-image-20220719161113272.png)
