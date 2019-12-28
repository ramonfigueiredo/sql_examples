Some SQL Examples
===========================

## Contents
1. [SQL SELECT](#sql-select)
2. [SQL SELECT DISTINCT](#sql-select-distinct)
3. [SQL WHERE](#sql-where)
4. [SQL AND OR NOT Operators](#sql-and-or-not-operators)
5. [SQL ORDER BY](#sql-order-by)
6. [SQL INSERT INTO](#sql-insert-into)
7. [SQL NULL Values](#sql-null-values)
8. [SQL UPDATE](#sql-update)
9. [SQL DELETE](#sql-delete)
10. [SQL SELECT TOP](#sql-select-top)
11. [SQL MIN MAX](#sql-min-max)
12. [SQL COUNT AVG SUM](#sql-count-avg-sum)
13. [SQL LIKE](#sql-like)
14. [SQL Wildcards](#sql-wildcards)
15. [SQL IN](#sql-in)
16. [SQL BETWEEN](#sql-between)
17. [SQL Aliases](#sql-aliases)
18. [SQL Joins](#sql-joins)
19. [SQL UNION](#sql-union)
20. [SQL GROUP BY](#sql-group-by)
21. [SQL HAVING](#sql-having)
22. [SQL EXISTS](#sql-exists)
23. [SQL ANY ALL](#sql-any-all)
24. [SQL INSERT INTO SELECT](#sql-insert-into-select)
25. [SQL CASE](#sql-case)
26. [SQL Comments](#sql-comments)
27. [SQL Database](#sql-database)

## SQL

SQL stands for Structured Query Language. SQL is a standard language for storing, manipulating and retrieving data in databases.

The following SQL examples will show you how to use SQL in: MySQL, SQL Server, MS Access, Oracle, Sybase, Informix, Postgres, and other database systems.

## SQL SELECT

* SELECT Column

```sql
SELECT CustomerName, City FROM Customers;
```

* SELECT *

```sql
SELECT * FROM Customers;
```

Go back to [Contents](#contents).

## SQL SELECT DISTINCT

* SELECT DISTINCT

```sql
SELECT DISTINCT Country FROM Customers;
```

* SELECT COUNT(DISTINCT column_name)

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```

* SELECT COUNT(DISTINCT column_name) workaround for MS ACCESS

```sql
SELECT COUNT(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```

Go back to [Contents](#contents).

## SQL WHERE

* WHERE Clause

```sql

```

* Text Fields vs. Numeric Fields

```sql

```

Go back to [Contents](#contents).

## SQL AND OR NOT Operators

* AND

* OR

* NOT

* Combining AND, OR and NOT

Go back to [Contents](#contents).

## SQL ORDER BY

* ORDER BY

* ORDER BY DESC

* ORDER BY Several Columns

Go back to [Contents](#contents).

## SQL INSERT INTO

* INSERT INTO

* Insert data in specific columns

Go back to [Contents](#contents).

## SQL NULL Values

* IS NULL Operator

* IS NOT NULL Operator

Go back to [Contents](#contents).

## SQL Update

* UPDATE Table

* UPDATE Multiple Records

* UPDATE Warning (if you omit the WHERE clause, all records will be updated)

Go back to [Contents](#contents).

## SQL DELETE

* DELETE

* DELETE All Records

Go back to [Contents](#contents).

## SQL SELECT TOP

* SELECT TOP

* LIMIT

* SELECT TOP PERCENT

* SELECT TOP and add a WHERE Clause

Go back to [Contents](#contents).

## SQL MIN MAX

* MIN()

* MAX()

Go back to [Contents](#contents).

## SQL COUNT AVG SUM

* COUNT()

* AVG()

* SUM()

Go back to [Contents](#contents).

## SQL LIKE

* LIKE - select all table rows starting with "a"

* LIKE - select all table rows ending with "a"

* LIKE - select all table rows that have "or" in any position

* LIKE - select all table rows that have "r" in the second position

* LIKE - select all table rows that starts with "a" and ends with "o"

* LIKE - select all table rows that does NOT start with "a"

Go back to [Contents](#contents).

## SQL Wildcards

* Using the % Wildcard

* Using the _ Wildcard

* Using the [charlist] Wildcard

* Using the [!charlist] Wildcard

Go back to [Contents](#contents).

## SQL IN

* IN

* NOT IN

Go back to [Contents](#contents).

## SQL BETWEEN

* BETWEEN

* NOT BETWEEN

* BETWEEN with IN

* BETWEEN Text Values

* NOT BETWEEN Text Values

Go back to [Contents](#contents).

## SQL Aliases

* Alias for Columns

* Two Aliases

* Alias for Tables

Go back to [Contents](#contents).

## SQL Joins

* INNER JOIN

* LEFT JOIN

* RIGHT JOIN

* Self JOIN

Go back to [Contents](#contents).

## SQL UNION

* UNION

* UNION ALL

* UNION With WHERE

* UNION ALL With WHERE

Go back to [Contents](#contents).

## SQL GROUP BY

* GROUP BY

* GROUP BY and ORDER BY

* GROUP BY With JOIN

Go back to [Contents](#contents).

## SQL HAVING

* HAVING and GROUP BY

* HAVING and ORDER BY

Go back to [Contents](#contents).

## SQL EXISTS

* EXISTS

Go back to [Contents](#contents).

## SQL ANY ALL

* ANY

* ALL

Go back to [Contents](#contents).

## SQL INSERT INTO SELECT

* INSERT INTO SELECT

* INSERT INTO SELECT with WHERE

Go back to [Contents](#contents).

## SQL CASE

* CASE 1

* CASE 2

Go back to [Contents](#contents).

## SQL Comments

* Single Line Comments

* Single Line Comments At The End Of a Line

* Multi-line Comments

Go back to [Contents](#contents).

## SQL Database

* SQL Create DB

* SQL DROP DB

* SQL Backup DB

* SQL Create Table

* SQL Drop Table

* SQL Alter Table

* SQL Constraints

* SQL Not Null

* SQL Unique

* SQL Primary Key

* SQL Foreign Key

* SQL Check

* SQL Default

* SQL Index

* SQL Auto Increment

* SQL Dates

* SQL Views

* SQL Injection

* SQL Hosting

Go back to [Contents](#contents).
