# SQL Syntax Types

## 1- Data Definition Language - DDL:
- Set of statements that allow the user to ==define== and ==modify== data structure and objects such as tables.

### 1.1- Create Statement:
- Used for creating entire database and database objects as tables.
```sql
-- Statement Syntax
CREATE DATABASE IF NOT EXISTS database_name;
```

```sql
-- Statement Syntax
CREATE TABLE table_name(column_name data_type);
```

- After creating the database, we can verify that our queries are executed on the correct database by running the following command.

```sql
-- Statement Syntax
USE database_name;
```

- Examples from the relational schema:
#### 1.1.1- Companies Table
~~~ sql 
CREATE TABLE companies 
(
company_id INT AUTO_INCREMENT,
company_name VARCHAR(15),
headquarters_phone_number VARCHAR(10),
PRIMARY KEY (company_id)
);
~~~
#### 1.1.2- Items Table
~~~ sql 
CREATE TABLE items
(
item_code INT AUTO_INCREMENT,
item VARCHAR(10),
unite_price FLOAT,
company_id INT,
PRIMARY KEY (item_code),
FOREIGN KEY (company_id) REFERENCES companies (company_id) ON DELETE CASCADE
);
~~~
#### 1.1.3- Customers Table
~~~ sql 
CREATE TABLE customers
(
customer_id INT AUTO_INCREMENT,
first_name VARCHAR(10),
last_name VARCHAR(10),
email_address VARCHAR(20),
number_of_complaints INT DEFAULT 0,
PRIMARY KEY (customer_id),
UNIQUE KEY (email_address)
);
~~~
#### 1.1.4- Sales Table
```sql
-- Statement Syntax
CREATE TABLE sales
(
purchase_number INT AUTO_INCREMENT,
date_of_purchase DATE NOT NUL,
customer_id INT,
item_code VARCHAR(10),
PRIMARY KEY (purchase_number),
FOREIGN KEY (customer_id) REFERENCES customers(customer_id) ON DELETE CASCADE
);
```

### 1.2- Alter Statement:
- Used when altering existing objects.
#### 1.2.1- Add 
- Allows you to add a new column to an existing table in a relational database.
```sql
-- Statement Syntax
ALTER TABLE table_name
ADD COLUMN column_name data_type;
```
#### 1.2.2- Drop
- Removes an entire table from the database, including all its data and structure.
~~~ sql
-- Statement Syntax
DROP TABLE table_name;
~~~
#### 1.2.3- Truncate
- Removes all rows from a table, effectively resetting the table to its original state with no data.
~~~ sql
-- Statement Syntax
TRUNCATE TABLE table_name;

~~~
#### 1.2.4- Rename
- Allows you to change the name of a table to a new specified name within the database.
~~~ sql
-- Statement Syntax
RENAME TABLE table_name TO new_table_name;
~~~


