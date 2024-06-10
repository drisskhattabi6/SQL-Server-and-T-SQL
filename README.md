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

**Transact-SQL (T-SQL) Definition:**

Transact-SQL, commonly known as T-SQL, is an extension of SQL (Structured Query Language) used primarily with Microsoft SQL Server and Sybase ASE (Adaptive Server Enterprise). T-SQL adds procedural programming capabilities to SQL, allowing for more complex and robust database manipulation and management. These capabilities include control-of-flow constructs (such as IF, WHILE), error handling, and support for variables, along with enhanced functions for string and date manipulation.

**Key Features of T-SQL:**

1. **Procedural Programming Constructs:**
    - **Control-of-Flow:** Includes statements like `IF...ELSE`, `WHILE`, and `BEGIN...END` for controlling the flow of execution.
    - **Error Handling:** Uses `TRY...CATCH` blocks to handle errors gracefully within code blocks.
    - **Variables:** Supports declaring and using variables to store temporary data.

2. **Enhanced Functions:**
   - **String Functions:** Functions like `CHARINDEX`, `PATINDEX`, `LEN`, `SUBSTRING`, and more for detailed string manipulation.
   - **Date Functions:** Functions like `GETDATE`, `DATEADD`, `DATEDIFF`, and `FORMAT` for handling date and time values.

3. **Stored Procedures and Functions:**
    - **Stored Procedures:** Precompiled collections of SQL statements that can accept parameters and be executed as a single unit.
    - **User-Defined Functions (UDFs):** Custom functions created by users to perform calculations or data transformations, returning either scalar values or tables.

4. **Triggers:**
    - Special types of stored procedures that automatically execute in response to certain events (INSERT, UPDATE, DELETE) on a table or view.

5. **Common Table Expressions (CTEs):**
    - Temporary result sets that can be referenced within a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement, simplifying complex queries and enabling recursive queries.

6. **Window Functions:**

    - Functions that perform calculations across a set of table rows related to the current row without collapsing the result set, useful for ranking, running totals, and other analytical operations.

**Goal of T-SQL:**
    To provide a powerful and flexible scripting environment for SQL Server, enabling developers and database administrators to perform complex data manipulation, transaction management, and procedural logic within their databases. T-SQL extends the capabilities of standard SQL, making it a robust tool for managing and querying relational databases efficiently.

## **the different types of variables in T-SQL**

In Transact-SQL (T-SQL), variables can be categorized into different types based on their scope, usage, and functionality. Here are the different types of variables in T-SQL:

### 1. Scalar Variables

**Definition:** Scalar variables are used to store a single data value of a specific type, such as an integer, a string, a date, etc.

**Common Data Types:**

- **INT:** Stores integer values.
- **FLOAT:** Stores floating-point numbers.
- **DECIMAL:** Stores fixed precision and scale numbers.
- **MONEY:** Stores currency values.
- **CHAR / VARCHAR:** Stores fixed or variable-length strings.
- **NCHAR / NVARCHAR:** Stores Unicode strings.
- **DATETIME:** Stores date and time values.
- **BIT:** Stores Boolean values (0 or 1).

**Example:**

```sql
DECLARE @EmployeeID INT;
DECLARE @EmployeeName NVARCHAR(50);
DECLARE @HireDate DATETIME;
DECLARE @IsActive BIT;

SET @EmployeeID = 1;
SET @EmployeeName = 'John Doe';
SET @HireDate = '2023-01-01';
SET @IsActive = 1;
```

### 2. Table Variables

**Definition:** Table variables are used to store a result set in the form of a table. They are similar to temporary tables but have some differences in scope and performance characteristics.

**Example:**

```sql
DECLARE @EmployeeTable TABLE (
    EmployeeID INT,
    EmployeeName NVARCHAR(50),
    HireDate DATETIME
);

INSERT INTO @EmployeeTable (EmployeeID, EmployeeName, HireDate)
VALUES (1, 'John Doe', '2023-01-01');

SELECT * FROM @EmployeeTable;
```

### 3. System Variables

**Definition:** System variables, also known as system functions, provide information about the SQL Server environment and the state of the current session.

**Common System Variables:**

- **@@ROWCOUNT:** Returns the number of rows affected by the last statement.
- **@@IDENTITY:** Returns the last-inserted identity value.
- **@@ERROR:** Returns the error number for the last Transact-SQL statement executed.
- **@@TRANCOUNT:** Returns the number of active transactions.

**Example:**

```sql
-- Example using @@ROWCOUNT
UPDATE Employees
SET IsActive = 1
WHERE HireDate < '2023-01-01';

SELECT @@ROWCOUNT AS RowsAffected;

-- Example using @@IDENTITY
INSERT INTO Employees (EmployeeName, HireDate, IsActive)
VALUES ('Jane Smith', '2024-01-01', 1);

SELECT @@IDENTITY AS LastInsertedID;
```

### 4. Global Variables

**Definition:** Global variables, also known as global functions, provide information about the global state of the SQL Server instance. These are prefixed with `@@` and are predefined by SQL Server.

**Common Global Variables:**

- **@@VERSION:** Returns the version of SQL Server.
- **@@SERVERNAME:** Returns the name of the local server.
- **@@MAX_CONNECTIONS:** Returns the maximum number of simultaneous user connections allowed.
- **@@LANGUAGE:** Returns the language currently in use.

**Example:**

```sql
SELECT @@VERSION AS SQLServerVersion;
SELECT @@SERVERNAME AS ServerName;
SELECT @@MAX_CONNECTIONS AS MaxConnections;
SELECT @@LANGUAGE AS CurrentLanguage;
```

### 5. Cursor Variables

**Definition:** Cursor variables are used to handle cursors, which are database objects used to retrieve data row-by-row from a result set.

**Example:**

```sql
DECLARE @EmployeeCursor CURSOR;
DECLARE @EmployeeID INT, @EmployeeName NVARCHAR(50);

SET @EmployeeCursor = CURSOR FOR
SELECT EmployeeID, EmployeeName
FROM Employees;

OPEN @EmployeeCursor;
FETCH NEXT FROM @EmployeeCursor INTO @EmployeeID, @EmployeeName;

WHILE @@FETCH_STATUS = 0
BEGIN
    PRINT 'Employee ID: ' + CAST(@EmployeeID AS NVARCHAR(10)) + ', Employee Name: ' + @EmployeeName;
    FETCH NEXT FROM @EmployeeCursor INTO @EmployeeID, @EmployeeName;
END;

CLOSE @EmployeeCursor;
DEALLOCATE @EmployeeCursor;
```

### Summary

- **Scalar Variables:** Store single values of specific data types.
- **Table Variables:** Store result sets in table format.
- **System Variables:** Provide information about the SQL Server environment and session state.
- **Global Variables:** Provide global information about the SQL Server instance.
- **Cursor Variables:** Manage cursors for row-by-row data retrieval.

These different types of variables allow for flexible and powerful data handling and manipulation in T-SQL.

## **Declare a Variable in T-SQL**

In Transact-SQL (T-SQL), variables are declared using the `DECLARE` statement. Variables are used to store temporary data for manipulation and can be of different data types. Here is how you declare and use a variable in T-SQL:

### Syntax

```sql
DECLARE @variable_name datatype;
```

### Examples

1. **Declaring a Single Variable:**

   ```sql
   DECLARE @MyVariable INT;
   ```

2. **Declaring Multiple Variables:**

   ```sql
   DECLARE @MyVariable1 INT, @MyVariable2 NVARCHAR(50), @MyVariable3 DATETIME;
   ```

3. **Setting a Value to a Variable:**

   ```sql
   DECLARE @MyVariable INT;
   SET @MyVariable = 10;
   ```

4. **Using SELECT to Set a Value:**

   ```sql
   DECLARE @MyVariable INT;
   SELECT @MyVariable = 10;
   ```

5. **Using Variables in a Query:**

   ```sql
   DECLARE @EmployeeID INT;
   SET @EmployeeID = 1;
   
   SELECT FirstName, LastName
   FROM Employees
   WHERE ID = @EmployeeID;
   ```

### Detailed Example:

```sql
-- Declare variables
DECLARE @FirstName NVARCHAR(50), @LastName NVARCHAR(50), @EmployeeID INT;

-- Set values to variables
SET @FirstName = 'John';
SET @LastName = 'Doe';
SET @EmployeeID = 123;

-- Use variables in a query
SELECT @FirstName AS FirstName, @LastName AS LastName, @EmployeeID AS EmployeeID;

-- Another example with data retrieval
DECLARE @DepartmentID INT;
SET @DepartmentID = 2;

SELECT EmployeeID, EmployeeName
FROM Employees
WHERE DepartmentID = @DepartmentID;
```

### Points to Remember:

- **Naming Conventions:** Variable names in T-SQL start with an `@` symbol.
- **Data Types:** The variable's data type must be specified at the time of declaration.
- **Scope:** The scope of a variable is limited to the batch, stored procedure, or function in which it is declared.

Using variables can help make your T-SQL scripts more flexible and easier to manage, especially when dealing with dynamic queries or performing iterative operations.

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

----

==================  inserted  Table 

la table inserted est une table logique spéciale qui contient les lignes nouvellement insérées dans une opération de déclenchement INSERT, UPDATE ou DELETE. Cette table est accessible uniquement à l'intérieur du corps du déclencheur (Trigger) et ne peut pas être consultée directement en dehors du déclencheur.

==================   SET NOCOUNT ON  

La commande SET NOCOUNT ON est une instruction SQL qui spécifie que le nombre de lignes affectées par une instruction SQL ne doit pas être retourné en tant que résultat. Elle est souvent utilisée dans les déclencheurs pour éviter que les messages supplémentaires sur le nombre de lignes affectées ne soient renvoyés au client, ce qui peut améliorer les performances en réduisant le trafic réseau.

Dans le contexte d'un déclencheur, l'utilisation de SET NOCOUNT ON est facultative mais recommandée pour des raisons de performance. Cela évite que des messages supplémentaires ne soient envoyés au client chaque fois que le déclencheur est déclenché, ce qui peut ne pas être nécessaire pour les opérations de déclencheur qui n'ont pas besoin de renvoyer de résultats.

Donc, dans le déclencheur que je vous ai fourni précédemment, SET NOCOUNT ON est utilisé pour désactiver le renvoi du nombre de lignes affectées par les instructions SQL à des fins de performance.


----

### stored procedure in T-SQL

- **CREATE PROCEDURE** Statement: This is used to define and create the stored procedure. It specifies the procedure name, input parameters (if any), and the code block containing the procedure's logic.

- **Input Parameters**: These are optional parameters that are passed to the procedure for execution. They are specified within parentheses after the procedure name.

- **AS** Statement: This part of the procedure declaration indicates the beginning of the code block where the procedure's logic is defined.

- **BEGIN...END** Block: This block contains the main logic of the procedure. It consists of SQL statements, control-of-flow statements (like IF...ELSE, WHILE, etc.), variable declarations if needed, and calls to other stored procedures or functions.

- Variable Declarations: These are optional statements where you declare local variables that are used within the procedure for computation.

- Output Parameters: These are optional parameters that can be used to return values from the procedure back to the calling code.

- RETURN Statement: This statement is used to explicitly return from the procedure before its end.

- Error Handling: Error handling code can be included to handle exceptions or errors that occur during the execution of the procedure.

Here's a basic structure of a stored procedure in T-SQL:

``` sql
CREATE PROCEDURE [schema_name.]procedure_name 
    @parameter1 data_type1,
    @parameter2 data_type2,
    ...
AS
BEGIN
    -- Variable declarations
    DECLARE @variable1 data_type1;
    DECLARE @variable2 data_type2;

    -- Main logic of the procedure
    -- SQL statements, control-of-flow statements, etc.

    -- RETURN statement (optional)
    -- RETURN result;

    -- Error handling (optional)
    -- BEGIN TRY
    --     ...
    -- END TRY
    -- BEGIN CATCH
    --     ...
    -- END CATCH
END;
```

In this structure:

- schema_name: (Optional) The schema in which the procedure will be created.
- procedure_name: The name of the procedure.
- @parameter1, @parameter2, ...: Input parameters to the procedure.
- @variable1, @variable2, ...: Local variables used within the procedure.
- result: The value or result set returned by the procedure (if any).
- Error handling block (optional): Used to handle exceptions or errors that occur during the execution of the procedure.

-----

### stored function in T-SQL

- CREATE FUNCTION Statement: This is used to define and create the function. It specifies the function name, input parameters, return type, and the code block containing the function's logic.

- Input Parameters: These are optional parameters that are passed to the function for computation. They are specified within parentheses after the function name.

- Returns Clause: This part of the function declaration specifies the data type that the function will return. In T-SQL, the RETURNS keyword is used to define the return type.

- BEGIN...END Block: This block contains the main logic of the function. It consists of SQL statements, control-of-flow statements (like IF...ELSE, WHILE, etc.), and variable declarations if needed.

- Variable Declarations: These are optional statements where you declare local variables that are used within the function for computation.

- RETURN Statement: This statement is used to return the result of the function. It can return a single value, a table, or a result set, depending on the function's purpose.

Here's a basic structure of a stored function in T-SQL:

```sql
CREATE FUNCTION [schema_name.]function_name 
    (@parameter1 data_type1, @parameter2 data_type2, ...)
RETURNS return_data_type
AS
BEGIN
    -- Variable declarations
    DECLARE @variable1 data_type1;
    DECLARE @variable2 data_type2;

    -- Main logic of the function
    -- SQL statements, control-of-flow statements, etc.

    -- RETURN statement
    RETURN result;
END;
```

In this structure:

- schema_name: (Optional) The schema in which the function will be created.
- function_name: The name of the function.
- @parameter1, @parameter2, ...: Input parameters to the function.
- return_data_type: The data type that the function will return.
- @variable1, @variable2, ...: Local variables used within the function.
- result: The value or result set returned by the function.

---

Stored functions and stored procedures are both database objects that contain a set of SQL statements for performing a specific task. However, there are some key differences between the two:

1- Return Value:

- Stored Function: A stored function must return a value. It typically computes and returns a single scalar value (such as an integer, string, or date).
- Stored Procedure: A stored procedure does not have to return a value, although it can optionally return one or more result sets or output parameters.

2- Usage:

- Stored Function: Functions are typically used within SQL statements, such as in SELECT, WHERE, and ORDER BY clauses, or assigned to variables.
- Stored Procedure: Procedures are typically called as standalone units of work from within an application or another stored procedure.

3- Transaction Control:

- Stored Function: Functions cannot contain statements that directly modify database state (e.g., INSERT, UPDATE, DELETE), and they cannot perform transaction control operations like COMMIT or ROLLBACK.
- Stored Procedure: Procedures can contain statements that modify database state, and they can perform transaction control operations.

4- Input/Output Parameters:

- Stored Function: Functions can have input parameters but cannot have output parameters. The return value serves as the output.
- Stored Procedure: Procedures can have both input and output parameters.

5- Portability:

- Stored Function: Functions are often more portable across different database systems because they are typically used within SQL statements and adhere to SQL standards.
- Stored Procedure: Procedures may have syntax and behavior specific to the database system in which they are created, making them less portable.

6- Function Overloading:

- Stored Function: Some database systems support function overloading, allowing multiple functions with the same name but different parameter lists. This feature is not standard in SQL.
- Stored Procedure: Procedures do not support overloading in most database systems.

In summary, stored functions are designed primarily for computation and return a single value, while stored procedures are more versatile and can perform a wider range of tasks, including data modification and transaction control.

---

### T-SQL constructs

Sure, here are examples for each of the T-SQL constructs mentioned:

### IF...ELSE Statement

**Definition:** The `IF...ELSE` statement allows for conditional execution of T-SQL code blocks.

**Example:**

```sql
DECLARE @Score INT;
SET @Score = 85;

IF @Score >= 90
BEGIN
    PRINT 'Grade: A';
END
ELSE IF @Score >= 80
BEGIN
    PRINT 'Grade: B';
END
ELSE IF @Score >= 70
BEGIN
    PRINT 'Grade: C';
END
ELSE
BEGIN
    PRINT 'Grade: F';
END;
```

### CASE Statement

**Definition:** The `CASE` statement allows for conditional logic within a query.

**Example:**

```sql
DECLARE @Score INT;
SET @Score = 85;

SELECT 
    CASE
        WHEN @Score >= 90 THEN 'Grade: A'
        WHEN @Score >= 80 THEN 'Grade: B'
        WHEN @Score >= 70 THEN 'Grade: C'
        ELSE 'Grade: F'
    END AS Grade;
```

### WHILE Loop

**Definition:** The `WHILE` loop repeatedly executes a block of code as long as the specified condition is true.

**Example:**

```sql
DECLARE @Counter INT;
SET @Counter = 1;

WHILE @Counter <= 5
BEGIN
    PRINT 'Counter Value: ' + CAST(@Counter AS NVARCHAR(10));
    SET @Counter = @Counter + 1;
END;
```

### GOTO Statement

**Definition:** The `GOTO` statement transfers control to a specified label within the T-SQL code.

**Example:**

```sql
DECLARE @Counter INT;
SET @Counter = 1;

PRINT 'Start of the script';

StartLoop:
IF @Counter <= 5
BEGIN
    PRINT 'Counter Value: ' + CAST(@Counter AS NVARCHAR(10));
    SET @Counter = @Counter + 1;
    GOTO StartLoop;
END;

PRINT 'End of the script';
```

### WAITFOR Statement

**Definition:** The `WAITFOR` statement delays the execution of the next statement until a specified time or for a specified duration.

**Example:**

```sql
PRINT 'Wait for 9:12 AM';
WAITFOR TIME '09:12';
PRINT 'This message is printed at 9:12 AM';

-- Alternatively, waiting for a duration (e.g., 10 seconds)
PRINT 'Wait for 10 seconds';
WAITFOR DELAY '00:00:10';
PRINT 'This message is printed after a 10-second delay';
```

### Summary

- **IF...ELSE:** Conditional execution based on specified conditions.
- **CASE:** Conditional logic within a query.
- **WHILE:** Looping construct to execute code repeatedly while a condition is true.
- **GOTO:** Transfers control to a labeled section of code.
- **WAITFOR:** Delays the execution of the next statement until a specified time or for a specified duration.

These examples demonstrate the use of conditional, looping, and control flow constructs in T-SQL, providing powerful tools for managing and manipulating data in SQL Server.

----

### Transaction in T-SQL

**Definition:**
A transaction in T-SQL is a sequence of operations performed as a single logical unit of work. A transaction ensures that either all operations within the transaction are completed successfully, or none of them are, maintaining the integrity of the database. Transactions follow the ACID properties: Atomicity, Consistency, Isolation, and Durability.

### Syntax:

#### Basic Syntax

```sql
BEGIN TRANSACTION;
-- SQL statements go here
COMMIT TRANSACTION; -- or ROLLBACK TRANSACTION;
```

#### Key Statements:

- **BEGIN TRANSACTION:** Starts a new transaction.
- **COMMIT TRANSACTION:** Saves all changes made during the transaction.
- **ROLLBACK TRANSACTION:** Undoes all changes made during the transaction.

### Examples:

#### Example 1: Simple Transaction

```sql
BEGIN TRANSACTION;

-- Insert a new employee
INSERT INTO Employees (FirstName, LastName, HireDate)
VALUES ('John', 'Doe', '2023-01-01');

-- Update another employee's information
UPDATE Employees
SET LastName = 'Smith'
WHERE EmployeeID = 1;

-- Check for errors and commit or rollback
IF @@ERROR = 0
BEGIN
    COMMIT TRANSACTION;
    PRINT 'Transaction committed successfully.';
END
ELSE
BEGIN
    ROLLBACK TRANSACTION;
    PRINT 'Transaction rolled back due to an error.';
END;
```

#### Example 2: Transaction with Error Handling

```sql
BEGIN TRANSACTION;

BEGIN TRY
    -- Insert a new department
    INSERT INTO Departments (DepartmentName)
    VALUES ('Sales');

    -- Insert a new employee in the new department
    INSERT INTO Employees (FirstName, LastName, DepartmentID)
    VALUES ('Jane', 'Doe', SCOPE_IDENTITY());

    -- Commit transaction
    COMMIT TRANSACTION;
    PRINT 'Transaction committed successfully.';
END TRY
BEGIN CATCH
    -- Rollback transaction in case of error
    ROLLBACK TRANSACTION;
    PRINT 'Transaction rolled back due to an error.';
    PRINT ERROR_MESSAGE();
END CATCH;
```

#### Example 3: Nested Transactions

```sql
BEGIN TRANSACTION OuterTransaction;

-- Insert a new product
INSERT INTO Products (ProductName, Price)
VALUES ('New Product', 100);

BEGIN TRANSACTION InnerTransaction;
-- Update an existing product's price
UPDATE Products
SET Price = 120
WHERE ProductID = 1;

-- Commit or rollback inner transaction based on condition
IF @@ERROR = 0
BEGIN
    COMMIT TRANSACTION InnerTransaction;
    PRINT 'Inner transaction committed.';
END
ELSE
BEGIN
    ROLLBACK TRANSACTION InnerTransaction;
    PRINT 'Inner transaction rolled back.';
END;

-- Commit or rollback outer transaction based on condition
IF @@ERROR = 0
BEGIN
    COMMIT TRANSACTION OuterTransaction;
    PRINT 'Outer transaction committed.';
END
ELSE
BEGIN
    ROLLBACK TRANSACTION OuterTransaction;
    PRINT 'Outer transaction rolled back.';
END;
```

### Points to Remember:

1. **Atomicity:** Ensures all operations within the transaction are completed successfully or none are.
2. **Consistency:** Ensures the database remains in a consistent state before and after the transaction.
3. **Isolation:** Ensures that transactions are isolated from each other until they are completed.
4. **Durability:** Ensures that once a transaction is committed, it remains so, even in the event of a system failure.

By using transactions, you can maintain the integrity and consistency of your database, especially in complex and multi-step operations.

---

### Constraints in T-SQL

In T-SQL, constraints are rules applied to columns or tables to enforce data integrity and define the conditions that data must meet. They ensure the accuracy and reliability of data within the database. Here are the various types of constraints available in T-SQL:

### 1. Primary Key Constraint

**Definition:** Ensures that each row in a table has a unique and non-null value for the specified column or columns. A table can have only one primary key.

**Syntax:**

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50)
);
```

**Example:**

```sql
ALTER TABLE Employees
ADD CONSTRAINT PK_EmployeeID PRIMARY KEY (EmployeeID);
```

### 2. Foreign Key Constraint

**Definition:** Ensures that the value in one column (or a group of columns) matches a value in the primary key column of another table, enforcing referential integrity.

**Syntax:**

```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    EmployeeID INT,
    OrderDate DATE,
    CONSTRAINT FK_Employee FOREIGN KEY (EmployeeID)
    REFERENCES Employees(EmployeeID)
);
```

**Example:**

```sql
ALTER TABLE Orders
ADD CONSTRAINT FK_EmployeeID FOREIGN KEY (EmployeeID)
REFERENCES Employees(EmployeeID);
```

### 3. Unique Constraint

**Definition:** Ensures that all values in a column or a group of columns are unique across the table.

**Syntax:**

```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Email NVARCHAR(100) UNIQUE
);
```

**Example:**

```sql
ALTER TABLE Customers
ADD CONSTRAINT UQ_Email UNIQUE (Email);
```

### 4. Check Constraint

**Definition:** Ensures that the value in a column meets a specified condition.

**Syntax:**

```sql
CREATE TABLE Products (
    ProductID INT PRIMARY KEY,
    ProductName NVARCHAR(100),
    Price DECIMAL(10, 2),
    CONSTRAINT CHK_Price CHECK (Price > 0)
);
```

**Example:**

```sql
ALTER TABLE Products
ADD CONSTRAINT CHK_Price CHECK (Price > 0);
```

### 5. Default Constraint

**Definition:** Provides a default value for a column when no value is specified during an insert operation.

**Syntax:**

```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    OrderDate DATE DEFAULT GETDATE()
);
```

**Example:**

```sql
ALTER TABLE Orders
ADD CONSTRAINT DF_OrderDate DEFAULT GETDATE() FOR OrderDate;
```

### 6. Not Null Constraint

**Definition:** Ensures that a column cannot have a NULL value.

**Syntax:**

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName NVARCHAR(50) NOT NULL,
    LastName NVARCHAR(50) NOT NULL
);
```

**Example:**

```sql
ALTER TABLE Employees
ALTER COLUMN FirstName NVARCHAR(50) NOT NULL;
```

### Summary of Constraints:

- **Primary Key Constraint:** Ensures unique identification for rows.
- **Foreign Key Constraint:** Enforces referential integrity between tables.
- **Unique Constraint:** Ensures all values in a column are unique.
- **Check Constraint:** Validates data based on a condition.
- **Default Constraint:** Assigns a default value to a column.
- **Not Null Constraint:** Ensures a column cannot contain NULL values.

These constraints are essential for maintaining data integrity and ensuring that the data entered into your database meets the specified rules and conditions.

---

### **AFTER Triggers** and **INSTEAD OF Triggers**

In SQL Server, triggers are special types of stored procedures that are automatically executed, or "fired," in response to certain events on a table or view. The timing of a trigger's execution is defined by the type of trigger:

### Types of Triggers

1. **AFTER Triggers**
2. **INSTEAD OF Triggers**

### 1. AFTER Triggers

**Definition:** An AFTER trigger fires after the SQL Server engine has performed the INSERT, UPDATE, or DELETE operation. These triggers can be used to enforce business rules, update other tables, or maintain audit trails.

**Syntax:**

```sql
CREATE TRIGGER TriggerName
ON TableName
AFTER INSERT, UPDATE, DELETE
AS
BEGIN
    -- Trigger logic here
END;
```

### 2. INSTEAD OF Triggers

**Definition:** An INSTEAD OF trigger fires instead of the triggering event. This means that the trigger is executed in place of the INSERT, UPDATE, or DELETE operation, allowing you to override the default behavior.

**Syntax:**

```sql
CREATE TRIGGER TriggerName
ON TableName
INSTEAD OF INSERT, UPDATE, DELETE
AS
BEGIN
    -- Trigger logic here
END;
```

### Summary of Timing:

- **AFTER Triggers:** Fire **after** the triggering event (INSERT, UPDATE, or DELETE) has been executed.
- **INSTEAD OF Triggers:** Fire **instead of** the triggering event, allowing custom handling of the event.

### Example Usage of AFTER and INSTEAD OF Triggers

#### AFTER Trigger Example

```sql
-- Create a table to log audit information
CREATE TABLE AuditLog (
    AuditID INT IDENTITY(1,1) PRIMARY KEY,
    ActionType NVARCHAR(50),
    ActionTime DATETIME,
    EmployeeID INT
);

-- Create an AFTER INSERT trigger to log insert actions
CREATE TRIGGER trgAfterInsertAudit
ON Employees
AFTER INSERT
AS
BEGIN
    INSERT INTO AuditLog (ActionType, ActionTime, EmployeeID)
    SELECT 'INSERT', GETDATE(), EmployeeID
    FROM inserted;
END;
```

#### INSTEAD OF Trigger Example:

```sql
-- Create an INSTEAD OF DELETE trigger to archive deleted records
CREATE TRIGGER trgInsteadOfDelete
ON Employees
INSTEAD OF DELETE
AS
BEGIN
    -- Insert deleted records into an archive table
    INSERT INTO EmployeesArchive (EmployeeID, FirstName, LastName, HireDate)
    SELECT EmployeeID, FirstName, LastName, HireDate
    FROM deleted;

    -- Perform the actual delete operation
    DELETE FROM Employees
    WHERE EmployeeID IN (SELECT EmployeeID FROM deleted);
END;
```

In summary, **AFTER triggers** are used to execute logic after the data modification, while **INSTEAD OF triggers** override the data modification action and provide custom behavior. This flexibility allows for a wide range of use cases, from simple auditing to complex business rule enforcement.

---

### IDENTITY(1,1)

In SQL Server, `IDENTITY(1,1)` is used to define an identity column in a table. An identity column is a column in a table that automatically generates a unique, incrementing value for each row inserted into the table. This is particularly useful for primary keys.

### Breakdown of `IDENTITY(1,1)`:

- **IDENTITY:** Specifies that the column is an identity column.
- **(1,1):** This part contains two values:
  - The **first value** (1) is the seed, which is the starting value for the identity column.
  - The **second value** (1) is the increment, which is the value by which the identity column is incremented for each new row.

### Example

Here is an example of how `IDENTITY(1,1)` is used in a table definition:

```sql
CREATE TABLE Employees (
    EmployeeID INT IDENTITY(1,1) PRIMARY KEY,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    HireDate DATE
);
```

### Explanation:

- **EmployeeID INT IDENTITY(1,1):** This defines `EmployeeID` as an identity column that starts at 1 and increments by 1 for each new row.
  - The first row inserted into the `Employees` table will have an `EmployeeID` of 1.
  - The second row will have an `EmployeeID` of 2.
  - The third row will have an `EmployeeID` of 3, and so on.

This automatic generation of unique values ensures that each `EmployeeID` is unique and can be used as a primary key to uniquely identify each row in the table.

### Example with Data Insertion

```sql
INSERT INTO Employees (FirstName, LastName, HireDate)
VALUES ('John', 'Doe', '2023-01-01');

INSERT INTO Employees (FirstName, LastName, HireDate)
VALUES ('Jane', 'Smith', '2023-02-01');

SELECT * FROM Employees;
```

### Result:

| EmployeeID | FirstName | LastName | HireDate   |
|------------|-----------|----------|------------|
| 1          | John      | Doe      | 2023-01-01 |
| 2          | Jane      | Smith    | 2023-02-01 |

In this example:
- The first row inserted has an `EmployeeID` of 1.
- The second row inserted has an `EmployeeID` of 2.

By using `IDENTITY(1,1)`, SQL Server ensures that `EmployeeID` is automatically and uniquely assigned to each new row, starting at 1 and incrementing by 1 for each subsequent row.

---

### `deleted` and `inserted` tables in triggers

In the context of SQL Server triggers, the `deleted` and `inserted` tables are special, temporary tables that are automatically created by the SQL Server engine during the execution of a trigger. They are used to hold the old and new values of the data being modified by an `UPDATE`, `INSERT`, or `DELETE` statement.

### Explanation:

- **`deleted` Table:**
  - Contains the old values of the rows that were either deleted or updated.
  - Used in `DELETE` and `UPDATE` triggers to capture the state of the data before the modification.

- **`inserted` Table:**
  - Contains the new values of the rows that were either inserted or updated.
  - Used in `INSERT` and `UPDATE` triggers to capture the state of the data after the modification.

### Example Scenarios:

#### DELETE Trigger Example:

A `DELETE` trigger uses the `deleted` table to handle rows that are being removed from the table.

```sql
-- Create a table for archiving deleted records
CREATE TABLE EmployeesArchive (
    EmployeeID INT,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    HireDate DATE
);

-- Create a trigger to archive deleted records
CREATE TRIGGER trgAfterDelete
ON Employees
AFTER DELETE
AS
BEGIN
    -- Insert deleted records into the archive table
    INSERT INTO EmployeesArchive (EmployeeID, FirstName, LastName, HireDate)
    SELECT EmployeeID, FirstName, LastName, HireDate
    FROM deleted;
END;
```

**Explanation:**

- When a `DELETE` statement is executed on the `Employees` table, the `trgAfterDelete` trigger fires.
- The `deleted` table contains the rows that were deleted from the `Employees` table.
- The trigger inserts these deleted rows into the `EmployeesArchive` table.

#### INSERT Trigger Example:

An `INSERT` trigger uses the `inserted` table to handle rows that are being added to the table.

```sql
-- Create a trigger to log insert operations
CREATE TRIGGER trgAfterInsert
ON Employees
AFTER INSERT
AS
BEGIN
    -- Log the insert operation
    INSERT INTO AuditLog (ActionType, ActionTime, EmployeeID)
    SELECT 'INSERT', GETDATE(), EmployeeID
    FROM inserted;
END;
```

**Explanation:**

- When an `INSERT` statement is executed on the `Employees` table, the `trgAfterInsert` trigger fires.
- The `inserted` table contains the rows that were inserted into the `Employees` table.
- The trigger logs these inserted rows into the `AuditLog` table.

#### UPDATE Trigger Example:

An `UPDATE` trigger can use both the `deleted` and `inserted` tables to handle rows that are being modified.

```sql
-- Create a trigger to log update operations
CREATE TRIGGER trgAfterUpdate
ON Employees
AFTER UPDATE
AS
BEGIN
    -- Log the update operation
    INSERT INTO AuditLog (ActionType, ActionTime, EmployeeID, OldFirstName, NewFirstName)
    SELECT 'UPDATE', GETDATE(), d.EmployeeID, d.FirstName, i.FirstName
    FROM deleted d
    JOIN inserted i ON d.EmployeeID = i.EmployeeID;
END;
```

**Explanation:**

- When an `UPDATE` statement is executed on the `Employees` table, the `trgAfterUpdate` trigger fires.
- The `deleted` table contains the rows with the old values before the update.
- The `inserted` table contains the rows with the new values after the update.
- The trigger logs the changes into the `AuditLog` table, including the old and new values.

### Summary:

- **`deleted` table:** Temporarily holds the old values of the rows affected by `DELETE` and `UPDATE` statements.
- **`inserted` table:** Temporarily holds the new values of the rows affected by `INSERT` and `UPDATE` statements.

These special tables are integral to the functionality of triggers, allowing them to access and manipulate the data before and after the modification.

---
