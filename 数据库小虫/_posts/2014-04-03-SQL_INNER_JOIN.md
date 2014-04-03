---
layout: post
keywords: 数据库
tags: [数据库,SQL]
---

INNER JOIN 操作符
-------------------
INNER JOIN 关键字在表中存在至少一个匹配时返回行。

SQL INNER JOIN 语法

	SELECT column_name(s)
	FROM table1
	INNER JOIN table2
	ON table1.column_name=table2.column_name;
或：

	SELECT column_name(s)
	FROM table1
	JOIN table2
	ON table1.column_name=table2.column_name;
	
注释：INNER JOIN 与 JOIN 是相同的 (交集)。

### Demo
	SELECT Customers.CustomerName, Orders.OrderID
	FROM Customers
	INNER JOIN Orders
	ON Customers.CustomerID=Orders.CustomerID
	ORDER BY Customers.CustomerName;
	
### Mysql 
也可以用上面的写法，等同下面

	SELECT Customers.CustomerName, Orders.OrderID
	FROM Customers , Orders
	WHERE  Customers.CustomerID=Orders.CustomerID
	ORDER BY Customers.CustomerName;	

	
