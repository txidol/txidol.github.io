---
layout: post
keywords: 数据库
tags: [数据库,SQL]
---

SQL SELECT TOP 子句
-------------------
SELECT TOP 子句用于规定要返回的记录的数目。

SELECT TOP 子句对于拥有数千条记录的大型表来说，是非常有用的。

**注释**：并非所有的数据库系统都支持 SELECT TOP 子句。

###SQL Server / MS Access 语法

    SELECT TOP number|percent column_name(s)
    FROM table_name;

###MySQL 语法

    SELECT column_name(s)
    FROM table_name
    LIMIT number;
实例

    SELECT *
    FROM Persons
    LIMIT 5;
###Oracle 语法

    SELECT column_name(s)
    FROM table_name
    WHERE ROWNUM <= number;
实例

    SELECT *
    FROM Persons
    WHERE ROWNUM <=5;
###MongoDB 语法
    db.users.findOne()    
or  
    
    db.users.find().limit(1)