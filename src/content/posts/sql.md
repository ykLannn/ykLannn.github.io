---
title: sql
published: 2024-07-21
description: 'sql语句的基础复习'
image: ''
tags: [sql]
category: 'sql'
draft: false 
---
## 基本查询
### 查询某一列
```sql
-- 查询表中的某一列数据
SELECT column_name FROM table_name;
```
### 查询多列
```sql
-- 查询表中的多列数据
SELECT column1, column2, column3 FROM table_name;
```
### 查询所有列
```sql
-- 查询表中的所有列数据
SELECT * FROM table_name;
```
## 条件查询
### 单条件查询
```sql
-- 查询满足条件的数据行
SELECT column1, column2 FROM table_name WHERE condition;
```
### 多条件查询
```sql
-- 查询满足多个条件的数据行
SELECT column1, column2 FROM table_name WHERE condition1 AND condition2;
SELECT column1, column2 FROM table_name WHERE condition1 OR condition2;
SELECT column1, column2 FROM table_name WHERE condition1 NOT condition2;

```
### 比较运算符
```sql
-- 使用比较运算符进行条件过滤
SELECT column1, column2 FROM table_name WHERE column1 > 10;
SELECT column1, column2 FROM table_name WHERE column2 BETWEEN 10 AND 20;
SELECT column1, column2 FROM table_name WHERE column1 IN (value1, value2, ...);
SELECT column1, column2 FROM table_name WHERE column3 LIKE 'pattern%';  -- 模糊匹配
SELECT column1, column2 FROM table_name WHERE column4 IS NULL;  -- 为空值
SELECT column1, column2 FROM table_name WHERE column5 IS NOT NULL;  -- 非空值

```
## 聚合函数
### COUNT() 函数
```sql
-- 计算行数或非空值数量
SELECT COUNT(*) FROM table_name;  -- 计算表中行数
SELECT COUNT(column) FROM table_name;  -- 计算某列非空值数量
```
### SUM() 函数
```sql
-- 计算数值列的总和
SELECT SUM(column) FROM table_name;
```
### AVG() 函数
```sql
-- 计算数值列的平均值
SELECT AVG(column) FROM table_name;
```
### MAX() 和 MIN() 函数
```sql
-- 查找数值列的最大值和最小值
SELECT MAX(column) FROM table_name;
SELECT MIN(column) FROM table_name;
```
## 分组和排序
### GROUP BY 子句
```sql
-- 根据列进行分组
SELECT column1, COUNT(*) FROM table_name GROUP BY column1;
```
### HAVING 子句
```sql
-- 对分组结果进行条件过滤
SELECT column1, COUNT(*) FROM table_name GROUP BY column1 HAVING COUNT(*) > 1;
```
### ORDER BY 子句
```sql
-- 对结果进行排序
SELECT column1, column2 FROM table_name ORDER BY column1 ASC;
SELECT column1, column2 FROM table_name ORDER BY column2 DESC;
```
## 连接查询
### INNER JOIN
```sql
-- 内连接，返回两个表中匹配行的交集
SELECT t1.column1, t2.column2 FROM table1 AS t1 INNER JOIN table2 AS t2 ON t1.key = t2.key;
```
### LEFT JOIN 和 RIGHT JOIN
```sql
-- 左连接和右连接，返回左表（或右表）的所有行和右表（或左表）中匹配行的交集
SELECT t1.column1, t2.column2 FROM table1 AS t1 LEFT JOIN table2 AS t2 ON t1.key = t2.key;
SELECT t1.column1, t2.column2 FROM table1 AS t1 RIGHT JOIN table2 AS t2 ON t1.key = t2.key;
```
### FULL JOIN
```sql
-- 全外连接，返回左表和右表中所有的行，以及匹配的行
SELECT t1.column1, t2.column2 FROM table1 AS t1 FULL JOIN table2 AS t2 ON t1.key = t2.key;
```
## 子查询
### 单行子查询
```sql
-- 使用单行子查询
SELECT column1, column2 FROM table_name WHERE column1 = (SELECT column1 FROM another_table WHERE condition);
```
### 多行子插询
```sql
-- 使用多行子查询
SELECT column1, column2 FROM table_name WHERE column1 IN (SELECT column1 FROM another_table WHERE condition);
```
### 相关子查询
```sql
-- 使用相关子查询
SELECT column1, column2 FROM table_name WHERE EXISTS (SELECT 1 FROM another_table WHERE table_name.column1 = another_table.column1);
```
## 数据操作
### 插入数据
```sql
-- 插入一行数据
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
-- 插入多行数据
INSERT INTO table_name (column1, column2) VALUES (value1, value2), (value3, value4);
```
### 更新数据
```sql
-- 更新表中的数据
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 删除数据
```sql
-- 删除表中的数据
DELETE FROM table_name WHERE condition;
```
## 创建和删除表
### 创建表
```sql
-- 创建一个新的表
CREATE TABLE table_name (
  column1 datatype PRIMARY KEY,
  column2 datatype NOT NULL,
  column3 datatype DEFAULT default_value
);
```
### 删除表
```sql
-- 删除一个表
DROP TABLE table_name;
```
### 修改表
```sql
-- 向表中添加列
ALTER TABLE table_name ADD column_name datatype;
-- 删除表中的列
ALTER TABLE table_name DROP COLUMN column_name;
-- 修改表中列的数据类型
ALTER TABLE table_name MODIFY COLUMN column_name new_datatype;
```
### 创建索引
```sql
-- 创建一个新的索引
CREATE INDEX index_name ON table_name (column_name);
-- 删除一个索引
DROP INDEX index_name;
```
## 事务处理
### 开始事务
```sql
-- 开始一个事务
START TRANSACTION;
```
### 提交事务
```sql
-- 提交一个事务
COMMIT;
```
### 回滚事务
```sql
-- 回滚一个事务
ROLLBACK;
```
## 查看表结构
### 显示表的定义
```sql
-- 显示表的定义
DESCRIBE table_name;
```
### 查看表的定义
```sql
-- 查看表的索引
SHOW INDEX FROM table_name;
```
### 查看表的索引
```sql
-- 查看表的索引
SHOW INDEX FROM table_name;
```
### 查看数据库中的表
```sql
-- 查看数据库中的所有表
SHOW TABLES;
```