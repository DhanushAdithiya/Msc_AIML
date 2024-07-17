---
id: SQL Operators and Statements
aliases:
  - SQL Operators and Statements
tags: []
---

# SQL Operators and Keywords
## Union Operator
The union operator is used to compine the result of two or more **SELECT** statemtns.
    - Every SELECT statement within UNION must have the same number of columns
    - the columns must also have similar data types
    - The columsn in every SELECT statement must also be in the same order

**SYNTAX**
```sql
SELECT col_names FROM table1
UNION
SELECT col_names FROM table2
```
## Union All
The UNION operator selects only distinct values by default. To allow duplicate values use UNION ALL

**SYNTAX**
```sql
SELECT col_names FROM table1
UNION ALL
SELECT col_names FROM table2
```
## Order By
The ORDER BY keyword is used to sort the result-set in ascending or descending order. By default it is in ascending order

**SYNTAX**
```sql
SELECT * FROM Products
ORDER BY Price DESC;


SELECT * FROM Products
ORDER BY Price;

The following SQL statement selects all customers from the "Customers" table, sorted ascending by the "Country" and descending by the "CustomerName" column:

SELECT * FROM Customer
ORDER BY Country ASC, CustomerName DESC;
```
## MIN and MAX
Returns the smallest and the largest values of the column respectievely.

**SYNTAX**
```sql
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```

## SELECT
Used to return specific cols from the table

**SYNTAX**

```sql
SELECT col_names
FROM table_name

# Used to return the unique values from the table
SELECT DISTINC col_names
FROM table_name
```

## LIKE
Like operator is used in a where clause in order for pattern matching
    - % is used to match 0,1 or multiple characters - "L%": all names starting with L
    - _ is used to match a single character - "_a": all names that have exactly one char before a

**SYNTAX**
```sql
SELECT column_name
FROM table_name
WHERE name LIKE "D%";
```

## IN & NOT IN
IN is a shorthand for multiple OR operators
NOT IN performs the opposite 

**SYNTAX**
```sql
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');


SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

## ALIAS
SQL aliases are used to give a table, or a column in a table, a temporary name.
Aliases are often used to make column names more readable. 
An alias only exists for the duration of that query. An alias is created with the AS keyword.


**SYNTAX**
```sql
SELECT column_name AS alias_name
FROM table_name;

SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;

SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
FROM Customers;
```

## GROUP BY
The **GROUP BY** statement groups rows that have the same vlaues into summary rows.
It is often used with aggregate function (count, max, min, sum, avg) to group the result-set by one or more columns

**SYNTAX**
```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;
```

