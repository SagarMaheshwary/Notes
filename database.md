# DATABASE

### NOTES

#### JOINS

- INNER JOIN/JOIN, returns rows if condition on both sides is true.
- LEFT JOIN/LEFT OUTER JOIN, returns rows from left table and rows from right table which only match the condition.
- RIGHT JOIN/RIGHT OUTER JOIN, returns rows from right table and rows from left table which only match the condition.
- FULL JOIN, returns rows from both tables whether the condition matches or not.

#### ORDER OF THE QUERY EXECUTION

- **FROM & JOINs** determine & filter rows
- **WHERE** more filters on the rows
- **GROUP BY** combines those rows into groups
- **HAVING** filters groups
- **SELECT** select columns
- **LIMIT** filters on the remaining rows/groups
- **ORDER BY** arranges the remaining rows/groups (order by column works even if it's not in the select statement unless distinct is used)

### TOPICS

- Table
- Table constraints
- Primary key
- **Primary key** consisting of multiple columns is called **Composite key**.
- Unique key
- Foreign key
- **Foreign key** consisting of multiple columns is called **Compound key**.
- Indexes
- Advantages and disadvantages of Indexes
- Joins
- Views
- Union
- Cursors
- Database engine ( aka Database server)
- Storage engine
- Stored Procedures
- **Triggers** are a special type of stored procedures that are executed on events like insert, update, and delete.
- Functions
- Stored Procedures vs Functions
- Aggregate functions
- Group by
- Order by
- group by vs Order by
- Subqueries
- Limit
- ACID
- Transactions
- Locks
  - Exclusive
  - Shared
- Having vs Where
- Normalization
  - 1NF
  - 2NF
  - 3NF

### SQL QUERIES TO PRACTICE

- EASY:
  - Create database
  - Create table
  - Create foreign keys
  - Create indexes
  - Create composite primary and foreign keys
  - Create, update, select, and delete rows
  - Joins: inner, left, right, (left and right are outer joins)
  - Group by
  - Order by
  - Aggregate functions
- MEDIUM/HARD:
  - Transactions
  - Locks
  - Design a database for a blog
  - Get all posts with user (tables: users, posts)
  - Get all users with post count (tables: users, posts)
  - Get all posts with categories (tables: posts, categories, and post_category (pivot table))
  - Get all posts with categories and user (tables: users, posts, categories, and post_category (pivot table))
  - Get all comments and their replies with user (tables: users, comments (replies are stored in the same table))
  - Get top categories by posts (tables: posts, categories, and post_category (pivot table))
