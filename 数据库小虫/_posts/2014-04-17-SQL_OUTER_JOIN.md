---
layout: post
keywords: 数据库
tags: [数据库,SQL]
---

LEFT JOIN 操作符
-------------------
LEFT JOIN 关键字从左表（table1）返回所有的行，即使右表（table2）中没有匹配。如果右表中没有匹配，则结果为 NULL。

SQL LEFT JOIN 语法

	SELECT column_name(s)
	FROM table1
	LEFT JOIN table2
	ON table1.column_name=table2.column_name;
或：

	SELECT column_name(s)
	FROM table1
	LEFT OUTER JOIN table2
	ON table1.column_name=table2.column_name;
	
注释：在某些数据库中，LEFT JOIN 称为 LEFT OUTER JOIN。

### Demo
	SELECT Customers.CustomerName, Orders.OrderID
	FROM Customers
	LEFT JOIN Orders
	ON Customers.CustomerID=Orders.CustomerID
	ORDER BY Customers.CustomerName;
注释：LEFT JOIN 关键字从左表（Customers）返回所有的行，即使右表（Orders）中没有匹配。
	
	
RIGHT JOIN 操作符
-------------------
RIGHT JOIN 关键字从右表（table2）返回所有的行，即使左表（table1）中没有匹配。如果左表中没有匹配，则结果为 NULL。

SQL RIGHT JOIN 语法

	SELECT column_name(s)
	FROM table1
	RIGHT JOIN table2
	ON table1.column_name=table2.column_name;
或：

	SELECT column_name(s)
	FROM table1
	RIGHT OUTER JOIN table2
	ON table1.column_name=table2.column_name;
	
注释：在某些数据库中，RIGHT JOIN 称为 RIGHT OUTER JOIN。

### Demo
	SELECT Orders.OrderID, Employees.FirstName
	FROM Orders
	RIGHT JOIN Employees
	ON Orders.EmployeeID=Employees.EmployeeID
	ORDER BY Orders.OrderID;
注释：RIGHT JOIN 关键字从右表（Employees）返回所有的行，即使左表（Orders）中没有匹配。
	
FULL OUTER JOIN 操作符
-------------------
FULL OUTER JOIN 关键字只要左表（table1）和右表（table2）其中一个表中存在匹配，则返回行.

FULL OUTER JOIN 关键字结合了 LEFT JOIN 和 RIGHT JOIN 的结果。

SQL FULL OUTER JOIN 语法

	SELECT column_name(s)
	FROM table1
	FULL OUTER JOIN table2
	ON table1.column_name=table2.column_name;

