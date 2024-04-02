# SQL Syntax Types
## 2- Data Manipulation Language - DML:

#### 2.1- Insert
- Allows you to add data into records or rows.
 ~~~ sql
-- Statement Syntax
INSERT INTO table_name(first_column_name, second_column_name)
VALUES(first_value, second_value);
~~~
##### When using this syntax make sure to enter the values according to the columns name in the correct order.
 ~~~ sql
-- Statement Syntax
INSERT INTO table_name
VALUES(first_value, second_value);
~~~
#### 2.2- Update
- Allows you to renew your existing data of your table.
~~~ sql
-- Statement Syntax
UPDATE table_name
SET first_column_name = value
WHERE second_column_name = condition_value;
~~~
#### 2.3- Delete
- Functions similarly to TRUNCATE, but with DELETE we can choose what can be removed.
~~~ sql
-- Statement Syntax
DELETE 
FROM table_name
WHERE column_name = condition_value;
~~~
#### 2.4- Select
- Retrieves the data from database objects like tables.
##### This retrieves all the data from a certain table.
 ~~~ sql
-- Statement Syntax
SELECT * 
FROM table_name;
~~~
##### This retrieves only specific data from a certain table.
 ~~~ sql
-- Statement Syntax
SELECT first_column_name, second_column_name
FROM table_name;
~~~
##### This retrieves only distinct data without duplicates.
 ~~~ sql
-- Statement Syntax
SELECT DISTINCT column_name
FROM table_name;
~~~
## 3- DML Conditions
### 3.1- Where 
- Allows us to set a condition upon which we will specify what part of the data we want to retrieve from the database.
### 3.2- Having
- Functions similarly to WHERE but with an aggregate function.

## 4- DML Mathematical Operators
| SQL Syntax | Meaning                  |
| ---------- | ------------------------ |
| =          | equal to                 |
| != or <>   | not equal to             |
| >          | greater than             |
| >=         | greater than or equal to |
| <          | less than                |
| <=         | less than or equal to    |
## 5- DML Operators
### 4.1- And
- Combines two statements in the WHERE condition block.
- Requires both statements to return true to fulfill the condition on different columns.
- SQL executes it first regardless the order you type it.
### 4.2- Or 
-  Combines two statements in the WHERE condition block.
- Requires either statement to return true to fulfill the condition on the same columns.
- SQL executes it after the AND regardless the order you type it.
### 4.3- In and Not In
#### In
- Checks if a value matches any value in a list.
- Useful for filtering rows based on multiple possible values.
- Equivalent to multiple OR conditions.
#### Not In
- Checks if a value does not match any value in a list or subquery.
- Opposite of the IN operator.
- Useful for excluding rows based on specific values.
### 4.4- Like and Not like
#### Like 
- Checks if a string value matches a specified pattern using wildcard characters (% or _).
- % represents zero or more characters, and _ represents a single character.
#### Not Like
- Checks if a string value does not match a specified pattern using wildcard characters (% or _).
- Opposite of the LIKE operator.
- Useful for excluding rows based on specific patterns within strings.
### 4.5- Between
- Checks if a value lies within a specified range.
- Useful for filtering rows based on numerical or date ranges.
### 4.6- Is null and Is Not Null
#### Is Null 
- Checks if a column contains a NULL value.
- Returns true if the value is NULL, otherwise false.
- Useful for filtering rows where a column has no value.
#### Is Not Null 
- Checks if a column does not contain a NULL value.
- Returns true if the value is not NULL, otherwise false.
- Useful for filtering rows where a column has a non-null value.
## 6- DML Aggregate Functions

### 6.1- Count
- counts the number of non-null record in a field.
~~~ sql
-- Statement Syntax
SELECT COUNT(column_name)
FROM table_name;
~~~
### 6.2- Sum
- sums all the non-null values in a column.
~~~ sql
-- Statement Syntax
SELECT SUM(column_name)
FROM table_name;
~~~
### 6.3- Average
- calculates the average of all non-null values in a column.
~~~ sql
-- Statement Syntax
SELECT AVG(column_name)
FROM table_name;
~~~
### 6.4- Max
- returns the maximum value in a column.
  ~~~ sql
-- Statement Syntax
SELECT MAX(column_name)
FROM table_name;
~~~
### 6.5- Min
- returns the minimum value in a column.
  ~~~ sql
-- Statement Syntax
SELECT MIN(column_name)
FROM table_name;
~~~
### 6.6- Round
- A function used to round a numeric value to a specified number of decimal places.
- Typically takes two arguments: the numeric value to be rounded and the number of decimal places.
~~~ sql
-- Statement Syntax
SELECT ROUND(column_name, decimal_to_round) 
FROM table_name;
~~~
### 6.7- Coalesce
- A function used to return the first non-null value.
- Useful for handling null values in SQL queries.

## 7- DML Query Organization
### 7.1- Order By
- Arranges the result set in a specified order (ascending or descending) based on one or more columns.
~~~ sql
-- Statement Syntax
SELECT *
FROM table_name
ORDER BY column_name ASC;
~~~

~~~ sql
-- Statement Syntax
SELECT *
FROM table_name
ORDER BY column_name DESC;
~~~
### 7.2- Group By 
- Used to group rows that have the same values into summary rows.
- Must be used with aggregate function's.
~~~ sql
-- Statement Syntax
SELECT column_name, COUNT(column_name) 
FROM table_name
GROUP BY column_name;
~~~
### 7.3- Aliasing
- used to rename a selection from a query.
~~~ sql
-- Statement Syntax
SELECT column_name, COUNT(column_name) AS new_column_name
FROM table_name
GROUP BY column_name;
~~~
### 7.4- Limit
- Specifies the maximum number of rows returned by a query.
- Useful for controlling the size of query results, particularly when dealing with large datasets.
- The following code gets the top 5 based on the given columns.

~~~ sql
-- Statement Syntax
SELECT first_column_name, 
       COUNT(second_column_name) AS new_column_name
FROM table_name
GROUP BY first_column_name
ORDER BY new_column_name DESC
LIMIT 5;
~~~