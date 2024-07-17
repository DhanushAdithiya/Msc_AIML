---
id: SQL order of execution
aliases:
  - SQL order of execution
tags: []
---

# SQL order of execution

An SQL query comprises of various clauses like SELECT, FROM, WHERE, GROUPBY, HAVING, and ORDERBY clauses. Each clause has a specific role in the query. Let’s understand each of them briefly.

When you write any query, your query is processed in the following steps:

Getting Data (FROM/JOIN)
Row Filter (WHERE)
Grouping (GROUP BY)
Group Filter (HAVING)
Return Expression (SELECT)
Order & Paging (ORDER BY & LIMIT/OFFSET)
