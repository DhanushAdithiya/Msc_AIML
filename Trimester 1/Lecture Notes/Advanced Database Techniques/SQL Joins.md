---
id: SQL Joins
aliases:
  - SQL Joins
tags: []
---

# SQL Joins
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

## Inner Join
Returns records that have matching values in both tables.

**SYNTAX**
```sql
SELECT column_name(s)             
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;

SELECT ProductID, ProductName, CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

## Left Outer Join
Returns all records from the left table, and the matched records from the right table.

**SYNTAX**
```sql
SELECT column_name(s)             
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

## Right Outer Join
Returns all the records from the right table and the matched records from the left table.


**SYNTAX**
```sql
SELECT column_name(s)             
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

## Full Outer Join
Returns all the records when there is a match in either left or right table.

**SYNTAX**
```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```

## Self Join
The self join i used to join a table to itself as if the table were two tables.
To carry this out out, asias of the tables should be used at lease onece.

Unlike other joins we use the WHERE clause to specify the join condition.

**SYNTAX**
```sql
SELECT column_name(s)
FROM table1 a, table1 b
WHERE a.common_field = b.common_field;
```
![sql_joins.png](assets/imgs/sql_joins.png)
