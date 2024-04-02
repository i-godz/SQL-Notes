# What is SQL
- Stands for ==structured query language==.
- A programming declarative language specifically designed for working with databases
- Create, manipulate and share data from relational database management systems by writing queries.
- Queries are a piece of code that prompts the computer to execute a certain operation that will deliver the desired output.
# SQL vs (MySQL, SQL Server, Oracle, SQLite)
- MySQL, SQL Server, Oracle and SQLite are multiple RDBMS which are based on SQL.
- They support different forms of the ==original language== and there are only slight difference between the different versions.
# Relation Database Management Systems
- RDBMS is a type of database management system that organizes data into structured tables with rows and columns.
- It follows the relational model, where data is stored in tables related to each other through common attributes or keys.

![](https://i.imgur.com/x8S3gsO.png)

- The table would look like this if there was no relation and the data was stored in a single table:

![](https://i.imgur.com/KjSPBfd.png)

## Database Design 
### Entity Relationship Diagram - ERD:
- Provides a high-level overview of the entire database system, illustrating the entities, their attributes, and the relationships between them.
- Used during the database design phase to visualize and plan the database structure, as well as to communicate the database schema to stakeholders.

![](https://i.imgur.com/k9wAt9O.png)

- Entities are the objects or concepts represented in the database, such as customers, orders, products, etc.
- Attributes are the properties or characteristics of entities, shown within the entities in the ERD.
### Relational Schema:
- Focuses on the detailed structure of individual tables, including their attributes and constraints.
- Used primarily by database designers and developers to design and implement individual database tables.

![](https://i.imgur.com/jrnQSzA.png)
#### Relationships 
- shows how entities are related to each other, such as one-to-one, one-to-many, or many-to-many relationships.

## Database Data Types

### 1- String 
#### 1.1- Character
| Function | Storage | Example | Length | Bytes |
| -------- | ------- | ------- | ------ | ----- |
| CHAR(5)  | fixed   | zyad    | 4      | 5     |
| CHAR(5)  | fixed   | bob     | 3      | 5     
#### 1.2- Variable Character
| Function   | Storage  | Example | Length | Bytes |
| ---------- | -------- | ------- | ------ | ----- |
| VARCHAR(5) | variable | zyad    | 4      | 4     |
| VARCHAR(5) | variable | bob     | 3      | 3     |
### 2- Integers
#### 2.1- Integers
- whole numbers with no decimal points
- function syntax as int.
#### 2.2- Float
- numbers with decimal points.
- function syntax as float.
### 3- Dates

#### 3.1- Date 
- used to represent a date in the format of YYYY-MM-DD
#### 3.2- DateTime
- next to the date we can also save time in the format of YYYY-MM-DD HH:MM:SS
#### 3.3- Timestamp 
- represents a moment in time as a number that allows you to easily obtain the difference between to timestamp values.
- appropriate to handle time zones.

## Database Constraints

### 1- Primary Key 
- uniquely identify each record (or row) within an entity and are represented in ERD to illustrate uniqueness.
- cannot be null.
### 2- Foreign Key
- are attributes in one entity that refer to the primary key in another entity, representing relationships between entities.
### 3- Not Null
- Ensures a column cannot have empty values (NULL).
- Guarantees every row has data in that specific column.
### 4- Default
- Specify a default value for a column when no value is provided during an INSERT operation.
### 5- Unique Key
-  Ensures that each value in a specified column or set of columns is unique across the entire table.
- Prevents duplicate entries in the specified column(s).
### 6- Auto Increment
- -Automatically generates a unique number for each new row inserted.
- Often used for ID columns and indexes.
### 7- On Delete Cascade
- if a specific value from the parents table primary key has been deleted, all the records from the child table referring to this value will be deleted as well.

