# SQL Server and T-SQL

## Content

### Module 1: Introduction to SQL Server

1. **Introduction to Databases**
   - What is a database?
   - Types of databases
   - Introduction to SQL Server

2. **SQL Server Architecture**
   - SQL Server components
   - SQL Server services
   - Database files and filegroups

---

### Module 2: SQL Basics

1. **Introduction to T-SQL**
   - SQL syntax and structure
   - Data types in SQL Server

2. **Basic Queries**
   - SELECT statements
   - Filtering data with WHERE clause
   - Sorting data with ORDER BY

3. **Joins and Subqueries**
   - Inner join, left join, right join, full join
   - Cross join
   - Subqueries and correlated subqueries

4. **Basic Data Manipulation**
   - INSERT, UPDATE, DELETE statements

---

### Module 3: Advanced SQL Queries

1. **Advanced SELECT Statements**
   - GROUP BY and HAVING clauses
   - Using aggregate functions (SUM, AVG, COUNT, etc.)

2. **Advanced Joins and Set Operations**
   - Self-joins
   - UNION, INTERSECT, EXCEPT

3. **Window Functions**
   - Introduction to window functions
   - ROW_NUMBER(), RANK(), DENSE_RANK(), NTILE()
   - Aggregate window functions

4. **Common Table Expressions (CTEs)**
   - Introduction to CTEs
   - Recursive CTEs

---

### Module 4: SQL Server Programming

1. **Stored Procedures**
   - Creating and executing stored procedures
   - Input and output parameters

2. **User-Defined Functions**
   - Scalar functions
   - Table-valued functions

3. **Triggers**
   - Introduction to triggers
   - AFTER and INSTEAD OF triggers

4. **Views**
   - Creating and managing views
   - Indexed views

---

### Module 1: Introduction to SQL Server

#### 1. Introduction to Databases

- **What is a database?** : Definition: A database is a structured collection of data that can be easily accessed, managed, and updated.

- **Types of databases**
  - **Relational Databases:**
    - Structure: Tables, rows, and columns.
    - Examples: SQL Server, MySQL, PostgreSQL, Oracle Database.
  - **Non-Relational (NoSQL) Databases:**
    - Structure: Document, key-value, wide-column, graph.
    - Examples: MongoDB, Cassandra, Redis.
  - **In-Memory Databases:**
    - Usage: Fast data processing, real-time applications.
    - Examples: Redis, Memcached.
  - **Cloud Databases:**
    - Deployment: Managed services in the cloud.
    - Examples: Amazon RDS, Google Cloud SQL, Azure SQL Database.

- **Introduction to SQL Server**
  - Overview: SQL Server is a relational database management system (RDBMS) developed by Microsoft.
  - Key Features: Data storage, querying, security, data integration, business intelligence.
  - Editions: Express, Standard, Enterprise, Developer.

#### 2. SQL Server Architecture

- **SQL Server components**
  - **Database Engine:**
    - Core service for storing, processing, and securing data.
    - Supports transaction processing, data warehousing, and analytics.
  - **SQL Server Agent:**
    - Job scheduling and automation.
    - Execute scheduled tasks (backups, maintenance).
  - **SQL Server Integration Services (SSIS):**
    - Data integration and ETL (Extract, Transform, Load).
    - Import and export data between different sources.
  - **SQL Server Reporting Services (SSRS):**
    - Design, deploy, and manage reports.
    - Interactive and printed reports.
  - **SQL Server Analysis Services (SSAS):**
    - Online Analytical Processing (OLAP) and data mining.
    - Create and manage multidimensional models.

- **SQL Server services**
  - **SQL Server Database Engine Service:**
    - Handles database operations (queries, transactions).
    - Installed as a Windows service.
  - **SQL Server Agent Service:**
    - Manages scheduled jobs.
    - Essential for automation tasks.
  - **SQL Server Browser Service:**
    - Helps clients connect to the correct instance of SQL Server.
    - Manages instance discovery and connection redirection.
  - **SQL Server Integration Services (SSIS) Service:**
    - Executes and manages SSIS packages.
  - **SQL Server Reporting Services (SSRS) Service:**
    - Manages report server functions.

- **Database files and filegroups**
  - **Database Files:**
    - **Primary Data File (.mdf):** Contains the startup information and the main data.
    - **Secondary Data Files (.ndf):** Optional, used to spread data across multiple files.
    - **Transaction Log File (.ldf):** Records all transactions and database modifications.
  - **Filegroups:**
    - Logical grouping of data files.
    - Primary Filegroup: Contains the primary data file and any secondary files not assigned to other filegroups.
    - User-defined Filegroups: Created for managing data and optimizing performance.

---

### Module 2: SQL Basics

#### 1. Introduction to T-SQL

- **SQL syntax and structure**
  - **Basic SQL Statement Structure:**
    - Keywords: SELECT, INSERT, UPDATE, DELETE, FROM, WHERE, JOIN.
    - Statement terminator: `;` (optional but recommended).
    - Comments: `--` for single line, `/* ... */` for multi-line.
  - **Basic Query Structure:**

    ```sql
    SELECT column1, column2
    FROM table_name
    WHERE condition
    ORDER BY column1;
    ```

- **Data types in SQL Server**
  - **Numeric Data Types:**
    - `INT`, `FLOAT`, `DECIMAL`, `NUMERIC`, `MONEY`
  - **String Data Types:**
    - `CHAR`, `VARCHAR`, `TEXT`, `NCHAR`, `NVARCHAR`, `NTEXT`
  - **Date and Time Data Types:**
    - `DATE`, `TIME`, `DATETIME`, `DATETIME2`, `SMALLDATETIME`, `TIMESTAMP`
  - **Other Data Types:**
    - `BIT`, `BINARY`, `VARBINARY`, `UNIQUEIDENTIFIER`

#### 2. Basic Queries

**Objective:** Learn how to retrieve and manipulate data using basic SQL queries.

- **SELECT statements**

    ```sql
    SELECT column1, column2
    FROM table_name;
    ```

- **Filtering data with WHERE clause**

    ```sql
    SELECT column1, column2
    FROM table_name
    WHERE condition;
    ```

- **Sorting data with ORDER BY**

    ```sql
    SELECT column1, column2
    FROM table_name
    ORDER BY column1 [ASC|DESC];
    ```

#### 3. Joins and Subqueries

**Objective:** Understand how to combine data from multiple tables and use subqueries to filter and aggregate data.

- **Inner join, left join, right join, full join**
  - **Inner Join:**

    ```sql
    SELECT a.column1, b.column2
    FROM table1 a
    INNER JOIN table2 b ON a.id = b.id;
    ```

  - **Left Join:**

    ```sql
    SELECT a.column1, b.column2
    FROM table1 a
    LEFT JOIN table2 b ON a.id = b.id;
    ```

  - **Right Join:**

    ```sql
    SELECT a.column1, b.column2
    FROM table1 a
    RIGHT JOIN table2 b ON a.id = b.id;
    ```

  - **Full Join:**

    ```sql
    SELECT a.column1, b.column2
    FROM table1 a
    FULL JOIN table2 b ON a.id = b.id;
    ```

- **Cross join**

    ```sql
    SELECT a.column1, b.column2
    FROM table1 a
    CROSS JOIN table2 b;
    ```

- **Subqueries and correlated subqueries**

    - **Subqueries Goal** : **Goal:** A query nested inside another query to provide results that will be used by the outer query. Subqueries can return single values, lists, or entire result sets. (Example Use: Fetch data to be used in a WHERE clause or SELECT list. )

    - **Correlated Subqueries Goal** : **Goal:** A subquery that references columns from the outer query, allowing it to be evaluated once for each row processed by the outer query. (**Example Use:** Perform row-by-row calculations or comparisons, such as finding rows where a certain condition holds true in a related table. )

  - **Subquery Example:**

    ```sql
    SELECT column1
    FROM table1
    WHERE column2 = (SELECT column2 FROM table2 WHERE condition);
    ```

  - **Correlated Subquery Example:**

    ```sql
    SELECT a.column1
    FROM table1 a
    WHERE a.column2 = (SELECT MAX(b.column2) FROM table2 b WHERE b.column1 = a.column1);
    ```

#### 4. Basic Data Manipulation

- **INSERT statements**

    ```sql
    INSERT INTO table_name (column1, column2)
    VALUES (value1, value2);
    ```

- **UPDATE statements**

    ```sql
    UPDATE table_name
    SET column1 = value1, column2 = value2
    WHERE condition;
    ```

- **DELETE statements**

    ```sql
    DELETE FROM table_name
    WHERE condition;
    ```

---

### Module 3: Advanced SQL Queries

#### 1. Advanced SELECT Statements

**Objective:** Learn advanced techniques for querying data, including grouping and aggregate functions.

- **GROUP BY and HAVING clauses**

    ```sql
    SELECT column1, COUNT(*)
    FROM table_name
    GROUP BY column1
    HAVING COUNT(*) > 1;
    ```

- **Using aggregate functions (SUM, AVG, COUNT, etc.)**

    ```sql
    SELECT SUM(column) FROM table_name;
    SELECT AVG(column) FROM table_name;
    SELECT COUNT(column) FROM table_name;
    SELECT MAX(column) FROM table_name;
    SELECT MIN(column) FROM table_name;
    ```

#### 2. Advanced Joins and Set Operations

- **Self-joins**

    ```sql
    SELECT a.column1, b.column2
    FROM table_name a, table_name b
    WHERE a.id = b.id;
    ```

- **UNION, INTERSECT, EXCEPT**
  - **UNION:**

    **Goal:** Combine the results of two or more SELECT queries into a single result set, eliminating duplicate rows. ( Example Use: Retrieve all rows from multiple tables with the same structure).

    ```sql
    SELECT column1 FROM table1
    UNION
    SELECT column1 FROM table2;
    ```

  - **INTERSECT:**

    **Goal:** Return only the rows that are common to the results of two SELECT queries. (Example Use: Find common entries between two tables or result sets).

    ```sql
    SELECT column1 FROM table1
    INTERSECT
    SELECT column1 FROM table2;
    ```

  - **EXCEPT:**

    **Goal:** Return the rows from the first SELECT query that are not present in the second SELECT query. (Example Use: Identify records in one table that do not exist in another.)

    ```sql
    SELECT column1 FROM table1
    EXCEPT
    SELECT column1 FROM table2;
    ```

#### 3. Window Functions

**Goal:** Perform calculations across a set of table rows that are related to the current row without collapsing the result set. They are often used for ranking, cumulative totals, moving averages, and other similar calculations.

**Example Use:** Calculate a running total or assign a unique rank to each row within a partition of data.

- **Introduction to window functions**


    ```sql
    SELECT column1, 
           ROW_NUMBER() OVER (PARTITION BY column2 ORDER BY column3) AS row_num
    FROM table_name;
    ```

- **ROW_NUMBER(), RANK(), DENSE_RANK(), NTILE()**

    ```sql
    SELECT column1, 
           ROW_NUMBER() OVER (ORDER BY column2) AS row_num
    FROM table_name;

    SELECT column1, 
           RANK() OVER (ORDER BY column2) AS rank
    FROM table_name;

    SELECT column1, 
           DENSE_RANK() OVER (ORDER BY column2) AS dense_rank
    FROM table_name;

    SELECT column1, 
           NTILE(4) OVER (ORDER BY column2) AS quartile
    FROM table_name;
    ```

- **Aggregate window functions**

    ```sql
    SELECT column1, 
           SUM(column2) OVER (PARTITION BY column3) AS sum_column2
    FROM table_name;

    SELECT column1, 
           AVG(column2) OVER (PARTITION BY column3) AS avg_column2
    FROM table_name;
    ```

#### 4. Common Table Expressions (CTEs)

**Goal:** Simplify complex queries by breaking them into simpler subqueries that can be referenced within the main query. CTEs can also be recursive, allowing for operations on hierarchical data.

- **Introduction to CTEs**

    ```sql
    WITH CTE AS (
        SELECT column1, column2
        FROM table_name
        WHERE condition
    )
    SELECT * FROM CTE;
    ```

- **Recursive CTEs**

    ```sql
    WITH CTE AS (
        SELECT column1, column2
        FROM table_name
        WHERE condition
        UNION ALL
        SELECT column1, column2
        FROM table_name
        INNER JOIN CTE ON table_name.column1 = CTE.column1
    )
    SELECT * FROM CTE;
    ```

---

### Module 4: SQL Server Programming

#### 1. Stored Procedures

**Definition:** A stored procedure is a precompiled collection of one or more SQL statements stored under a name and processed as a unit. They can be invoked by name and can accept input parameters, return output parameters, and produce a result set.

**Goal:** To encapsulate frequently used or complex queries and operations, improve performance through precompilation, and enhance security by controlling access to data.

- **Creating and Executing Stored Procedures**
  - **Syntax:**

    ```sql
    CREATE PROCEDURE procedure_name
    AS
    BEGIN
        SQL statements
    END;
    ```

  - **Example:**

    ```sql
    CREATE PROCEDURE GetEmployeeDetails
    AS
    BEGIN
        SELECT * FROM Employees;
    END;
    ```

  - **Executing:**

    ```sql
    EXEC GetEmployeeDetails;
    ```

- **Input and Output Parameters**
  - **Syntax:**

    ```sql
    CREATE PROCEDURE procedure_name
    @input_param INT,
    @output_param INT OUTPUT
    AS
    BEGIN
        SQL statements
    END;
    ```

  - **Example:**

    ```sql
    CREATE PROCEDURE GetEmployeeByID
    @EmployeeID INT,
    @EmployeeName NVARCHAR(50) OUTPUT
    AS
    BEGIN
        SELECT @EmployeeName = Name
        FROM Employees
        WHERE ID = @EmployeeID;
    END;
    ```

  - **Executing with Parameters:**

    ```sql
    DECLARE @Name NVARCHAR(50);
    EXEC GetEmployeeByID @EmployeeID = 1, @EmployeeName = @Name OUTPUT;
    SELECT @Name;
    ```

#### 2. User-Defined Functions (UDFs)

**Definition:** UDFs are functions created by the user to encapsulate reusable code for calculations or data transformations. They can be scalar (returning a single value) or table-valued (returning a table).

**Goal:** To modularize code for reuse, maintainability, and to simplify complex calculations and operations in queries.

- **Scalar Functions**
  - **Definition:** Returns a single value based on the input parameters.
  - **Syntax:**

    ```sql
    CREATE FUNCTION function_name (@param1 INT)
    RETURNS INT
    AS
    BEGIN
        RETURN @param1 * 2;
    END;
    ```

  - **Example:**

    ```sql
    CREATE FUNCTION GetDouble (@Number INT)
    RETURNS INT
    AS
    BEGIN
        RETURN @Number * 2;
    END;
    ```

  - **Usage:**

    ```sql
    SELECT dbo.GetDouble(5);
    ```

- **Table-Valued Functions**
  - **Definition:** Returns a table data type that can be used like a table in queries.
  - **Syntax:**

    ```sql
    CREATE FUNCTION function_name (@param1 INT)
    RETURNS TABLE
    AS
    RETURN
    (
        SELECT columns
        FROM table_name
        WHERE condition
    );
    ```

  - **Example:**

    ```sql
    CREATE FUNCTION GetEmployeesByDepartment (@DepartmentID INT)
    RETURNS TABLE
    AS
    RETURN
    (
        SELECT * FROM Employees
        WHERE DepartmentID = @DepartmentID
    );
    ```

  - **Usage:**

    ```sql
    SELECT * FROM dbo.GetEmployeesByDepartment(1);
    ```

#### 3. Triggers

**Definition:** Triggers are special types of stored procedures that automatically execute (or "fire") when specific actions occur in the database, such as INSERT, UPDATE, or DELETE.

**Goal:** To enforce business rules, maintain data integrity, and perform automatic actions in response to changes in the database.

- **Introduction to Triggers**
  - **Definition:** Automatically invoked in response to certain events on a table or view.
  - **Types:** DML Triggers (Data Manipulation Language) and DDL Triggers (Data Definition Language).

- **AFTER and INSTEAD OF Triggers**
  - **AFTER Triggers:** Execute after the triggering action has been completed.
    - **Syntax:**

      ```sql
      CREATE TRIGGER trigger_name
      ON table_name
      AFTER INSERT, UPDATE, DELETE
      AS
      BEGIN
          SQL statements
      END;
      ```

    - **Example:**

      ```sql
      CREATE TRIGGER trgAfterInsert
      ON Employees
      AFTER INSERT
      AS
      BEGIN
          PRINT 'Record Inserted';
      END;
      ```

  - **INSTEAD OF Triggers:** Execute in place of the triggering action, allowing custom actions.
    - **Syntax:**

      ```sql
      CREATE TRIGGER trigger_name
      ON table_name
      INSTEAD OF INSERT, UPDATE, DELETE
      AS
      BEGIN
          SQL statements
      END;
      ```

    - **Example:**

      ```sql
      CREATE TRIGGER trgInsteadOfInsert
      ON Employees
      INSTEAD OF INSERT
      AS
      BEGIN
          PRINT 'Insert operation intercepted';
      END;
      ```

#### 4. Views

**Definition:** A view is a virtual table based on the result-set of a SELECT query. Views do not store data physically but display data from one or more tables.

**Goal:** To simplify complex queries, enhance security by restricting access to certain columns, and present data in a specific format.

- **Creating and Managing Views**
  - **Syntax:**

    ```sql
    CREATE VIEW view_name AS
    SELECT columns
    FROM table_name
    WHERE condition;
    ```

  - **Example:**

    ```sql
    CREATE VIEW vwEmployees AS
    SELECT FirstName, LastName, Department
    FROM Employees
    WHERE IsActive = 1;
    ```

- **Indexed Views**
  - **Definition:** Views that have a unique clustered index, making the data physically stored and improving performance for certain types of queries.
  - **Syntax:**

    ```sql
    CREATE VIEW view_name WITH SCHEMABINDING AS
    SELECT columns
    FROM table_name
    WHERE condition;

    CREATE UNIQUE CLUSTERED INDEX index_name
    ON view_name (column);
    ```

  - **Example:**

    ```sql
    CREATE VIEW vwActiveEmployees WITH SCHEMABINDING AS
    SELECT FirstName, LastName, Department
    FROM dbo.Employees
    WHERE IsActive = 1;

    CREATE UNIQUE CLUSTERED INDEX idxActiveEmployees
    ON vwActiveEmployees (FirstName, LastName);
    ```
