## **1. Basic Database Concepts**

#### **1.1 Relational Database Management System (RDBMS)**

An **RDBMS** is a system used to manage databases in a structured way, using tables (relations) to store data. It uses Structured Query Language (**SQL**) to interact with the data.

##### **Key Features of RDBMS**:
- **Table-based**: Data is stored in tables, where each row represents a record and each column represents an attribute of that record.
- **Data Integrity**: Ensures accuracy and consistency of data over its lifecycle, and relational databases enforce data constraints, such as **Primary Key** and **Foreign Key** constraints.
- **ACID Properties**: RDBMS systems ensure that transactions are processed reliably using the ACID properties: **Atomicity**, **Consistency**, **Isolation**, and **Durability**.
- **Normalization**: RDBMS systems are designed to minimize redundancy and improve data integrity through normalization techniques.

##### **Common RDBMS Examples**:
| RDBMS Name        | Example DB Systems           |
|-------------------|------------------------------|
| SQL-based         | MySQL, PostgreSQL, MS SQL Server |
| NoSQL-based       | MongoDB, Cassandra, CouchDB |

##### **Why Use RDBMS?**
- **Data Integrity**: Ensures that data is consistent and accurate.
- **Efficient Data Retrieval**: Helps in fast searching and retrieval of data using indexing.
- **Security**: Provides advanced user management and access control, allowing the database administrator to define user roles and permissions.

#### **1.2 ER Diagram (Entity-Relationship Diagram)**

An **ER Diagram** is a visual representation of the relationships between entities in a database. It's used for designing and structuring a database and represents how entities (tables) interact with one another.

##### **Components of ER Diagrams**:
- **Entities**: Represented by rectangles. An entity can be a person, place, object, or event that has relevance within the database.
- **Attributes**: Represented by ovals. These are the properties that describe an entity (e.g., Name, Age).
- **Relationships**: Represented by diamonds. These describe how entities are related to one another.
- **Primary Key**: An attribute or set of attributes that uniquely identify a record in an entity.
- **Foreign Key**: An attribute that creates a relationship between two entities.

##### **Example**:
- **Entities**: `Student`, `Course`
- **Attributes** of `Student`: `StudentID`, `Name`, `Age`
- **Relationship**: `EnrolledIn` (linking `Student` to `Course`)

##### **Sample ER Diagram**:

```
|------------|      Enrolls        |------------|
|  Student  |-------------------->|   Course  |
|------------|                     |------------|
| StudentID (PK) |                 | CourseID (PK) |
| Name          |                 | CourseName     |
| Age           |                 | Credits        |
```

---

#### **1.3 ACID Properties of Transactions**

The **ACID** properties ensure the integrity and reliability of transactions in a database. These properties are:

1. **Atomicity**: A transaction is treated as a single unit, which either completely succeeds or completely fails. If a failure occurs, all changes made by the transaction are rolled back.
   - **Example**: A money transfer transaction between two bank accounts: Either both the debit and the credit happen, or neither happens.

2. **Consistency**: A transaction brings the database from one valid state to another. It ensures that all rules (e.g., constraints) are followed.
   - **Example**: If a database enforces a constraint that a student's grade must be between 0 and 100, then after a transaction, this rule must hold true.

3. **Isolation**: Ensures that transactions are isolated from one another. A transaction should not be affected by other transactions occurring at the same time.
   - **Example**: If two transactions are accessing the same data, one transaction should not be able to see the changes made by the other transaction until it is committed.

4. **Durability**: Once a transaction has been committed, it will persist, even if the system crashes.
   - **Example**: If a database commits a record insertion, the inserted record will remain in the database, even if there is a power failure immediately afterward.

##### **Example**: Consider a database operation where money is transferred from one account to another. If the debit operation happens, but the credit operation fails, atomicity ensures that the transaction is rolled back, and no money is deducted.

---

#### **1.4 Keys in a Relational Database**

**Keys** are essential for ensuring that data in relational databases is structured, accessible, and maintains relationships across tables. Here's an explanation of the most commonly used keys:

1. **Primary Key (PK)**: A primary key is a field or combination of fields that uniquely identifies each record in a table.
   - **Example**: In the `Students` table, `StudentID` can be the primary key, ensuring that no two students have the same ID.

2. **Foreign Key (FK)**: A foreign key is a field in a table that is linked to the primary key of another table. It establishes a relationship between two tables.
   - **Example**: In the `Orders` table, `CustomerID` is a foreign key that links to `CustomerID` in the `Customers` table.

3. **Candidate Key**: A candidate key is any attribute that could potentially be a primary key. There can be multiple candidate keys, but only one will be chosen as the primary key.
   - **Example**: In the `Students` table, both `StudentID` and `Email` could be candidate keys.

4. **Composite Key**: A composite key is a combination of two or more columns in a table used to uniquely identify a record.
   - **Example**: In the `Course_Enrollments` table, the combination of `StudentID` and `CourseID` can form a composite key.

5. **Alternate Key**: An alternate key is any candidate key that is not selected as the primary key.
   - **Example**: If `Email` is a candidate key but not the primary key, it becomes an alternate key.

6. **Super Key**: A superkey is a set of one or more columns that can uniquely identify a record in a table. It can have extra columns beyond the candidate key.
   - **Example**: `{StudentID, StudentName}` is a superkey in the `Students` table because it uniquely identifies a student (even though `StudentID` alone could serve as a primary key).

---

#### **1.5 Indexes in Databases**

An **Index** in a database is a data structure that improves the speed of data retrieval operations. It is created on columns that are frequently queried in the `WHERE`, `ORDER BY`, or `JOIN` clauses of SQL statements.

##### **Types of Indexes**:
1. **Unique Index**: Ensures that the values in the indexed column are unique.
   - **Example**: Indexing the `StudentID` column in the `Students` table ensures that each student has a unique ID.
   
2. **Clustered Index**: This type of index determines the physical order of data in the table. There can only be one clustered index per table.
   - **Example**: The `PRIMARY KEY` constraint automatically creates a clustered index on that column.

3. **Non-Clustered Index**: This index does not alter the physical order of data but creates a separate structure that points to the data.
   - **Example**: If you create a non-clustered index on the `LastName` column, the index will store pointers to the actual rows where that data exists.

4. **Composite Index**: An index created on multiple columns.
   - **Example**: If queries frequently involve `FirstName` and `LastName` together, you can create a composite index on both columns.

##### **When to Use Indexes**:
- Use indexes when queries involve `WHERE` clauses or sorting (`ORDER BY`).
- Avoid indexing columns that are frequently updated or contain lots of duplicate values, as maintaining an index can be resource-intensive.

---

#### **1.6 Normalization**

**Normalization** is the process of structuring the data to reduce redundancy and improve data integrity. It involves dividing a large table into smaller, related tables and defining relationships between them.

##### **Normal Forms**:
1. **First Normal Form (1NF)**: Ensures that each column contains atomic (indivisible) values. Each row must be unique.
   - **Example**: If a table contains multiple phone numbers for each employee, split them into separate rows.
   
2. **Second Normal Form (2NF)**: Achieved when the table is in 1NF and all non-key attributes are fully dependent on the primary key.
   - **Example**: If a `Course_Enrollments` table has `StudentID` and `CourseID` as the primary key, all non-key columns must depend on the entire combination, not just `StudentID`.

3. **Third Normal Form (3NF)**: Achieved when the table is in 2NF and no transitive dependency exists (i.e., non-key attributes must depend only on the primary key).
   - **Example**: If `ManagerName` depends on `Department`, it should be removed and placed in a separate `Department` table.

---

### **1.7 Joins in Relational Databases**

**Joins** are used to combine data from two or more tables based on a related column between them. In relational databases, these related columns are typically **foreign keys**.

There are several types of joins:

#### **1.7.1 INNER JOIN**
The **INNER JOIN** keyword selects records that have matching values in both tables. If there is no match, the row is not included in the result.

- **Example**: Suppose we have two tables: `Employees` and `Departments`.
  - `Employees` contains columns: `EmployeeID`, `Name`, `DepartmentID`
  - `Departments` contains columns: `DepartmentID`, `DepartmentName`
  
  A query that performs an inner join to retrieve employees along with their department names would look like this:

  ```sql
  SELECT Employees.Name, Departments.DepartmentName
  FROM Employees
  INNER JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
  ```

  **Result**: Only employees who belong to a department are included in the result set.

#### **1.7.2 LEFT JOIN (or LEFT OUTER JOIN)**
The **LEFT JOIN** returns all records from the left table (the first table), and the matched records from the right table (second table). If there is no match, the result is **NULL** on the side of the right table.

- **Example**:
  ```sql
  SELECT Employees.Name, Departments.DepartmentName
  FROM Employees
  LEFT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
  ```

  **Result**: This query returns all employees, even those who are not assigned to any department. For such employees, the `DepartmentName` will be `NULL`.

#### **1.7.3 RIGHT JOIN (or RIGHT OUTER JOIN)**
The **RIGHT JOIN** returns all records from the right table, and the matched records from the left table. If there is no match, the result will be **NULL** on the left side.

- **Example**:
  ```sql
  SELECT Employees.Name, Departments.DepartmentName
  FROM Employees
  RIGHT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
  ```

  **Result**: This query returns all departments, even those that don't have any employees assigned to them.

#### **1.7.4 FULL JOIN (or FULL OUTER JOIN)**
The **FULL JOIN** returns all records when there is a match in either the left or right table. It combines the results of both **LEFT JOIN** and **RIGHT JOIN**. If there is no match, the result is **NULL** for non-matching rows from both sides.

- **Example**:
  ```sql
  SELECT Employees.Name, Departments.DepartmentName
  FROM Employees
  FULL JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
  ```

  **Result**: This query returns all employees and all departments. If an employee does not belong to a department or a department has no employees, it will show `NULL` for the missing information.

#### **1.7.5 CROSS JOIN**
A **CROSS JOIN** returns the Cartesian product of the two tables. This means it will combine every row from the first table with every row from the second table. 

- **Example**:
  ```sql
  SELECT Employees.Name, Departments.DepartmentName
  FROM Employees
  CROSS JOIN Departments;
  ```

  **Result**: Every employee will be paired with every department, potentially generating a large number of rows.

#### **1.7.6 SELF JOIN**
A **SELF JOIN** is when a table is joined with itself. This is often used to compare rows within the same table.

- **Example**: Suppose we have an `Employees` table with `EmployeeID`, `ManagerID`, and `Name`. We want to find the names of employees and their managers.
  ```sql
  SELECT E.Name AS Employee, M.Name AS Manager
  FROM Employees E
  LEFT JOIN Employees M ON E.ManagerID = M.EmployeeID;
  ```

  **Result**: This query will list employees and their respective managers.

---

### **1.8 SQL Functions**

SQL functions are used to perform operations on data within the database. They can be categorized as follows:

#### **1.8.1 Aggregate Functions**
These functions perform a calculation on a set of values and return a single value. Some common aggregate functions include:
- **COUNT()**: Counts the number of rows in a result set.
  ```sql
  SELECT COUNT(*) FROM Employees;
  ```
- **SUM()**: Returns the total sum of a numeric column.
  ```sql
  SELECT SUM(Salary) FROM Employees;
  ```
- **AVG()**: Returns the average value of a numeric column.
  ```sql
  SELECT AVG(Salary) FROM Employees;
  ```
- **MAX()**: Returns the maximum value of a column.
  ```sql
  SELECT MAX(Salary) FROM Employees;
  ```
- **MIN()**: Returns the minimum value of a column.
  ```sql
  SELECT MIN(Salary) FROM Employees;
  ```

#### **1.8.2 Scalar Functions**
Scalar functions return a single value based on the input value. Common scalar functions include:
- **UPPER()**: Converts a string to uppercase.
  ```sql
  SELECT UPPER(Name) FROM Employees;
  ```
- **LOWER()**: Converts a string to lowercase.
  ```sql
  SELECT LOWER(Name) FROM Employees;
  ```
- **LENGTH()**: Returns the length of a string.
  ```sql
  SELECT LENGTH(Name) FROM Employees;
  ```

#### **1.8.3 Date Functions**
- **CURRENT_DATE**: Returns the current date.
  ```sql
  SELECT CURRENT_DATE;
  ```
- **DATEADD()**: Adds a specified time interval to a date.
  ```sql
  SELECT DATEADD(DAY, 7, CURRENT_DATE);
  ```
- **DATEDIFF()**: Returns the difference between two dates.
  ```sql
  SELECT DATEDIFF('2024-12-31', '2024-01-01');
  ```

#### **1.8.4 Conversion Functions**
- **CAST()**: Converts a value from one data type to another.
  ```sql
  SELECT CAST(Salary AS VARCHAR) FROM Employees;
  ```
- **CONVERT()**: Similar to `CAST()`, but allows additional formatting for date/time types.
  ```sql
  SELECT CONVERT(VARCHAR, HireDate, 103) FROM Employees;
  ```

---

### **1.9 Views, Triggers, and Cursors**

#### **1.9.1 Views**
A **View** is a virtual table created by a query that selects data from one or more tables. It doesn't store data itself but allows you to view data in a structured way. Views are useful for simplifying complex queries.

- **Example**: 
  ```sql
  CREATE VIEW EmployeeDetails AS
  SELECT EmployeeID, Name, DepartmentID
  FROM Employees;
  ```

  You can then query the view just like a table:
  ```sql
  SELECT * FROM EmployeeDetails;
  ```

#### **1.9.2 Triggers**
A **Trigger** is a database object that automatically executes or fires when certain events (INSERT, UPDATE, DELETE) occur on a table or view. Triggers are used to enforce rules and maintain data integrity.

- **Example**: A trigger that automatically updates the `LastUpdated` timestamp when a record in the `Employees` table is updated:
  ```sql
  CREATE TRIGGER UpdateTimestamp
  BEFORE UPDATE ON Employees
  FOR EACH ROW
  SET NEW.LastUpdated = CURRENT_TIMESTAMP;
  ```

#### **1.9.3 Cursors**
A **Cursor** allows you to retrieve a few rows of a result set, one at a time. It is used for handling complex row-by-row operations.

- **Example**:
  ```sql
  DECLARE @EmployeeName VARCHAR(100);
  DECLARE employee_cursor CURSOR FOR
    SELECT Name FROM Employees;
  
  OPEN employee_cursor;
  FETCH NEXT FROM employee_cursor INTO @EmployeeName;
  
  WHILE @@FETCH_STATUS = 0
  BEGIN
    PRINT @EmployeeName;
    FETCH NEXT FROM employee_cursor INTO @EmployeeName;
  END
  
  CLOSE employee_cursor;
  DEALLOCATE employee_cursor;
  ```

---

### **1.10 Monolith vs Microservices Architecture**

**Monolithic Architecture** and **Microservices Architecture** are two different approaches to building and structuring software applications.

#### **1.10.1 Monolithic Architecture**
In a **monolithic architecture**, the entire application is built as a single unit or block, where all the components are tightly integrated and share a common codebase. This type of architecture was traditionally used for many enterprise applications.

- **Key Characteristics**:
  - **Single codebase**: All components (e.g., UI, business logic, database access) are part of the same codebase.
  - **Tightly coupled**: Changes in one part of the application can potentially affect other parts.
  - **Single deployment**: The whole application is deployed as one unit.
  - **Scalability challenges**: Scaling a monolithic application is often more complex because you have to scale the entire application, even if only one part of it is under heavy load.

- **Advantages**:
  - Easier to develop initially (due to simplicity and lack of distributed nature).
  - Simple deployment (just one deployable unit).
  - Easier to maintain in small teams with well-defined modules.

- **Disadvantages**:
  - **Scalability issues**: Difficult to scale parts of the application independently.
  - **Long-term maintainability**: As the application grows, the codebase can become difficult to maintain and understand.
  - **Deployment bottlenecks**: Deploying even a small update requires redeploying the entire application.

#### **1.10.2 Microservices Architecture**
In **microservices architecture**, the application is broken down into a set of small, independent services that communicate with each other over well-defined APIs. Each service is responsible for a specific business function.

- **Key Characteristics**:
  - **Decoupled services**: Each service can be developed, deployed, and scaled independently.
  - **Distributed**: Each service typically runs in its own process and often uses a different database.
  - **Independent scalability**: Services can be scaled independently, allowing you to allocate resources to parts of the application that need them the most.
  - **Fault isolation**: Failures in one service are less likely to affect others.

- **Advantages**:
  - **Independent scaling**: You can scale parts of the system without affecting the entire application.
  - **Technology flexibility**: Each microservice can be built using different technologies (e.g., different programming languages or databases) based on its requirements.
  - **Resilience**: Because services are decoupled, if one service fails, it does not bring down the entire system.
  - **Faster deployment**: Continuous delivery and independent deployment of microservices.

- **Disadvantages**:
  - **Complexity**: Building and maintaining a microservices architecture can be complex due to the distributed nature.
  - **Deployment challenges**: Managing the deployment of multiple services can be tricky.
  - **Increased communication overhead**: Microservices communicate over a network, so network latency and reliability become concerns.

#### **1.10.3 Key Differences**

| Aspect                    | Monolithic Architecture            | Microservices Architecture         |
|---------------------------|-------------------------------------|-------------------------------------|
| **Architecture Type**      | Single, unified application        | Distributed, independent services  |
| **Deployment**             | Single deployment unit             | Multiple independent deployments   |
| **Scalability**            | Limited; need to scale the entire app | Independent scaling of services    |
| **Fault Tolerance**        | Single failure point               | Faults isolated to individual services |
| **Development Speed**      | Faster to start, simpler initially | Slower initial setup, more complex |
| **Maintainability**        | Harder to maintain as it grows     | Easier to maintain with small services |
| **Technology Stack**       | Same stack for entire app          | Different stacks for different services |
| **Communication**          | Internal calls (direct access)     | API calls (REST, gRPC, etc.) between services |

---

