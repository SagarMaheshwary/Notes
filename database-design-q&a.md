## DBMS Design Q&A

- #### What is a database?
A database is a collection of data that is organized so that it can be easily accessed, managed, and updated.<br>OR<br>
A database is orgranized collection of data stored and retrieved digitally on remote or local computer.<br>
Ex. Databases are used to store all sorts of data, such as customer information, product inventory, and financial records.

- #### What is DBMS (Database Management System)?
DBMS acts as interface between the database and end user or application software. <br>
DBMS manage, update, create data on database. can store structure data, sami-structure data and unstructure data.<br>
DBMS Provides an organized way of managing, retrieving,and storing from a collection of logically related information.

- #### Advantages of DBMS?
**Data Integrity**: DBMSs ensure that data is accurate and consistent by enforcing data constraints and rules.<br>
**Data Sharing**: DBMSs make it easy to share data between different users and applications.<br>
**Data Backup And Recovery**: DBMSs provide built-in backup and recovery mechanisms to protect data from loss or corruption.<br>
**Data Security**: DBMSs protect data from unauthorized access and modification by implementing security features such as user authentication and access control.<br>
**Performance**: DBMSs are designed to handle large amounts of data efficiently, providing fast data access and retrieval.<br>
**Scalability**: DBMSs can be scaled to meet the needs of growing businesses and organizations.

- #### Types of DBMSs?
**Relational DBMS**: Relational databases are the most common type of database. They store data in tables, which are made up of rows and columns. ex. PostgreSQL, MySQL.<br>
**No Relational DBMS**: NoSQL databases are a newer type of database that is designed to store large amounts of unstructured data. ex. MongoDB, Radis.<br>
**Object-Oriented DBMS**: Object-oriented databases store data in objects, which are similar to the objects that are used in programming languages. ex. WakandaDB.<br>
**Distributed DBMS**: Distributed databases are databases that are spread across multiple computers. ex. Apache Cassandra.<br>
**Hierarchical DBMS**: is a type of DBMS that organizes data into a tree-like structure, with each record having a single parent record and zero or more child records. ex. File system structure.<br>
**Network DBMS**: is a type of DBMS that organizes data into a network-like structure, with each record having multiple parent records and multiple child records. ex. TurboIMAGE.

- #### What is RDBMS (Relational Database Management System)?
RDBMS type of DBMS that store data as tables, rows and columns fashion support normalization and other RDBMS feature.

- #### What is the difference between a relational database and a NoSQL database?
The main difference between a relational database and a NoSQL database is the way they store data.
Relational databases store data in tables, which are made up of rows and columns. a single row is called a record.
NoSQL databases store data in different ways, depending on the type of NoSQL database. like mangodb save document in collection.other are groph, key-value pairs.

- #### What is the difference between two and three-tier database architectures?
**Two-Tier**: The client and the database communicate directly with each other. Client -> Database.<br>
**Three-Ttier**: The application layer acts as an intermediary between the client and the database. Client, Application and Database.

- #### Levels of abstraction or Schema architecture in DBMS?
**Physical level (Internal level)**: The physical level is the lowest level of abstraction and is closest to the hardware. It describes how the data is physically stored on the disk. The physical level is typically hidden from users and applications, and is managed by the DBMS. <br>
Example of physical level are <br>
Data structures: The physical level defines the data structures used to store the data, such as files, blocks, and pages.<br>
Access methods: The physical level defines the methods used to access the data, such as indexes and hash tables.<br>
Storage management: The physical level manages the allocation and de-allocation of storage space for the data.<br>
**Logical level (Conceptual level)**: The logical level is the middle level of abstraction and is closest to the users and applications. It describes the data model that is used to organize the data in the database. it includes entities, relationships and attributes The logical level is typically represented by an entity-relationship diagram (ERD).<br>
**View level (External level)**: The view level is the highest level of abstraction and is closest to the users and applications. It describes the different ways in which the data in the database can be viewed. Views are typically created for different groups of users, so that they can see only the data that is relevant to them.The view level is implemented using views. A view is a logical representation of the data in the database.

- #### What are Entities, Relationships and Attributes?
**Entities**: Entities are the objects that are stored in the database, such as customers, products, and orders.
**Relationships**: Relationships are the connections between entities. For example, a customer can place an order for a product.
**Attributes**: Attributes are the properties of entities. For example, a customer entity might have the following attributes: name, address, and phone number.

- #### What is an entity-relationship model (ERD or ERM)?
An entity-relationship model (ERM) is a graphical representation of the entities, relationships, and attributes in a database. It is a conceptual model that is used to design and maintain complex databases.
Chen notation, Crow Foot notation are some examples of developing ERD.

- #### What do you understand by the terms Entity, Entity Type, and Entity Set in DBMS?
**Entity**: A real world object like person, car etc<br>
**Entity type**: An abstract concept that represents entities. For example Person, Car etc<br>
**Entity set**: All instances/objects of same kind of entity. Example all persons, cars etc.

- #### List the different types of relationships in DBMS?
**One-to-One** - This can be defined as the relationship between two tables where
each record in one table is associated with the maximum of one record in the
other table.<br>
**One-to-Many & Many-to-One** - This is the most commonly used relationship
where a record in a table is associated with multiple records in the other table.<br>
**Many-to-Many** - This is used in cases when multiple instances on both sides are
needed for defining a relationship.<br>
**Self-Referencing Relationships** - This is used when a table needs to define a
relationship with itself.

- #### What are DBMS anomalies?
Database anomalies are inconsistencies in the data that can occur due to poor database design or incorrect data entry. There are three main types of database anomalies:<br>
**Insertion anomaly**: An insertion anomaly occurs when a new record cannot be inserted into a database because the required data is not available. For example, you might not be able to insert a new order record into a database if there is no customer record for the customer who placed the order.<br>
**Deletion anomaly**: A deletion anomaly occurs when deleting a record from a database causes other records to become inconsistent or incomplete. For example, if you delete a customer record from a database, you might also need to delete all of the order records associated with that customer.<br>
**Update anomaly**: An update anomaly occurs when updating a record in a database causes other records to become inconsistent or incomplete. For example, if you update the customer address in a database, you might also need to update the address in all of the order records associated with that customer.

- #### What is Normalization?
Database normalization is the process of organizing a database to minimize redundancy and improve data integrity. It is a systematic way to reduce data duplication and improve data consistency.

- #### What is De Normalization?
De Normalization is a database design technique that involves adding redundant data to a normalized database to improve read performance. It is often used for applications that need to retrieve data from multiple tables quickly.

- #### what are Dependencies in DBMS?
Dependencies in DBMS are relationships between different attributes in a database table. They can be used to ensure that the data in the table is consistent and accurate.

- #### What are the various forms of Normalization?
**First normal form (1NF)**: A relation is in first normal form if every attribute in that relation is a single valued attribute. Each table must have a primary key, which is a column or set of columns that uniquely identifies each row in the table.<br>
**Second normal form (2NF)**: Does not contain any partial dependency. Each non-prime attribute (an attribute that is not part of the primary key) must be dependent on the entire primary key.<br>
**Third normal form (3NF)**: Does not contain any transitive dependency. Each non-prime attribute must not be directly dependent on any other non-prime attribute.<br>
other are **BCNF** and **5NF**.

- #### Types of Dependencies in DBMS?
**Multi valued dependency (MVD)**: each attribute should have a single value. hence 1NF.<br>
**Functional dependency (FD)**: (X->Y) every attribute should depend on primary key. hence 2NF.<br>
**Transitive dependency OR Partial dependency (TD)**: (X->Y->Z then X->Z) functional dependency that occurs indirectly.hence 3NF.<br>

- #### Types of updates in DBMS?
**Logical Updates**: operations on the table level insert, update, delete.<br>
**Physical Updates**: operations on the schema level delete table, alter index etc.

- #### Intension and Extension in DBMS?
**Intension**: refers to the definition of a table, including the column names, data types, and constraints.<br>
**Extension**: refers to the set of all rows that are currently in the table.

- #### Explain the terms specialization and generalization?
**Specialization**: Specialization is a process of defining a set of subclasses of the entity type. Here,
each subclass will contain all the attributes and relationships of the parent entity. Apart from this, the
subclasses may contain additional attributes and relationships specific to itself.
**Generalization**: Generalization is a process of finding relations, common attributes for a particular
set of entities; and finally defining a common superclass for them.

- #### What are the different integrity rules present in the DBMS?
**Domain integrity constraints**: Domain integrity constraints ensure that the data in a column is of the correct type and within the specified range of values. For example, a domain integrity constraint might specify that a column can only contain numbers between 1 and 100.<br>
**Entity integrity constraints**: Entity integrity constraints ensure that each row in a table has a unique primary key value. The primary key is a column or set of columns that uniquely identifies each row in a table.<br>
**Referential integrity constraints**: Referential integrity constraints ensure that the values in a foreign key column match the values in the primary key column of a related table. For example, a referential integrity constraint might specify that the customer_id column in the orders table must match a value in the customer_id column of the customers table.<br>
**Key constraints**: Key constraints are a combination of domain integrity constraints, entity integrity constraints, and referential integrity constraints.

- #### What is Data Independence in DBMS?
Data independence in DBMS is the ability to modify the logical or physical structure of a database without affecting the application programs that use the database. This is achieved by separating the logical and physical views of the data.

- #### What different languages are supported by DBMS?
**DDL -  Data Definition Language**: These operations are used to create, alter, and drop database objects. create, alter, drop.<br>
For example, you can use a data definition operation to create a new table, add a new column to an existing table, or delete an existing table.<br>
**DQL - Data Query Language**: It is a language used to query data from a database. The most common database language is Structured Query Language (SQL). for example SELECT<br>
**DML - Data Manipulation operations**: These operations are used to insert, update, delete, and select data from database objects. for example create, update, delete.<br>
For example, you can use a data manipulation operation to insert a new row into a table, update the value of a column in a row, delete a row from a table, or select data from a table.<br>
**DCL - Data Control operations**: These operations are used to grant and revoke access to database objects, and to manage transactions. GRANT, Revoke, Lock table, unlock table.<br>
For example, you can use a data control operation to grant a user permission to update a table, or to roll back a transaction that has been partially completed.<br>
**TCL - Transaction Control Language**: It is a set of commands used to manage transactions in a database.
-A transaction is a unit of work that must be completed in its entirety. Commit, Rollback, SavePoint.

- #### What is an Index in DBMS?
A database index is a data structure that provides a quick lookup of data in a column
or columns of a table. It improves the performance of queries by storing the values of one or more columns in a sorted order. EX. Phone Book in Mobile.

- #### Types of Indexes?
**Unique Indexes**: A unique index is a type of database index that enforces uniqueness on the indexed columns. This means that no two rows in the table can have the same value for the indexed columns. improve data integrity and Performance EX. Customer ID Or Order ID etc.<br>
**Non Unique Indexes** A non-unique index is a type of database index that does not enforce uniqueness on the indexed columns. This means that multiple rows in the table can have the same value for the indexed columns. improve query performance. Ex. search customer by name.<br>
**Cluster Index**: The table rows are physically reordered to match the index. This means that the data in the table is stored in the same order as the index.<br>
**Non Cluster Index**:  the table rows are not physically reordered to match the index. This means that the data in the table is stored in a different order than the index.<br>
PostgreSQL only supports non-clustered indexes. This means that the table rows are not physically reordered to match the index.<br>
The main difference between clustered and non-clustered indexes is how the data in the table is physically stored.

- #### What is Index Hunting in DBMS?
Index hunting in databases is the process of finding the most efficient index to use for a given query. This can be done by the database optimizer, which is a software component that analyzes queries and determines the best way to execute them.


- #### What is concurrency control?
Concurrency control in DBMS is the process of managing simultaneous access to data by multiple users. It is important to have concurrency control in place to ensure that the data remains consistent and accurate, even when multiple users are updating it at the same time.<br>
There are two main types of concurrency control: locking and optimistic.<br>
**Locking**: Locking concurrency control uses locks to prevent multiple users from accessing the same data at the same time. When a user needs to access a piece of data, they must first acquire a lock on that data. Once they have acquired the lock, they are the only user who can access that data until they release the lock.<br>
**Optimistic**: Optimistic concurrency control does not use locks to prevent multiple users from accessing the same data at the same time. Instead, it assumes that users will not be updating the same data at the same time. If two users do try to update the same data at the same time, optimistic concurrency control will detect the conflict and resolve it.

- #### Define Database Transaction Properties OR What is ACID?
**ACID** is a set of properties that guarantee the reliability and consistency of data in a database. The acronym ACID stands for Atomicity, Consistency, Isolation, and Durability.<br>
**Atomicity** ensures that all or none of the changes made during a transaction are committed to the database. This means that if any part of a transaction fails, the entire transaction is rolled back and the database is left in its original state.<br>
**Consistency** ensures that the database is always in a valid state. This means that all of the data in the database is consistent with each other.<br>
**Isolation** ensures that concurrent transactions do not interfere with each other. This means that each transaction sees a consistent view of the database, as if it were the only transaction running.<br>
**Durability** ensures that once a transaction is committed, its changes are permanent and cannot be lost. This means that even if the database crashes, the changes made by the transaction will be restored when the database is restarted.

- #### What is DBMS Partitioning?
The process of dividing a database into smaller, more manageable units there are two types.<br>
**Horizontal partitioning**: Horizontal partitioning divides a table into rows, based on a specific criteria. For example, you could horizontally partition a customer table by region, so that each partition contains the customer data for a specific region.<br>
**Vertical partitioning**: Vertical partitioning divides a table into columns, based on a specific criteria. For example, you could vertically partition a customer table by order data, so that one partition contains the customer's name, address, and phone number, and another partition contains the customer's order history.

- #### What is DBMS Sharding?
Sharding in DBMS is a process of dividing a large database into smaller, more manageable parts. This is done to improve performance, scalability, and manageability.<br>
Sharded databases are typically distributed across multiple servers. This allows the database to handle a larger volume of data and more concurrent requests. It also makes the database more resilient to failures, since if one server fails, the other servers can continue to operate.<br>
There are two main types of sharding: horizontal and vertical.<br>
**Horizontal sharding**: Horizontal sharding divides a database table into rows, based on a specific criteria. For example, you could horizontally shard a customer table by region, so that each partition contains the customer data for a specific region.<br>
**Vertical sharding**: Vertical sharding divides a database table into columns, based on a specific criteria. For example, you could vertically shard a customer table by order data, so that one partition contains the customer's name, address, and phone number, and another partition contains the customer's order history.

- #### What is Difference between DBMS Partitioning and Sharding?
DBMS partitioning and sharding are both techniques for dividing a large database into smaller, more manageable parts. However, there are some key differences between the two.<br>
**Partitioning** is typically used to improve performance and manageability. It involves dividing a database table into smaller parts based on a specific criteria, such as date range, region, or customer type. Partitions can be stored on the same server or on different servers.<br>
**Sharding** is typically used to improve scalability and performance. It involves dividing a database table into smaller parts and distributing them across multiple servers. This allows the database to handle a larger volume of data and more concurrent requests.



