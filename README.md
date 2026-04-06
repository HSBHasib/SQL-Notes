# SQL-Notes

---

## 1️⃣ What is a Database?
```js
↪ It is a collection of data in a format that can be easily accessed.

Why databases?
 • Can store large data
 • Features like security, scalability etc.
 • Easier to insert, update or delete data. 
```

---

## 2️⃣ SQL vs NoSQL
| Feature | SQL                  | NoSQL           |
| ------- | -------------------- | --------------- |
| Type    | Relational           | Non-relational  |
| Data    | Table (rows/columns) | JSON, key-value, graph, etc |
| Schema/Design  | Fixed                | Flexible        |
| Example | MySQL, Oracle, PostgreSQL    | MongoDB, Cassandra, Neo4j, etc |

---

## 3️⃣ What is SQL?
```js
↪ SQL (Structured Query Language)
SQL is a programming language used to interact with relational databases.
```

---

## 4️⃣ What is a Table?
```js
↪ A table is a collection of rows and columns used to store data.
```

---

### Create New Database
```js
CREATE DATABASE users;
CREATE DATABASE IF NOT EXISTS users;
```

### Delete Database
```js
DROP DATABASE users;
DROP DATABASE IF EXISTS users;
```

### Show Database -(It Show all the Databases Info)
```js
Show DATABASES;
```

### Select The Database
```js
USE users;
```

---

### Table Queries
```js
 • Create  - (Create New Table)
 • Insert  - (Add Data Into Table)
 • Update  - (Update The Data In Table)
 • Alter   - (Change The Table Schema/Column)
 • Truncate - (Delete All The In Table)
 • Delete  - (Delete The Table)
```

###  Create New Table
```js
CREATE TABLE table_name (
  column_name1 datatype constraint, - (Constraint Optional )
  column_name2 datatype constraint,
  column_name3 datatype constraint
);

// Example: -
CREATE TABLE students (
  id INT,
  name VARCHAR(50),
  age INT
);
```

###  Insert Data Into Table
```js
INSERT INTO students
(id, name, age)
VALUES
(1, 'Hasib', 20),
(2, 'Adib', 22);
```

### Show TABLES -(It Show all the TABLES Info)
```js
Show TABLES;
```

### Constraints
```js
// Rules of data in the table
• NOT NULL  - columns cannot have a null value
• UNIQUE    - all values in column are different
• DEFAULT   - sets the default values of a column  
• CHECK     - it can limit the values allowed in a column

// Example: -
CREATE TABLE students (
  id INT,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(50) UNIQUE,
  follwers INT DEFAULT 0,
  age INT,
  CONSTRAINT age_check CHECK (age >= 13)  - (age-check it is a name and name is optinal)
);

• PRIMARY KEY  - makes a column unique & not null but used only for one
                 CREATE TABLE temp (
                  id INT NOT NULL,
                  PRIMARY KEY (id)
                 );

• FOREIGN KEY  - prevent actions that would destroy links between tables
                 CREATE TABLE temp (
                  cust_id INT,
                  FOREIGN KEY (cust_id) REFERENCES customers(id)
                 );
 
--------------------------------------------------------------------------------------------------------

• What are KEYS?
 KEY is a special column in the table

• Primary Key
It is a column (or set of columns) in a table that uniquely identifies each row. (a unique id)
There is only 1 PK & it should be NOT null

• Foreign Key
A foreign key is a column (or set of columns) in a table that refers to the primary key in another table.
FKs can have duplicate & null values.

There can be multiple FKs.
```

---

### Select & Show data from DB 
```js
// Show The Specific Data
SELECT col1, col2 FROM table_name;

// ( DISTINCT ) - Select The Unique Data
SELECT DISTINCT age FROM table_name;

// to show all table data
SELECT * FROM table_name;

```

---

