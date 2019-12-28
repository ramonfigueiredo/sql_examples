Some SQL Examples
===========================

## Contents
1. [SQL SELECT](#sql-select)
2. [SQL SELECT DISTINCT](#sql-select-distinct)

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