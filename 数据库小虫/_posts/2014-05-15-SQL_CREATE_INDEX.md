---
layout: post
keywords: 数据库
tags: [数据库,SQL]
---

CREATE INDEX 语句
-------------------
CREATE INDEX 语句用于在表中创建索引。

在不读取整个表的情况下，索引使数据库应用程序可以更快地查找数据。

###索引

您可以在表中创建索引，以便更加快速高效地查询数据。

用户无法看到索引，它们只能被用来加速搜索/查询。

注释：更新一个包含索引的表需要比更新一个没有索引的表花费更多的时间，这是由于索引本身也需要更新。因此，理想的做法是仅仅在常常被搜索的列（以及表）上面创建索引。

###SQL CREATE INDEX 语法

在表上创建一个简单的索引。允许使用重复的值：

	CREATE INDEX index_name
	ON table_name (column_name)
	
###SQL CREATE UNIQUE INDEX 语法

在表上创建一个唯一的索引。不允许使用重复的值：唯一的索引意味着两个行不能拥有相同的索引值。

	CREATE UNIQUE INDEX index_name
	ON table_name (column_name)

**注释**：用于创建索引的语法在不同的数据库中不一样。因此，检查您的数据库中创建索引的语法。
	
###CREATE INDEX 实例

下面的 SQL 语句在 "Persons" 表的 "LastName" 列上创建一个名为 "PIndex" 的索引：

	CREATE INDEX PIndex
	ON Persons (LastName)
	
如果您希望索引不止一个列，您可以在括号中列出这些列的名称，用逗号隔开：

	CREATE INDEX PIndex
	ON Persons (LastName, FirstName)
	
Oracle 语法：
-------------

	CREATE UNIUQE | BITMAP INDEX <schema>.<index_name>

      ON <schema>.<table_name>

           (<column_name> | <expression> ASC | DESC,

            <column_name> | <expression> ASC | DESC,...)

		TABLESPACE <tablespace_name>

		STORAGE <storage_settings>

		LOGGING | NOLOGGING

		COMPUTE STATISTICS

		NOCOMPRESS | COMPRESS<nn>

		NOSORT | REVERSE

		PARTITION | GLOBAL PARTITION<partition_setting>

 

相关说明

* UNIQUE | BITMAP：指定UNIQUE为唯一值索引，BITMAP为位图索引，省略为B-Tree索引。

* <column_name> | <expression> ASC | DESC：可以对多列进行联合索引，当为expression时即“基于函数的索引”

* TABLESPACE：指定存放索引的表空间(索引和原表不在一个表空间时效率更高)

* STORAGE：可进一步设置表空间的存储参数

* LOGGING | NOLOGGING：是否对索引产生重做日志(对大表尽量使用NOLOGGING来减少占用空间并提高效率)

* COMPUTE STATISTICS：创建新索引时收集统计信息

* NOCOMPRESS | COMPRESS<nn>：是否使用“键压缩”(使用键压缩可以删除一个键列中出现的重复值)

* NOSORT | REVERSE：NOSORT表示与表中相同的顺序创建索引，REVERSE表示相反顺序存储索引值

* PARTITION | NOPARTITION：可以在分区表和未分区表上对创建的索引进行分区