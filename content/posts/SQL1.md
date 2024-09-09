---
author: ["Yandong Zhang"]
title: "Common MySQL Codes"
date: "2024-09-07"
description: "MySQL Notes."
summary: "MySQL Cheat Sheet"
tags: ["SQL", "MySQL", "Joins"]
categories: ["SQL"]
series: []
ShowToc: true
TocOpen: true
---

### Introduction to MySQL Commands and Tips

This note provides a comprehensive overview of commonly used MySQL Joins and Unions commands. 


### Inner Joins
Returns only the rows that have matching values in both tables.
```html {linenos=true,hl_lines=[2,8]}
SELECT columns
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;

```

### LEFT JOIN (or LEFT OUTER JOIN)
Returns all rows from the left table and matched rows from the right table. If no match is found, NULL values are returned for columns from the right table.
```html {linenos=true,hl_lines=[2,8]}
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.common_column = table2.common_column;

```

### RIGHT JOIN (or RIGHT OUTER JOIN
Returns all rows from the right table and matched rows from the left table. If no match is found, NULL values are returned for columns from the left table.
```html {linenos=true}
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.common_column = table2.common_column;

```

### FULL JOIN (or FULL OUTER JOIN)
Returns all rows when there is a match in either left or right table. If there is no match, NULL values are returned for columns of the table that lacks a match.


```html {linenos=true,hl_lines=[2,8]}
SELECT columns
FROM table1
FULL JOIN table2
ON table1.common_column = table2.common_column;

```

### CROSS JOIN
Returns the Cartesian product of the two tables, i.e., all possible combinations of rows from the tables.
```html {linenos=true,hl_lines=[2,8]}
SELECT columns
FROM table1
CROSS JOIN table2;

```
### SELF JOIN
A join where a table is joined with itself. Typically used with table aliases.

```html {linenos=true,hl_lines=[2,8]}
SELECT a.columns, b.columns
FROM table a
INNER JOIN table b
ON a.common_column = b.common_column;

```

### Union
Unions are used to combine the results of two or more SELECT queries into a single result set. The queries combined with a union must have the same number of columns and compatible data types.
UNION: Combines the result sets of two or more SELECT queries and removes duplicate rows.
```html {linenos=true,hl_lines=[2,8]}
SELECT column1, column2
FROM table1
UNION
SELECT column1, column2
FROM table2;
```
UNION ALL: Combines the result sets of two or more SELECT queries and includes all rows, including duplicates.
```html {linenos=true,hl_lines=[2,8]}
SELECT column1, column2
FROM table1
UNION ALL
SELECT column1, column2
FROM table2;
```

