# SQL Syntax Types
## 3- Data Control Language - DCL:
- Allow us to manage the rights the users have in the database.
- People who complete rights to the database are called database administrators.
- permission_type can be CREATE, SELECT, TRUNCATE, DROP, INSERT, ALTER, ALL.
##### The following will create new database user credentials.
~~~ sql
-- Statement Syntax
CREATE USER 'zyad'@'localhost IDENTIFIED BY 'my_passowrd';
~~~

#### 3.1- Grant
- Gives certain permissions to users.
~~~ sql
-- Statement Syntax
GRANT permission_type ON database_name.table_name 
TO 'username'@'localhost';
~~~
#### 3.2- Revoke
- Used to remove any permissions and privileges of database users.
~~~ sql
-- Statement Syntax
REVOKE permission_type ON database_name.table_name 
TO 'username'@'localhost';
~~~