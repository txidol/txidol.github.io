---
layout: post
keywords: 数据库
tags: [数据库,SQL]
---

SELECT 语句
---------------
SELECT 语句用于从数据库中选取数据。

结果被存储在一个结果表中，称为结果集。  
<br>
#### SELECT 语法

	SELECT column_name,column_name
	FROM table_name;
与

	SELECT * FROM table_name;

---
	
SELECT DISTINCT 语句
--------------------
在表中，一个列可能会包含多个重复值，有时您也许希望仅仅列出不同（distinct）的值。

`DISTINC` 关键词用于返回唯一不同的值。  
<br>
#### SELECT DISTINCT 语法

	SELECT DISTINCT column_name,column_name
	FROM table_name;

---
	
WHERE 子句
----------
WHERE 子句用于提取那些满足指定标准的记录。  
<br>
#### WHERE 语法

	SELECT column_name,column_name
	FROM table_name
	WHERE column_name operator value;

---
	
AND & OR 运算符
---------------
AND & OR 运算符用于基于一个以上的条件对记录进行过滤。  
<br>
#### AND & OR 运算符
如果第一个条件和第二个条件都成立，则 AND 运算符显示一条记录。

如果第一个条件和第二个条件中只要有一个成立，则 OR 运算符显示一条记录。

	SELECT * FROM Customers
	WHERE Country='Germany'
	AND City='Berlin';
	
	SELECT * FROM Customers
	WHERE City='Berlin'
	OR City='München';
	
	SELECT * FROM Customers
	WHERE Country='Germany'
	AND (City='Berlin' OR City='München');

---
	
ORDER BY 关键字
---------------
ORDER BY 关键字用于对结果集按照一个列或者多个列进行排序。

ORDER BY 关键字默认按照升序对记录进行排序。如果需要按照降序对记录进行排序，您可以使用 DESC 关键字。  
<br>
#### ORDER BY 语法

	SELECT column_name,column_name
	FROM table_name
	ORDER BY column_name,column_name ASC|DESC;

---
	
INSERT INTO 语句
----------------
INSERT INTO 语句用于向表中插入新记录。  
<br>
#### INSERT INTO 语法

INSERT INTO 语句可以有两种编写形式。

- 第一种形式无需指定要插入数据的列名，只需提供被插入的值即可：

		INSERT INTO table_name
		VALUES (value1,value2,value3,...);
	
- 第二种形式需要指定列名及被插入的值：

		INSERT INTO table_name (column1,column2,column3,...)
		VALUES (value1,value2,value3,...);

---
	
UPDATE 语句
-----------
UPDATE 语句用于更新表中已存在的记录。  
<br>
#### UPDATE 语法

	table_name
	SET column1=value1,column2=value2,...
	WHERE some_column=some_value;

<i class="fa fa-warning"></i>请注意 SQL UPDATE 语句中的 WHERE 子句！
WHERE 子句规定哪条记录或者哪些记录需要更新。如果您省略了 WHERE 子句，所有的记录都将被更新！

---

DELETE 语句
-----------
DELETE 语句用于删除表中的行。  
<br>
#### DELETE 语法

	DELETE FROM table_name
	WHERE some_column=some_value;

<i class="fa fa-warning"></i>请注意 SQL DELETE 语句中的 WHERE 子句！
WHERE 子句规定哪条记录或者哪些记录需要删除。如果您省略了 WHERE 子句，所有的记录都将被删除！
