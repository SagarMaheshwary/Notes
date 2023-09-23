## SQL QUESTIONS

- #### What is SQL?

  SQL stands for Structured Query Language. It is the standard language for **RDBMS**. It is especially useful in handling organized data
  comprised of entities (tables) and relations between different entities of the data.

- #### What are the different components of an RDBMS?

  **Tables**: Tables are the basic unit of storage in an RDBMS. A table is a collection of related data, organized into rows and columns. Each row represents a single record, and each column represents a single attribute of the record.<br>
  **Constraints**: Constraints are used to ensure the integrity of the data in an RDBMS. For example, a constraint can be used to prevent duplicate values from being inserted into a column, or to ensure that a value in one column is always greater than or equal to a value in another column.<br>
  **Transactions**: Transactions are used to group together multiple operations into a single unit of work. If any of the operations in a transaction fail, the entire transaction is rolled back, and the data is returned to its previous state.<br>
  **Indexes**: Indexes are used to improve the performance of queries. An index is a data structure that stores the values of a column in a sorted order. This allows the RDBMS to quickly find rows that match the criteria in a query.<br>
  **Views**: Views are virtual tables that are based on one or more underlying tables. Views can be used to restrict the data that is visible to users, or to create new tables that contain only the data that is needed for a specific application.<br>
  **Stored procedures and functions**: Stored procedures and functions are pre-compiled SQL statements that can be reused multiple times. This can improve the performance of applications and make them easier to maintain.

- #### What are Tables and Fields in RDBMS?

  A table is an organized collection of data stored in the form of rows and columns.
  Columns can be categorized as vertical and rows as horizontal. The columns in a
  table are called fields while the rows can be referred to as records.

- #### What is Constraints in SQL?

  Constraints in SQL are rules that are used to ensure the integrity and accuracy of data in a database. They can be used to specify the data type, range, uniqueness, and other properties of columns in a table.<br>Constraints can be defined at the table level or the column level. Table level constraints apply to all rows in a table, while column level constraints apply to specific columns in a table. ex. primary key, foreign key, unique, not null, default, index, check.<br>
  **NOT NULL**: This constraint prevents a column from having a NULL value.<br>
  **UNIQUE**: all values in a column should be different. table can have multiple unique keys, can be null,doesn't add automatic index.<br>
  **PRIMARY KEY**: This constraint is a combination of a NOT NULL and UNIQUE constraint. Identify a row in a table. automatically add index, only one per table allowed, can't contain null values.<br>
  **FOREIGN KEY**: A foreign key is a column or group of columns in a table that refers to the primary key of another table. The foreign key links these two tables together. Foreign keys are used to enforce referential integrity (set of rules that ensures that the data in the two tables is consistent).<br>
  **CHECK**: This constraint allows you to define a custom rule for the values in a column.<br>
  **DEFAULT**: This constraint specifies a default value for a column if no value is specified when a new row is inserted into the table.

- #### Different types of keys available in RDBMS?

  **PRIMARY KEY**: A primary key is a unique identifier for each row in a table. It can be a single column or a combination of multiple columns.<br>
  **FOREIGN KEY**: A foreign key is a column in one table that references the primary key of another table. This creates a relationship between the two tables.<br>
  **Candidate key**: A candidate key is a column or set of columns that can uniquely identify each row in a table. However, there may be multiple candidate keys for a table.<br>
  **Alternate key**: An alternate key is a candidate key that is not chosen as the primary key.<br>
  **Unique key**: A unique key is a column or set of columns that can uniquely identify each row in a table. However, unlike a primary key, it can contain null values.<br>
  **Composite key**: A composite key is a primary key that is made up of multiple columns.<br>
  **Surrogate key**: A surrogate key is a unique identifier that is not a natural part of the data. Surrogate keys are often used when the natural keys(primary key) are not unique.

- #### What are DDL commands in SQL?

  **DDL (Data Definition Language)** commands are used to create, modify, and delete database objects, such as tables, views, indexes, and constraints.<br>
  Some common DDL commands include:<br>
  **CREATE**: Creates a new database object.<br>
  **ALTER**: Modifies an existing database object.<br>
  **DROP**: Deletes an existing database object.<br>
  **RENAME**: Renames an existing database object.<br>
  **TRUNCATE**: Deletes all data from a table, but keeps the table structure.

- #### What are DQL commands in SQL?

  **DQL (Data Query Language)** commands are used to retrieve data from a database. DQL commands are read-only operations, meaning that they cannot change the data in the database.<br>
  The most common DQL command is the **SELECT** statement.

- #### What are DML commands in SQL?

  **Data Manipulation Language (DML)** commands in SQL are used to change the data in a database. DML commands are typically used to insert, update, or delete data in a table.<br>
  The most common DML commands are:<br>
  **INSERT**: Inserts a new row into a table.<br>
  **UPDATE**: Updates the data in an existing row in a table.<br>
  **DELETE**: Deletes a row from a table.

- #### What are DCL commands in SQL?

  **DCL (Data Control Language)** commands in SQL are used to grant, revoke, and manage permissions on database objects. DCL commands are typically used by database administrators (DBAs) to control who has access to the database and what they can do with it.<br>
  The most common DCL commands are:<br>
  **GRANT**: Grants permissions on a database object to a user or role.<br>
  **REVOKE**: Revokes permissions on a database object from a user or role.<br>
  Other DCL commands include:<br>
  **CREATE USER**: Creates a new database user.<br>
  **ALTER USER**: Modifies an existing database user.<br>
  **DROP USER**: Deletes an existing database user.<br>
  **CREATE ROLE**: Creates a new database role.<br>
  **ALTER ROLE**: Modifies an existing database role.<br>
  **DROP ROLE**: Deletes an existing database role.<br>

- #### What are TCL commands in SQL?

  **TCL (Transaction Control Language)** commands in SQL are used to manage transactions. A transaction is a group of database operations that are treated as a single unit. If any of the operations in a transaction fail, then the entire transaction is rolled back and the database is restored to its previous state.<br>
  The most common TCL commands are:<br>
  **COMMIT**: Commits a transaction, making the changes to the database permanent.<br>
  **ROLLBACK**: Rolls back a transaction, restoring the database to its previous state.<br>
  **SAVEPOINT**: Creates a savepoint within a transaction. This allows you to roll back the transaction to the savepoint if something goes wrong.

- #### What are Joins in SQL?

  A join in a database is a query that combines rows(records) from two or more tables based on related column between the two. Joins are used to retrieve data that is spread across multiple tables.

- #### Types of Joins?
  **Inner Join**: retrieve records that have matching values in both tables.
  Ex. all customers who have placed an order.

**Left Join**: retrieve all rows from the left table and match records.
Ex. all customers, even if they have not placed an order.

**Right Join**: retrieve all rows from the right table and match records.
Ex. all orders, even if they have not been placed by a customer;

**Full Join**: retrieve all rows that have either matched in left table or right table.
Ex. all customers and orders, even if a customer has not placed an order or an order has not been placed by a customer

**Self Join**: A table is join to itself based on some relation between its own columns. used inner-join or left-join clause with different alias for same table name.
Ex. find all employees who are managers same id and manger_id in same table.

**cross Join**: Cartesian product (is the set of all possible combinations of rows from the two tables).
They can be used to find all possible relationships between two tables.

- #### Advantages and Disadvantages of Joins?
  **Advantages of Join**: <br>
  Joins can be used to retrieve data from multiple tables in a single operation.<br>
  This can improve the performance of queries by reducing the number of times that the database needs to be accessed.

**Disadvantages of Join**:<br>
Joins can be complex to write and understand.<br>
Joins can be computationally expensive.

- #### Common Join Algorithms in SQL?
  **Nested loop join**: This algorithm is the simplest join algorithm, but it is also the least efficient. It works by comparing each row in the left table to every row in the right table.<br>
  Ex.<br>
- For each row in the left table:<br>
  - For each row in the right table:<br>
    - If the join column values match, then add the row to the result set.<br>

**Merge join**: This algorithm is more efficient than the nested loop join algorithm, but it requires both tables to be sorted on the join column. It works by merging the two sorted tables together, comparing one row from each table at a time.<br>
Ex.<br>

- Sort both tables on the join column.<br>
- Create two cursors, one for each table.<br>
- Move the cursors to the first rows in each table.<br>
- While the cursors are not at the end of both tables:<br>
  - If the join column values match, then add the row to the result set.<br>
  - Move the cursor for the smaller table to the next row.<br>
- Close the cursors.<br>

**Hash join**: This algorithm is the most efficient join algorithm, but it requires both tables to be able to fit in memory. It works by creating a hash table for one of the tables, and then using the hash table to find the matching rows in the other table.<br>
Ex.<br>

- Create a hash table for one of the tables, using the join column as the key.<br>
- For each row in the other table:<br>

  - Look up the join column value in the hash table.<br>
  - If there is a matching row in the hash table, then add the row to the result set.<br>

- #### What do you understand by CLAUSE in SQL?

  A clause in SQL is a group of statements that define the structure of a SQL query. Most common SQL clauses are SELECT, FROM, WHERE, GROUP BY, HAVING, ORDER BY.

- #### What is the Order of execution of SQL Query?

  The order of execution of a SQL query is as follows:<br>
  **FROM**: The FROM clause specifies the tables that will be used in the query. The DBMS will first locate the data in these tables.<br>
  **WHERE**: The WHERE clause specifies the conditions that must be met for the query to return results. The DBMS will filter the data from the FROM clause based on the WHERE clause conditions.<br>
  **GROUP BY**: The GROUP BY clause groups the rows in the result set based on the specified columns.<br>
  **HAVING**: The HAVING clause specifies the conditions that must be met for groups of rows to be included in the result set.<br>
  **SELECT**: The SELECT clause specifies the columns that will be returned by the query.<br>
  **ORDER BY**: The ORDER BY clause specifies the order in which the rows in the result set will be returned.

- #### What are the differences between DROP, TRUNCATE and DELETE commands?
  **DROP**: Drops a table or other database object from the database. The dropped object cannot be recovered.<br>
  **Truncate**: Deletes all rows from a table, but preserves the table structure. The deleted rows cannot be recovered.<br>
  **DELETE**: Deletes specific rows from a table, based on a WHERE clause. The deleted rows can be recovered using a ROLLBACK statement.<br>

| Feature                   | Drop | Truncate | Delete |
| ------------------------- | ---- | -------- | ------ |
| Deletes table             | Yes  | No       | No     |
| Deletes rows              | Yes  | Yes      | Yes    |
| Preserves table structure | No   | Yes      | Yes    |
| Recoverable               | No   | No       | No     |
| Command Type              | DDL  | DDl      | DML    |
| Speed                     | slow | fastest  | fast   |

- #### What is a Sub Query?

  A sub query is a query within another query, also known as a nested query or inner
  query. the inner query is sub query and the outer query is main query.

- #### What are Types of Sub Query?

  **Single Row SubQuery**: This type of subquery returns a single row of data. It is typically used in the WHERE clause to filter the results of the main query.<br>
  **Multiple Row SubQuery**: This type of subquery returns multiple rows of data. It is typically used in the SELECT clause to generate more complex results.<br>
  **Multiple Column SubQuery**:This type of subquery returns multiple columns of data.<br>
  **Correlated SubQuery**: This type of subquery references a column from the outer query. It is typically used to perform more complex calculations or comparisons.<br>
  **Nested SubQuery**: A nested subquery is a subquery that is contained within another subquery.

- #### What are indexes in SQL?

  An index in SQL is a data structure that improves the speed of data retrieval operations on a database table. Indexes are created on one or more columns in a table, and they store a sorted list of the values in those columns. When a query is executed, the DBMS can use the index to quickly find the rows in the table that match the query criteria. EX. phonebook.

- #### What are data Structure of Indexes?

  There are many different algorithms that can be used to implement indexes in a DBMS. However, the most common algorithm is the B-tree algorithm.<br>
  A B-tree is a self-balancing tree data structure that keeps data in a sorted order. This allows the DBMS to quickly find the rows in the table that match the query criteria.<br>
  The B-tree algorithm works by creating a tree of nodes, where each node contains a set of key-value pairs. The keys are the values of the indexed column, and the values are the pointers to the rows in the table that contain the corresponding key values. useful for range based and equality based queries.<br>
  other algorithm are Hash index(equality based),Gin index.

- #### What is a View in SQL?

  A view in SQL is a virtual table that is based on the result set of an SQL statement. Views can be used to simplify queries, restrict access to data, and create logical data structures.<br>
  Views are created using the CREATE VIEW statement.

- #### What is a Materialized View in SQL?

  A materialized view is a database object that contains the results of a query. It is a physical table that is populated with the results of a query and is kept up to date as the underlying data changes. <br>
  Materialized Views are created using the CREATE MATERIALIZED VIEW statement.

- #### Difference View and Materialized View?

  The main difference between a view and a materialized view is that a view is a virtual table, while a materialized view is a physical table.<br>
  views are always up-to-date, while materialized views need to be refreshed periodically.<br>
  views doesn't store data on database while materialized views store data on db.<br>
  views are slower then materialized views.

- #### What is Pattern Matching in SQL?

  Pattern matching in SQL is the ability to search for strings or data that match a specific pattern. This can be done using the LIKE operator, which is a built-in operator in SQL.<br>
  The LIKE operator allows you to specify wildcards, which are special characters that can match any single character or any sequence of characters. The most common wildcards are the percent sign (%) and the underscore (_).<br>
  The % wildcard matches any sequence of characters, including zero characters. The _ wildcard matches any single character.

- #### What are UNION, UNION ALL , MINUS and INTERSECT commands?

  **UNION**: The UNION command combines the results of two or more SELECT statements, eliminating duplicate rows.<br>
  **UNION ALL**: The UNION ALL command combines the results of two or more SELECT statements, including duplicate rows.<br>
  **MINUS**: The MINUS command returns the rows from the first SELECT statement that are not present in the second SELECT statement.<br>
  **INTERSECT**: The INTERSECT command returns the rows that are present in both SELECT statements.<br>

- #### What is Store Procedure in SQL?

  A stored procedure is a sub routine or set of SQL statements that are grouped together and saved as a single unit.<br>
  stored procedures can be used to perform a variety of tasks, such as:<br>
  Inserting, updating, and deleting data.<br>
  Performing complex calculations.<br>
  Validating data.<br>
  Implementing security features.<br>
  Improving the performance of database applications.<br>
  Stored procedures are created using the CREATE PROCEDURE statement.<br>
  it can be executed using the EXECUTE PROCEDURE statement.

- #### What is Functions in SQL?

  A Function is a type of stored procedure that returns a single value. Functions are often used to perform calculations or to return a value based on a set of input parameters.<br>
  Functions can be used to perform a variety of tasks, such as:<br>
  Formatting data.<br>
  Performing calculations.<br>
  Validating data.<br>
  Converting data types.<br>
  Returning data from multiple tables.<br>
  Functions are created using the CREATE FUNCTION statement.

- #### What is Trigger in SQL?

  A trigger in SQL is a special type of stored procedure that is automatically executed when a specific event occurs on a table. Triggers can be used to enforce business rules, maintain data integrity, and automate certain actions within a database.<br>
  Most commonly used trigger are DML and less common are DDL.<br>
  Triggers are created using the CREATE TRIGGER statement.

- #### Difference between Store Procedure, Function and Trigger in SQL?
  The main difference between a stored procedure, function, and trigger in SQL is that <br> a stored procedure is a group of SQL statements that performs a specific task,<br> a function is a special type of stored procedure that returns a value,<br> and a trigger is a special type of stored procedure that is automatically executed when a specific event occurs on a table.<br>

##### Differences:

| Feature       | Stored Procedure                                                                                                                                                                                     | Function                                                | Trigger                                                                                               |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Execution** | Executed explicitly using the EXECUTE PROCEDURE statement.                                                                                                                                           | Executed implicitly when called in a SELECT statement.  | Trigger can be executed automatically on specified action on a table like, update, delete, or update. |
| **Calling**   | Stored Procedures can't be called from a function because functions can be called from a select statement and Stored Procedures can't be called from. But you can call Store Procedure from Trigger. | Function can be called from Store Procedure or Trigger. | Trigger can’t be called from Store Procedure or Function.                                             |
| **Parameter** | Stored Procedures can accept any type of parameter                                                                                                                                                   | Function can accept any type of parameter.              | We can’t pass a parameter to trigger                                                                  |
| **Return**    | Stored Procedures may or may not return any values                                                                                                                                                   | Stored Procedures may or may not return any values      | Trigger never return value on execution.                                                              |

- Use stored procedures to perform complex tasks that involve multiple SQL statements.<br>
- Use functions to perform simple tasks that involve a single SQL statement and return a value.<br>
- Use triggers to enforce business rules, maintain data integrity, and automate certain actions within a database.

- #### What are User-defined functions (UDFs)?

  **User-defined functions (UDFs)** in SQL are custom functions that can be created and used in SQL queries. UDFs can be used to perform a variety of tasks, such as:<br>
  Formatting data<br>
  Performing calculations<br>
  Validating data<br>
  Converting data types<br>
  Combining data from multiple tables<br>
  Performing complex calculations<br>
  UDFs can be created using the CREATE FUNCTION statement.<br>
  EX. get_full_name from user table first name and last name.

- #### Difference between Aggregate, Scalar, and Table-valued functions in SQL?

  **Aggregate functions**: Aggregate functions return a single value that summarizes the values in a column or group of rows. Examples of aggregate functions include SUM(), AVG(), COUNT(), and MAX().<br>
  **Scalar functions**: Scalar functions return a single value that is calculated from the input parameters. Examples of scalar functions include SUBSTR(), DATEADD(), and CONCAT().<br>
  **Table-valued functions**: Table-valued functions return a table of data. Examples of table-valued functions include FNSplit() and FNSort().

- #### What is Cursor in SQL?

  A cursor in SQL is a temporary database object that allows you to iterate over the rows of a result set one at a time.<br>
  Cursors are created using the DECLARE CURSOR statement.<br>
  There are two main types of cursors in SQL:<br>
  **Implicit cursors**: Implicit cursors are created and managed by the database engine. They are typically used to fetch rows from a result set one at a time.
  **Explicit cursors**: Explicit cursors are created and managed by the user. They give the user more control over how the cursor moves through the result set.
  EX. Generator function in programming.

- #### How To define a transaction in a Sql?
  To define a transaction in a SQL, you can use the following steps:<br>
- Start the transaction by issuing a BEGIN TRANSACTION or START DBMS statement.
- Perform the operations that you want to include in the transaction.
- Commit the transaction by issuing a COMMIT TRANSACTION or END DBMS statement.

- #### What is Exclusive lock and Shared Lock?
  **Exclusive**: An exclusive lock prevents any other transaction from accessing the locked resource.<br>
  **Shared**: A shared lock allows other transactions to read the locked resource, but not to modify it.
