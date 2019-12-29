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
SELECT * FROM Customers WHERE CustomerName LIKE 'a%';
```

* LIKE - select all table rows ending with "a"

```sql
SELECT * FROM Customers WHERE CustomerName LIKE '%a';
```

* LIKE - select all table rows that have "or" in any position

```sql
SELECT * FROM Customers WHERE CustomerName LIKE '%or%'
```

* LIKE - select all table rows that have "r" in the second position

```sql
SELECT * FROM Customers WHERE CustomerName LIKE '_r%';
```

* LIKE - select all table rows that starts with "a" and ends with "o"

```sql
SELECT * FROM Customers WHERE ContactName LIKE 'a%o';
```

* LIKE - select all table rows that does NOT start with "a"

```sql
SELECT * FROM Customers WHERE CustomerName NOT LIKE 'a%';
```

Go back to [Contents](#contents).

## SQL Wildcards

* Using the % Wildcard

```sql
SELECT * FROM Customers WHERE City LIKE 'ra%';
```

* Using the _ Wildcard

```sql
SELECT * FROM Customers WHERE City LIKE '_ontréal';
```

* Using the [charlist] Wildcard

```sql
SELECT * FROM Customers WHERE City LIKE '[bsp]%';
```

* Using the [!charlist] Wildcard

```sql
SELECT * FROM Customers WHERE City LIKE '[!bsp]%';
```

Go back to [Contents](#contents).

## SQL IN

* IN

```sql
SELECT * FROM Customers WHERE Country IN ('Canada', 'France', 'Brazil');
```

* NOT IN

```sql
SELECT * FROM Customers WHERE Country NOT IN ('Canada', 'France', 'Brazil');
```

Go back to [Contents](#contents).

## SQL BETWEEN

* BETWEEN

```sql
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20;
```

* NOT BETWEEN

```sql
SELECT * FROM Products WHERE Price NOT BETWEEN 10 AND 20;
```

* BETWEEN with IN

```sql
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20 AND NOT CategoryID IN (1,2,3);
```

* BETWEEN Text Values

```sql
SELECT * FROM Products WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni' ORDER BY ProductName;
```

* NOT BETWEEN Text Values

```sql
SELECT * FROM Products WHERE ProductName NOT BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni' ORDER BY ProductName;
```

Go back to [Contents](#contents).

## SQL Aliases

* Alias for Columns

```sql
SELECT CustomerID AS ID, CustomerName AS Customer FROM Customers;
```

* Two Aliases

```sql
SELECT CustomerName AS Customer, ContactName AS [Contact Person] FROM Customers;
```

* Alias for Tables

```sql
SELECT o.OrderID, o.OrderDate, c.CustomerName FROM Customers AS c, Orders AS o WHERE c.CustomerName="Around the Horn" AND c.CustomerID=o.CustomerID;
```

Go back to [Contents](#contents).

## SQL Joins

* INNER JOIN

```sql
SELECT Orders.OrderID, Customers.CustomerName FROM Orders INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

* LEFT JOIN

```sql
SELECT Customers.CustomerName, Orders.OrderID FROM Customers LEFT JOIN Orders ON Customers.CustomerID=Orders.CustomerID ORDER BY Customers.CustomerName;
```

* RIGHT JOIN

```sql
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName FROM Orders RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID ORDER BY Orders.OrderID;
```

* Self JOIN

```sql
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City FROM Customers A, Customers B WHERE A.CustomerID <> B.CustomerID AND A.City = B.City ORDER BY A.City;
```

Go back to [Contents](#contents).

## SQL UNION

* UNION

```sql
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers 
ORDER BY City;
```

* UNION ALL

```sql
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers 
ORDER BY City;
```

* UNION With WHERE

```sql
SELECT City, Country FROM Customers WHERE Country='Germany'
UNION
SELECT City, Country FROM Suppliers WHERE Country='Germany' ORDER BY City;
```

* UNION ALL With WHERE

```sql
SELECT City, Country FROM Customers WHERE Country='Germany'
UNION ALL
SELECT City, Country FROM Suppliers WHERE Country='Germany' ORDER BY City;
```

Go back to [Contents](#contents).

## SQL GROUP BY

* GROUP BY

```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country;
```

* GROUP BY and ORDER BY

```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country ORDER BY COUNT(CustomerID) DESC;
```

* GROUP BY With JOIN

```sql
SELECT Shippers.ShipperName,COUNT(Orders.OrderID) AS NumberOfOrders FROM Orders LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID GROUP BY ShipperName;
```

Go back to [Contents](#contents).

## SQL HAVING

* HAVING and GROUP BY

```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country HAVING COUNT(CustomerID) > 5;
```

* HAVING and ORDER BY

```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country HAVING COUNT(CustomerID) > 5 ORDER BY COUNT(CustomerID) DESC;
```

Go back to [Contents](#contents).

## SQL EXISTS

* EXISTS

```sql
SELECT SupplierName FROM Suppliers WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20);
```

Go back to [Contents](#contents).

## SQL ANY ALL

* ANY

```sql
SELECT ProductName  FROM Products WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);
```

* ALL

```sql
SELECT ProductName  FROM Products WHERE ProductID = ALL (SELECT ProductID FROM OrderDetails WHERE Quantity = 10); 
```

Go back to [Contents](#contents).

## SQL INSERT INTO SELECT

* INSERT INTO SELECT

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers;
```

* INSERT INTO SELECT with WHERE

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers WHERE Country='Germany';
```

Go back to [Contents](#contents).

## SQL CASE

* CASE 1

```sql
SELECT OrderID, Quantity, 
CASE WHEN Quantity > 30 THEN "The quantity is greater than 30"
WHEN Quantity = 30 THEN "The quantity is 30"
ELSE "The quantity is under 30"
END AS QuantityText
FROM OrderDetails;
```

* CASE 2

```sql
SELECT CustomerName, City, Country FROM Customers
ORDER BY (CASE
WHEN City IS NULL THEN Country
ELSE City
END);
```

Go back to [Contents](#contents).

## SQL Comments

* Single Line Comments

```sql
-- Select all:
SELECT * FROM Customers;
```

* Single Line Comments At The End Of a Line

```sql
SELECT * FROM Customers -- WHERE City='Toronto';
```

* Multi-line Comments

```sql
/*Select all the columns
of all the records
in the Customers table:*/
SELECT * FROM Customers;
```

Go back to [Contents](#contents).

## SQL Database

### SQL Create DB

```sql
CREATE DATABASE testDB;
```

### SQL DROP DB

```sql
DROP DATABASE testDB;
```

### SQL Backup DB

```sql
BACKUP DATABASE testDB TO DISK = 'D:\backups\testDB.bak';
```

#### SQL Backup with differential

**Tip:** A differential back up reduces the back up time (since only the changes are backed up).

```sql
BACKUP DATABASE testDB TO DISK = 'D:\backups\testDB.bak' WITH DIFFERENTIAL;
```

### SQL Create Table

```sql
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```

#### Create Table Using Another Table

```sql
CREATE TABLE TestTable AS
SELECT customername, contactname FROM customers;
```

### SQL Drop Table

```sql
DROP TABLE Persons;
```

### SQL Alter Table

```sql
ALTER TABLE Customers ADD Email varchar(255);
```

#### ALTER TABLE - DROP COLUMN

```sql
ALTER TABLE Customers
DROP COLUMN Email;
```

#### ALTER TABLE - ALTER/MODIFY COLUMN

**SQL Server / MS Access:**

```sql
ALTER TABLE table_name
ALTER COLUMN column_name datatype;
```

**My SQL / Oracle (prior version 10G):**

```sql
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

**My SQL / Oracle (prior version 10G):**

```sql
ALTER TABLE table_name
MODIFY column_name datatype;
```

### SQL Constraints

* The following constraints are commonly used in SQL:

	* **NOT NULL** Ensures that a column cannot have a NULL value

	* **UNIQUE** Ensures that all values in a column are different
	* **PRIMARY KEY** A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
	* **FOREIGN KEY** Uniquely identifies a row/record in another table
	* **CHECK** Ensures that all values in a column satisfies a specific condition
	* **DEFAULT** Sets a default value for a column when no value is specified
	* **INDEX** Used to create and retrieve data from the database very quickly

### SQL Not Null

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

#### SQL NOT NULL on ALTER TABLE

```sql
ALTER TABLE Persons MODIFY Age int NOT NULL;
);
```

### SQL Unique

The following SQL creates a UNIQUE constraint on the "ID" column when the "Persons" table is created:

**SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

**MySQL:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```

To name a UNIQUE constraint, and to define a UNIQUE constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT UC_Person UNIQUE (ID,LastName)
);
```

#### SQL UNIQUE Constraint on ALTER TABLE

To create a UNIQUE constraint on the "ID" column when the table is already created, use the following SQL:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons ADD UNIQUE (ID);
```

To name a UNIQUE constraint, and to define a UNIQUE constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons ADD CONSTRAINT UC_Person UNIQUE (ID,LastName);
```

#### DROP a UNIQUE Constraint

**MySQL:**

```sql
ALTER TABLE Persons
DROP INDEX UC_Person;
```

**SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```

### SQL Primary Key

The PRIMARY KEY constraint uniquely identifies each record in a table.

#### SQL PRIMARY KEY on CREATE TABLE

The following SQL creates a PRIMARY KEY on the "ID" column when the "Persons" table is created:

**MySQL:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```

**SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

**Note:** In the example above there is only ONE PRIMARY KEY (PK_Person). However, the VALUE of the primary key is made up of TWO COLUMNS (ID + LastName).

* SQL PRIMARY KEY on ALTER TABLE

**MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```

To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```

**Note:** If you use the ALTER TABLE statement to add a primary key, the primary key column(s) must already have been declared to not contain NULL values (when the table was first created).

* DROP a PRIMARY KEY Constraint

**MySQL:**

```sql
ALTER TABLE Persons
DROP PRIMARY KEY;
```

**SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```

### SQL Foreign Key

A FOREIGN KEY is a key used to link two tables together.

* SQL FOREIGN KEY on CREATE TABLE

**MySQL:**

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

**SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```

To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```

* SQL FOREIGN KEY on ALTER TABLE

**MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

* DROP a FOREIGN KEY Constraint

**MySQL:**

```sql
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```

**SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```

### SQL Check

The CHECK constraint is used to limit the value range that can be placed in a column.


* SQL CHECK on CREATE TABLE

**MySQL:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```

**SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);
```

To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```

* SQL CHECK on ALTER TABLE

** MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD CHECK (Age>=18);
```

To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns, use the following SQL syntax:

** MySQL / SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```

* DROP a CHECK Constraint

**SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
DROP CONSTRAINT CHK_PersonAge;
```

**MySQL:**

```sql
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```

### SQL Default

The DEFAULT constraint is used to provide a default value for a column.

* SQL DEFAULT on CREATE TABLE

**My SQL / SQL Server / Oracle / MS Access:**

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Toronto'
);
```

The DEFAULT constraint can also be used to insert system values, by using functions like GETDATE():

```sql
CREATE TABLE Orders (
    ID int NOT NULL,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT GETDATE()
);
```

#### SQL DEFAULT on ALTER TABLE

**MySQL:**

```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Montréal';
```

**SQL Server:**

```sql
ALTER TABLE Persons
ADD CONSTRAINT df_City
DEFAULT 'Montréal' FOR City;
```

**MS Access:**

```sql
ALTER TABLE Persons
ALTER COLUMN City SET DEFAULT 'Montréal';
```

Oracle:

```sql
ALTER TABLE Persons
MODIFY City DEFAULT 'Montréal';
```

#### DROP a DEFAULT Constraint

**MySQL:**

```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```

**SQL Server / Oracle / MS Access:**

```sql
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```

### SQL Index

The CREATE INDEX statement is used to create indexes in tables.

Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.

#### CREATE INDEX Example

```sql
CREATE INDEX idx_lastname ON Persons (LastName);
```

If you want to create an index on a combination of columns, you can list the column names within the parentheses, separated by commas:

```sql
CREATE INDEX idx_pname ON Persons (LastName, FirstName);
```

#### DROP INDEX Statement

**MS Access:**

```sql
DROP INDEX index_name ON table_name;
```

**SQL Server:**

```sql
DROP INDEX table_name.index_name;
```

**DB2/Oracle:**

```sql
DROP INDEX index_name;
```

**MySQL:**

```sql
ALTER TABLE table_name
DROP INDEX index_name;
```

### SQL Auto Increment

Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

**Syntax for MySQL**

```sql
CREATE TABLE Persons (
    Personid int NOT NULL AUTO_INCREMENT,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (Personid)
);
```

MySQL uses the AUTO_INCREMENT keyword to perform an auto-increment feature.

By default, the starting value for AUTO_INCREMENT is 1, and it will increment by 1 for each new record.

To let the AUTO_INCREMENT sequence start with another value, use the following SQL statement:

```sql
ALTER TABLE Persons AUTO_INCREMENT=100;
```

To insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):

```sql
INSERT INTO Persons (FirstName,LastName) VALUES ('Will','Smith');
```

**Syntax for SQL Server**

```sql
CREATE TABLE Persons (
    Personid int IDENTITY(1,1) PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

The MS SQL Server uses the IDENTITY keyword to perform an auto-increment feature.

In the example above, the starting value for IDENTITY is 1, and it will increment by 1 for each new record.

Tip: To specify that the "Personid" column should start at value 10 and increment by 5, change it to IDENTITY(10,5).

To insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):

```sql
INSERT INTO Persons (FirstName,LastName)
VALUES ('Will','Smith');
```
**Syntax for Access**

```sql
CREATE TABLE Persons (
    Personid AUTOINCREMENT PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

The MS Access uses the AUTOINCREMENT keyword to perform an auto-increment feature.

By default, the starting value for AUTOINCREMENT is 1, and it will increment by 1 for each new record.

**Tip:** To specify that the "Personid" column should start at value 10 and increment by 5, change the autoincrement to AUTOINCREMENT(10,5).

To insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):

```sql
INSERT INTO Persons (FirstName,LastName)
VALUES ('Will','Smith');
```

**Syntax for Oracle**

In Oracle the code is a little bit more tricky.

You will have to create an auto-increment field with the sequence object (this object generates a number sequence).

Use the following CREATE SEQUENCE syntax:

```sql
CREATE SEQUENCE seq_person
MINVALUE 1
START WITH 1
INCREMENT BY 1
CACHE 10;
```

The code above creates a sequence object called seq_person, that starts with 1 and will increment by 1. It will also cache up to 10 values for performance. The cache option specifies how many sequence values will be stored in memory for faster access.

To insert a new record into the "Persons" table, we will have to use the nextval function (this function retrieves the next value from seq_person sequence):

```sql
INSERT INTO Persons (Personid,FirstName,LastName)
VALUES (seq_person.nextval,'Will','Smith');
```

### SQL Dates

The most difficult part when working with dates is to be sure that the format of the date you are trying to insert, matches the format of the date column in the database.

As long as your data contains only the date portion, your queries will work as expected. However, if a time portion is involved, it gets more complicated.

#### SQL Date Data Types

**MySQL** comes with the following data types for storing a date or a date/time value in the database:
	* DATE - format YYYY-MM-DD
	* DATETIME - format: YYYY-MM-DD HH:MI:SS
	* TIMESTAMP - format: YYYY-MM-DD HH:MI:SS
	* YEAR - format YYYY or YY

**SQL Server** comes with the following data types for storing a date or a date/time value in the database:
	* DATE - format YYYY-MM-DD
	* DATETIME - format: YYYY-MM-DD HH:MI:SS
	* SMALLDATETIME - format: YYYY-MM-DD HH:MI:SS
	* TIMESTAMP - format: a unique number

**Note:** The date types are chosen for a column when you create a new table in your database!

```sql
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```

### SQL Views

In SQL, a view is a virtual table based on the result-set of an SQL statement.

A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

You can add SQL functions, WHERE, and JOIN statements to a view and present the data as if the data were coming from one single table.

#### SQL CREATE VIEW Examples

```sql
CREATE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = "Brazil";
```

We can query the view above as follows:

```sql
SELECT * FROM [Brazil Customers];
```

The following SQL creates a view that selects every product in the "Products" table with a price higher than the average price:

```sql
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```

We can query the view above as follows:

```sql
SELECT * FROM [Products Above Average Price];
```

#### SQL Updating a View

A view can be updated with the CREATE OR REPLACE VIEW command.

#### SQL CREATE OR REPLACE VIEW

```sql
CREATE OR REPLACE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName, City
FROM Customers
WHERE Country = "Brazil";
```

#### SQL Dropping a View

```sql
DROP VIEW [Brazil Customers];
```

### SQL Injection

SQL injection is a code injection technique that might destroy your database.

SQL injection is one of the most common web hacking techniques.

SQL injection is the placement of malicious code in SQL statements, via web page input.

#### SQL in Web Pages

SQL injection usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.

Look at the following example which creates a SELECT statement by adding a variable (txtUserId) to a select string. The variable is fetched from user input (getRequestString):

Example

```sql
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

Potential dangers of using user input in SQL statements.

* SQL Injection Based on 1=1 is Always True

Look at the example above again. The original purpose of the code was to create an SQL statement to select a user, with a given user id.

If there is nothing to prevent a user from entering "wrong" input, the user can enter some "smart" input like this:

```
UserId: 105 OR 1=1
```

Then, the SQL statement will look like this:

```sql
SELECT * FROM Users WHERE UserId = 105 OR 1=1;
```

The SQL above is valid and will return ALL rows from the "Users" table, since OR 1=1 is always TRUE.

Does the example above look dangerous? What if the "Users" table contains names and passwords?

The SQL statement above is much the same as this:

```sql
SELECT UserId, Name, Password FROM Users WHERE UserId = 105 or 1=1;
```

A hacker might get access to all the user names and passwords in a database, by simply inserting 105 OR 1=1 into the input field.

* SQL Injection Based on ""="" is Always True

Here is an example of a user login on a web site:

```
Username:
John Doe

Password:
myPass
```

Example

```sql
uName = getRequestString("username");
uPass = getRequestString("userpassword");

sql = 'SELECT * FROM Users WHERE Name ="' + uName + '" AND Pass ="' + uPass + '"'
```

Result

```sql
SELECT * FROM Users WHERE Name ="Morgan Freeman" AND Pass ="myPass"
```

A hacker might get access to user names and passwords in a database by simply inserting " OR ""=" into the user name or password text box:

```
User Name:
" or ""="

Password:
" or ""="
```

The code at the server will create a valid SQL statement like this:

Result
```sql
SELECT * FROM Users WHERE Name ="" or ""="" AND Pass ="" or ""=""
```

The SQL above is valid and will return all rows from the "Users" table, since OR ""="" is always TRUE.

* SQL Injection Based on Batched SQL Statements 

Most databases support batched SQL statement.

A batch of SQL statements is a group of two or more SQL statements, separated by semicolons.

The SQL statement below will return all rows from the "Users" table, then delete the "Suppliers" table.

Example

```sql
SELECT * FROM Users; DROP TABLE Suppliers
```

Look at the following example:

```sql
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

And the following input:

```
User id: 105; DROP TABLE Suppliers
```

The valid SQL statement would look like this:

```sql
SELECT * FROM Users WHERE UserId = 105; DROP TABLE Suppliers;
```

#### Use SQL Parameters for Protection

To protect a web site from SQL injection, you can use SQL parameters.

SQL parameters are values that are added to an SQL query at execution time, in a controlled manner.

ASP.NET Razor Example

```sql
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = @0";
db.Execute(txtSQL,txtUserId);
```

Note that parameters are represented in the SQL statement by a @ marker.

The SQL engine checks each parameter to ensure that it is correct for its column and are treated literally, and not as part of the SQL to be executed.

Another Example

```sql
txtNam = getRequestString("CustomerName");
txtAdd = getRequestString("Address");
txtCit = getRequestString("City");
txtSQL = "INSERT INTO Customers (CustomerName,Address,City) Values(@0,@1,@2)";
db.Execute(txtSQL,txtNam,txtAdd,txtCit);
```

#### Examples

The following examples shows how to build parameterized queries in some common web languages.

SELECT STATEMENT IN ASP.NET:

```sql
txtUserId = getRequestString("UserId");
sql = "SELECT * FROM Customers WHERE CustomerId = @0";
command = new SqlCommand(sql);
command.Parameters.AddWithValue("@0",txtUserID);
command.ExecuteReader();
```

INSERT INTO STATEMENT IN ASP.NET:

```sql
txtNam = getRequestString("CustomerName");
txtAdd = getRequestString("Address");
txtCit = getRequestString("City");
txtSQL = "INSERT INTO Customers (CustomerName,Address,City) Values(@0,@1,@2)";
command = new SqlCommand(txtSQL);
command.Parameters.AddWithValue("@0",txtNam);
command.Parameters.AddWithValue("@1",txtAdd);
command.Parameters.AddWithValue("@2",txtCit);
command.ExecuteNonQuery();
```

INSERT INTO STATEMENT IN PHP:

```php
$stmt = $dbh->prepare("INSERT INTO Customers (CustomerName,Address,City)
VALUES (:nam, :add, :cit)");
$stmt->bindParam(':nam', $txtNam);
$stmt->bindParam(':add', $txtAdd);
$stmt->bindParam(':cit', $txtCit);
$stmt->execute();
```

### SQL Hosting

If you want your web site to be able to store and retrieve data from a database, your web server should have access to a database-system that uses the SQL language.

If your web server is hosted by an Internet Service Provider (ISP), you will have to look for SQL hosting plans.

The most common SQL hosting databases are MS SQL Server, Oracle, MySQL, and MS Access.

#### MS SQL Server

Microsoft's SQL Server is a popular database software for database-driven web sites with high traffic.

SQL Server is a very powerful, robust and full featured SQL database system.

#### Oracle

Oracle is also a popular database software for database-driven web sites with high traffic.

Oracle is a very powerful, robust and full featured SQL database system.

#### MySQL

MySQL is also a popular database software for web sites.

MySQL is a very powerful, robust and full featured SQL database system.

MySQL is an inexpensive alternative to the expensive Microsoft and Oracle solutions.

#### Access

When a web site requires only a simple database, Microsoft Access can be a solution.

Access is not well suited for very high-traffic, and not as powerful as MySQL, SQL Server, or Oracle.

Go back to [Contents](#contents).
