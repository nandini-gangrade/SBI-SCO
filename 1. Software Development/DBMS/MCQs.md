
1. **Which of the following is a Data Definition Language (DDL) command?**
   - a) `INSERT`
   - b) `UPDATE`
   - c) `CREATE`
   - d) `SELECT`
   
   **Answer**: c) `CREATE`  
   **Explanation**: DDL commands deal with the structure of the database, such as creating, altering, or deleting tables. `CREATE` is used to define new tables or database structures.

---

2. **Which command is used to add new records into a database table?**
   - a) `INSERT`
   - b) `UPDATE`
   - c) `ALTER`
   - d) `DROP`
   
   **Answer**: a) `INSERT`  
   **Explanation**: `INSERT` is a DML (Data Manipulation Language) command used to add new rows to a table.

---

3. **Which of the following is a Data Control Language (DCL) command?**
   - a) `SELECT`
   - b) `GRANT`
   - c) `UPDATE`
   - d) `DELETE`
   
   **Answer**: b) `GRANT`  
   **Explanation**: DCL commands are used to control access to the database. `GRANT` gives specific privileges to users.

---

4. **Which command is used to remove a table from the database?**
   - a) `DELETE`
   - b) `DROP`
   - c) `TRUNCATE`
   - d) `REMOVE`
   
   **Answer**: b) `DROP`  
   **Explanation**: `DROP` is a DDL command used to delete a table, its structure, and all its data permanently.

---

### **Basic SQL Functions**

5. **Which SQL function is used to find the total number of records in a table?**
   - a) `SUM()`
   - b) `COUNT()`
   - c) `MAX()`
   - d) `AVG()`
   
   **Answer**: b) `COUNT()`  
   **Explanation**: `COUNT()` returns the number of rows in a table that match a specified condition.

---

6. **What is the purpose of the `AVG()` function in SQL?**
   - a) Returns the highest value
   - b) Returns the average value of a numeric column
   - c) Returns the sum of the values
   - d) Returns the number of records
   
   **Answer**: b) Returns the average value of a numeric column  
   **Explanation**: The `AVG()` function calculates the average (mean) of a numeric column.

---

7. **Which SQL function is used to return the largest value from a set of values?**
   - a) `MIN()`
   - b) `MAX()`
   - c) `COUNT()`
   - d) `AVG()`
   
   **Answer**: b) `MAX()`  
   **Explanation**: `MAX()` returns the maximum value from a set of values in a column.

---

8. **What does the `NOW()` function in SQL return?**
   - a) The current date and time
   - b) The current date
   - c) The current time
   - d) The current year
   
   **Answer**: a) The current date and time  
   **Explanation**: `NOW()` returns the current date and time in the format `YYYY-MM-DD HH:MM:SS`.

---

### **Views, Triggers, and Cursors**

9. **What is a view in SQL?**
   - a) A physical table in a database
   - b) A stored procedure
   - c) A virtual table created by a query
   - d) A temporary database
   
   **Answer**: c) A virtual table created by a query  
   **Explanation**: A view is a virtual table based on the result-set of an SQL query. It does not store data but displays data from one or more tables.

---

10. **Which of the following is true about triggers in SQL?**
   - a) A trigger can only be executed manually
   - b) A trigger is used to automatically modify the database in response to events like INSERT, UPDATE, DELETE
   - c) Triggers are executed only once
   - d) Triggers are used to create views
   
   **Answer**: b) A trigger is used to automatically modify the database in response to events like INSERT, UPDATE, DELETE  
   **Explanation**: A trigger is a stored procedure that automatically executes when a certain event occurs on a table or view.

---

11. **Which SQL component is used to fetch a set of records one at a time?**
   - a) View
   - b) Trigger
   - c) Cursor
   - d) Stored Procedure
   
   **Answer**: c) Cursor  
   **Explanation**: A cursor is a database object used to retrieve, manipulate, and process rows one by one in a set of results.

---

### **Monolith vs Microservice Architecture**

12. **Which of the following is a key feature of a microservice architecture?**
   - a) A single large codebase for the entire application
   - b) Components of the application are tightly coupled
   - c) Each service can be deployed and scaled independently
   - d) No communication between different services
   
   **Answer**: c) Each service can be deployed and scaled independently  
   **Explanation**: Microservices are independent services that can be developed, deployed, and scaled individually, which is a key feature of this architecture.

---

13. **In a monolithic application, the code for all components is:**
   - a) Distributed across multiple services
   - b) Located in a single codebase
   - c) Deployed independently
   - d) Written in different programming languages
   
   **Answer**: b) Located in a single codebase  
   **Explanation**: A monolithic application is a single unit, and its codebase typically contains all components tightly integrated.

---

14. **Which of the following is an advantage of microservices over monolithic architecture?**
   - a) Easier to manage and maintain a single codebase
   - b) Faster deployment of changes to the application
   - c) No need for network communication between services
   - d) All services are tightly coupled and interdependent
   
   **Answer**: b) Faster deployment of changes to the application  
   **Explanation**: Microservices allow for independent deployment of each service, which speeds up the deployment process compared to monolithic applications.

---

### **Basic Database Concepts: Relational DBMS, ER Diagram, Transactions, Keys, Indexes, Normalization, and Joins**

15. **Which of the following is a key feature of a relational DBMS?**
   - a) No data is stored in tables
   - b) Data is organized in tables with relationships between them
   - c) Only one user can access the database at a time
   - d) Data is stored in JSON format
   
   **Answer**: b) Data is organized in tables with relationships between them  
   **Explanation**: A relational DBMS uses tables to store data and enforces relationships between different tables through keys.

---

16. **In an ER diagram, which of the following represents an entity?**
   - a) Rectangle
   - b) Circle
   - c) Diamond
   - d) Ellipse
   
   **Answer**: a) Rectangle  
   **Explanation**: In an ER diagram, entities are represented by rectangles, which are the objects or concepts that the database stores information about.

---

17. **Which of the following is an example of a foreign key?**
   - a) A unique identifier for each record in a table
   - b) A key that references the primary key in another table
   - c) A key used for indexing records
   - d) A key that identifies entities in an ER diagram
   
   **Answer**: b) A key that references the primary key in another table  
   **Explanation**: A foreign key in one table refers to the primary key in another table, establishing a relationship between the two tables.

---

18. **Which SQL clause is used to combine records from two tables based on a related column?**
   - a) `INNER JOIN`
   - b) `WHERE`
   - c) `GROUP BY`
   - d) `ORDER BY`
   
   **Answer**: a) `INNER JOIN`  
   **Explanation**: `INNER JOIN` is used to combine records from two tables based on a related column, showing only the records where there is a match.

---

19. **What is the purpose of normalization in a relational database?**
   - a) To increase redundancy in the data
   - b) To organize data to avoid data anomalies
   - c) To speed up database queries
   - d) To delete unnecessary data from the database
   
   **Answer**: b) To organize data to avoid data anomalies  
   **Explanation**: Normalization involves organizing data in a database to reduce redundancy and dependency, thus minimizing the risk of data anomalies.

---

20. **Which of the following is true about a primary key?**
   - a) It can contain duplicate values
   - b) It can be NULL
   - c) It uniquely identifies a record in a table
   - d) It can be referenced by a foreign key but cannot be used in indexing
   
   **Answer**: c) It uniquely identifies a record in a table  
   **Explanation**: A primary key uniquely identifies each record in a table and cannot contain NULL values or duplicates.

---

21. **Which of the following DDL commands is used to modify the structure of an existing table?**
   - a) `UPDATE`
   - b) `ALTER`
   - c) `INSERT`
   - d) `DROP`
   
   **Answer**: b) `ALTER`  
   **Explanation**: The `ALTER` command is used to modify the structure of an existing table, such as adding, deleting, or modifying columns.

---

22. **Which DML command is used to remove records from a table?**
   - a) `DROP`
   - b) `TRUNCATE`
   - c) `DELETE`
   - d) `REMOVE`
   
   **Answer**: c) `DELETE`  
   **Explanation**: The `DELETE` command is used to remove specific records from a table based on a condition.

---

23. **Which SQL command is used to apply changes to the database and make them permanent?**
   - a) `ROLLBACK`
   - b) `COMMIT`
   - c) `SAVEPOINT`
   - d) `TRUNCATE`
   
   **Answer**: b) `COMMIT`  
   **Explanation**: `COMMIT` is used to save all changes made in a transaction to the database permanently.

---

24. **Which command is used to undo the changes made in the current transaction?**
   - a) `SAVEPOINT`
   - b) `ROLLBACK`
   - c) `COMMIT`
   - d) `TRUNCATE`
   
   **Answer**: b) `ROLLBACK`  
   **Explanation**: `ROLLBACK` is used to undo any changes made during the current transaction, reverting the database to its previous state.

---

### **Basic SQL Functions**

25. **What does the `LEN()` function in SQL do?**
   - a) Returns the number of records in a table
   - b) Returns the length of a string
   - c) Returns the highest value in a column
   - d) Returns the average value in a column
   
   **Answer**: b) Returns the length of a string  
   **Explanation**: The `LEN()` function returns the number of characters in a string (including spaces).

---

26. **Which of the following SQL functions can be used to round a number to the nearest integer?**
   - a) `ROUND()`
   - b) `CEIL()`
   - c) `FLOOR()`
   - d) `ABS()`
   
   **Answer**: a) `ROUND()`  
   **Explanation**: The `ROUND()` function rounds a numeric value to the nearest integer or a specified number of decimal places.

---

27. **Which function is used to return the current date in SQL?**
   - a) `GETDATE()`
   - b) `NOW()`
   - c) `CURRENT_DATE`
   - d) `CURDATE()`
   
   **Answer**: a) `GETDATE()`  
   **Explanation**: `GETDATE()` returns the current date and time in SQL Server. Other RDBMS like MySQL might use `NOW()`.

---

28. **What does the `COALESCE()` function do in SQL?**
   - a) Returns the first non-NULL value in a list of arguments
   - b) Returns the total number of records in a table
   - c) Returns the highest value in a column
   - d) Returns the value of a column that matches the given condition
   
   **Answer**: a) Returns the first non-NULL value in a list of arguments  
   **Explanation**: `COALESCE()` returns the first non-NULL value in a list of arguments, allowing handling of NULL values in expressions.

---

### **Views, Triggers, and Cursors**

29. **Which SQL object is used to store a result-set and treat it like a table?**
   - a) Trigger
   - b) Cursor
   - c) View
   - d) Procedure
   
   **Answer**: c) View  
   **Explanation**: A `View` is a virtual table that stores the result-set of a query and behaves like a table but does not store data physically.

---

30. **Which type of trigger in SQL fires before any operation is performed on a table?**
   - a) `AFTER`
   - b) `INSTEAD OF`
   - c) `BEFORE`
   - d) `REPLACE`
   
   **Answer**: c) `BEFORE`  
   **Explanation**: A `BEFORE` trigger is executed before an operation (such as `INSERT`, `UPDATE`, or `DELETE`) is performed on a table.

---

31. **Which of the following is NOT a type of trigger in SQL?**
   - a) `BEFORE`
   - b) `AFTER`
   - c) `ON`
   - d) `INSTEAD OF`
   
   **Answer**: c) `ON`  
   **Explanation**: `ON` is not a type of trigger. The correct trigger types are `BEFORE`, `AFTER`, and `INSTEAD OF`.

---

32. **Which command is used to declare a cursor in SQL?**
   - a) `DECLARE`
   - b) `OPEN`
   - c) `FETCH`
   - d) `CLOSE`
   
   **Answer**: a) `DECLARE`  
   **Explanation**: `DECLARE` is used to define a cursor in SQL, which will hold the query result for row-by-row processing.

---

### **Monolith vs Microservice Architecture**

33. **Which of the following is a disadvantage of the monolithic architecture?**
   - a) Scalability issues due to tight coupling of services
   - b) Simplified deployment process
   - c) Independent development of services
   - d) Easier to manage smaller teams
   
   **Answer**: a) Scalability issues due to tight coupling of services  
   **Explanation**: In monolithic architecture, the components are tightly coupled, making scaling difficult because scaling involves the entire application, not just individual components.

---

34. **Which of the following is a key advantage of microservices architecture over monolithic architecture?**
   - a) Easier to manage a single codebase
   - b) Faster scaling and deployment of individual components
   - c) Better for small, simple applications
   - d) Less network communication between services
   
   **Answer**: b) Faster scaling and deployment of individual components  
   **Explanation**: Microservices allow independent deployment and scaling of individual services, leading to more flexibility and faster deployment cycles.

---

35. **In microservices architecture, which communication method is commonly used for interaction between services?**
   - a) Direct database access
   - b) HTTP/REST APIs or messaging queues
   - c) File sharing
   - d) Shared memory access
   
   **Answer**: b) HTTP/REST APIs or messaging queues  
   **Explanation**: Microservices communicate via HTTP/REST APIs or message brokers, which provide decoupling between services.

---

36. **Which of the following best describes the microservices architecture?**
   - a) A single, unified codebase
   - b) Independent, loosely-coupled services that interact over a network
   - c) A monolithic application with many modules
   - d) An architecture with no inter-service communication
   
   **Answer**: b) Independent, loosely-coupled services that interact over a network  
   **Explanation**: Microservices are independent services, each responsible for a specific functionality, communicating over a network via APIs.

---

### **Basic Database Concepts: Relational DBMS, ER Diagram, Transactions, Keys, Indexes, Normalization, and Joins**

37. **Which key uniquely identifies each row in a table?**
   - a) Foreign Key
   - b) Primary Key
   - c) Candidate Key
   - d) Super Key
   
   **Answer**: b) Primary Key  
   **Explanation**: The primary key uniquely identifies each record in a table and cannot have duplicate or NULL values.

---

38. **What is the purpose of an index in a database?**
   - a) To organize data in a table
   - b) To speed up data retrieval operations
   - c) To enforce referential integrity
   - d) To create a relationship between two tables
   
   **Answer**: b) To speed up data retrieval operations  
   **Explanation**: An index is used to speed up retrieval operations in a database by allowing faster searches of specific columns.

---

39. **Which SQL clause is used to filter records based on a specific condition?**
   - a) `WHERE`
   - b) `GROUP BY`
   - c) `ORDER BY`
   - d) `HAVING`
   
   **Answer**: a) `WHERE`  
   **Explanation**: The `WHERE` clause is used to filter records that meet a specific condition.

---

40. **What does the term "ACID" stand for in the context of transactions in databases?**
   - a) Atomicity, Consistency, Isolation, Durability
   - b) Attribute, Consistency, Integrity, Durability
   - c) Application, Consistency, Integrity, Durability
   - d) Access, Control, Integrity, Durability
   
   **Answer**: a) Atomicity, Consistency, Isolation, Durability  
   **Explanation**: ACID refers to the properties that ensure database transactions are processed reliably: Atomicity, Consistency, Isolation, and Durability.

---
