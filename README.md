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
SELECT COUNT(*) AS DistinctCountries FROM (SELECT DISTINCT Country FROM Customers);
```

Go back to [Contents](#contents).

## SQL WHERE

* WHERE Clause

```sql
SELECT * FROM Customers WHERE Country='Brazil';
```

* Text Fields vs. Numeric Fields

```sql
SELECT * FROM Customers WHERE CustomerID=1;
```

Go back to [Contents](#contents).

## SQL AND OR NOT Operators

* AND

```sql
SELECT * FROM Customers WHERE Country='Brazil' AND City='São Paulo';
```

* OR

```sql
SELECT * FROM Customers WHERE Country='Brazil' OR City='Belo Horizonte';
```

* NOT

```sql
SELECT * FROM Customers WHERE NOT Country='Brazil';
```

* Combining AND, OR and NOT

```sql
SELECT * FROM Customers WHERE Country='Canada' AND (City='Montréal' OR City='Vancouver')
```

Go back to [Contents](#contents).

## SQL ORDER BY

* ORDER BY

```sql
SELECT * FROM Customers ORDER BY Country;
```

* ORDER BY DESC

```sql
SELECT * FROM Customers ORDER BY Country DESC;
```

* ORDER BY Several Columns

```sql
SELECT * FROM Customers ORDER BY Country, CustomerName;
```

Go back to [Contents](#contents).

## SQL INSERT INTO

* INSERT INTO

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country) VALUES ('Customer Name 1','Contact Name 1','Address 1','Montréal','123456','Canada');
```

* Insert data in specific columns

```sql
INSERT INTO Customers (CustomerName, City, Country) VALUES ('Customer Name 2', 'São Paulo', 'Brazil');
```

Go back to [Contents](#contents).

## SQL NULL Values

* IS NULL Operator

```sql
SELECT CustomerName, ContactName, Address FROM Customers WHERE Address IS NULL;
```

* IS NOT NULL Operator

```sql
SELECT CustomerName, ContactName, Address FROM Customers WHERE Address IS NOT NULL;
```

Go back to [Contents](#contents).

## SQL Update

* UPDATE Table

```sql
UPDATE Customers SET ContactName='Jim Carrey', City='Newmarket' WHERE CustomerID=1;
```

* UPDATE Multiple Records

```sql
UPDATE Customers SET ContactName='Cobie Smulders' WHERE Country='Canada';
```

* UPDATE Warning (if you omit the WHERE clause, all records will be updated)

```sql
/*You should Restore the Database after finishing this example*/
UPDATE Customers SET ContactName='Pedro';
```

Go back to [Contents](#contents).

## SQL DELETE

* DELETE

```sql
DELETE FROM Customers WHERE CustomerName='Elvis Presley';
```

* DELETE All Records

```sql
DELETE FROM Customers;
```

Go back to [Contents](#contents).

## SQL SELECT TOP

* SELECT TOP

```sql
SELECT TOP 3 * FROM Customers;
```

* LIMIT

```sql
SELECT * FROM Customers LIMIT 3;
```

* SELECT TOP PERCENT

```sql
SELECT TOP 50 PERCENT * FROM Customers;
```

* SELECT TOP and add a WHERE Clause

```sql
SELECT TOP 3 * FROM Customers WHERE Country='Brazil';
```

Go back to [Contents](#contents).

## SQL MIN MAX

* MIN()

```sql
SELECT MIN(Price) AS SmallestPrice FROM Products; 
```

* MAX()

```sql
SELECT MAX(Price) AS LargestPrice FROM Products; 
```

Go back to [Contents](#contents).

## SQL COUNT AVG SUM

* COUNT()

```sql
SELECT COUNT(ProductID) FROM Products;
```

* AVG()

```sql
SELECT AVG(Price) FROM Products;
```

* SUM()

```sql
SELECT SUM(Quantity) FROM OrderDetails;
```

Go back to [Contents](#contents).

## SQL LIKE

* LIKE - select all table rows starting with "a"

```sql

```

* LIKE - select all table rows ending with "a"

```sql

```

* LIKE - select all table rows that have "or" in any position

```sql

```

* LIKE - select all table rows that have "r" in the second position

```sql

```

* LIKE - select all table rows that starts with "a" and ends with "o"

```sql

```

* LIKE - select all table rows that does NOT start with "a"

```sql

```

Go back to [Contents](#contents).

## SQL Wildcards

* Using the % Wildcard

```sql

```

* Using the _ Wildcard

```sql

```

* Using the [charlist] Wildcard

```sql

```

* Using the [!charlist] Wildcard

```sql

```

Go back to [Contents](#contents).

## SQL IN

* IN

```sql

```

* NOT IN

```sql

```

Go back to [Contents](#contents).

## SQL BETWEEN

* BETWEEN

```sql

```

* NOT BETWEEN

```sql

```

* BETWEEN with IN

```sql

```

* BETWEEN Text Values

```sql

```

* NOT BETWEEN Text Values

```sql

```

Go back to [Contents](#contents).

## SQL Aliases

* Alias for Columns

```sql

```

* Two Aliases

```sql

```

* Alias for Tables

```sql

```

Go back to [Contents](#contents).

## SQL Joins

* INNER JOIN

```sql

```

* LEFT JOIN

```sql

```

* RIGHT JOIN

```sql

```

* Self JOIN

```sql

```

Go back to [Contents](#contents).

## SQL UNION

* UNION

```sql

```

* UNION ALL

```sql

```

* UNION With WHERE

```sql

```

* UNION ALL With WHERE

```sql

```

Go back to [Contents](#contents).

## SQL GROUP BY

* GROUP BY

```sql

```

* GROUP BY and ORDER BY

```sql

```

* GROUP BY With JOIN

```sql

```

Go back to [Contents](#contents).

## SQL HAVING

* HAVING and GROUP BY

```sql

```

* HAVING and ORDER BY

```sql

```

Go back to [Contents](#contents).

## SQL EXISTS

* EXISTS

```sql

```

Go back to [Contents](#contents).

## SQL ANY ALL

* ANY

```sql

```

* ALL

```sql

```

Go back to [Contents](#contents).

## SQL INSERT INTO SELECT

* INSERT INTO SELECT

```sql

```

* INSERT INTO SELECT with WHERE

```sql

```

Go back to [Contents](#contents).

## SQL CASE

* CASE 1

```sql

```

* CASE 2

```sql

```

Go back to [Contents](#contents).

## SQL Comments

* Single Line Comments

```sql

```

* Single Line Comments At The End Of a Line

```sql

```

* Multi-line Comments

```sql

```

Go back to [Contents](#contents).

## SQL Database

* SQL Create DB

```sql

```

* SQL DROP DB

```sql

```

* SQL Backup DB

```sql

```

* SQL Create Table

```sql

```

* SQL Drop Table

```sql

```

* SQL Alter Table

```sql

```

* SQL Constraints

```sql

```

* SQL Not Null

```sql

```

* SQL Unique

```sql

```

* SQL Primary Key

```sql

```

* SQL Foreign Key

```sql

```

* SQL Check

```sql

```

* SQL Default

```sql

```

* SQL Index

```sql

```

* SQL Auto Increment

```sql

```

* SQL Dates

```sql

```

* SQL Views

```sql

```

* SQL Injection

```sql

```

* SQL Hosting


Go back to [Contents](#contents).
