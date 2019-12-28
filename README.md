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
8. [SQL Update](#sql-update)
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

Go back to [Contents](#contents).

## SQL AND OR NOT Operators

Go back to [Contents](#contents).

## SQL ORDER BY

Go back to [Contents](#contents).

## SQL INSERT INTO

Go back to [Contents](#contents).

## SQL NULL Values

Go back to [Contents](#contents).

## SQL Update

Go back to [Contents](#contents).

## SQL DELETE

Go back to [Contents](#contents).

## SQL SELECT TOP

Go back to [Contents](#contents).

## SQL MIN MAX

Go back to [Contents](#contents).

## SQL COUNT AVG SUM

Go back to [Contents](#contents).

## SQL LIKE

Go back to [Contents](#contents).

## SQL Wildcards

Go back to [Contents](#contents).

## SQL IN

Go back to [Contents](#contents).

## SQL BETWEEN

Go back to [Contents](#contents).

## SQL Aliases

Go back to [Contents](#contents).

## SQL Joins

Go back to [Contents](#contents).

## SQL UNION

Go back to [Contents](#contents).

## SQL GROUP BY

Go back to [Contents](#contents).

## SQL HAVING

Go back to [Contents](#contents).

## SQL EXISTS

Go back to [Contents](#contents).

## SQL ANY ALL

Go back to [Contents](#contents).

## SQL INSERT INTO SELECT

Go back to [Contents](#contents).

## SQL CASE

Go back to [Contents](#contents).

## SQL Comments

Go back to [Contents](#contents).

## SQL Database

Go back to [Contents](#contents).
