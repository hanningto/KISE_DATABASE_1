
# Database and SQL Basics

## 1. Creating a Database

### 1.1 Creating a Database
To create a new database, use the following SQL command:
```sql
CREATE DATABASE database_name;
```
Replace `database_name` with the desired name of your database.

### 1.2 Selecting a Database
Once the database is created, you can select it for use:
```sql
USE database_name;
```

### 1.3 Creating a Table
To create a table within a database, define columns and data types:
```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    ...
);
```
For example:
```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    Age INT,
    Gender CHAR(1)
);
```

### 1.4 Viewing Tables
To see the list of tables in the current database:
```sql
SHOW TABLES;
```

### 1.5 Data Types
Some common data types include:
- `INT` - Integer
- `VARCHAR(size)` - Variable-length string
- `DATE` - Date format
- `FLOAT` - Floating point numbers

### 1.6 Constraints
Constraints help maintain data integrity. Common constraints are:
- `PRIMARY KEY`: Uniquely identifies each record
- `FOREIGN KEY`: Establishes a relationship between tables
- `NOT NULL`: Ensures a column cannot have a NULL value
- `UNIQUE`: Ensures all values in a column are unique

### 1.7 Changing a Column
To modify a column, use:
```sql
ALTER TABLE table_name MODIFY COLUMN column_name new_datatype;
```

### 1.8 Dropping a Column
To remove a column from a table:
```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

### 1.9 Altering a Column
To rename or change a column’s type:
```sql
ALTER TABLE table_name CHANGE old_column_name new_column_name new_datatype;
```

## 2. Adding Records

### 2.1 Inserting Data
Insert new records into a table using:
```sql
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
```

### 2.2 Loading Data from a File
To load data from a file, use:
```sql
LOAD DATA INFILE 'file_path' INTO TABLE table_name;
```

## 3. Viewing Records

### 3.1 Viewing All Records
To see all records in a table:
```sql
SELECT * FROM table_name;
```

### 3.2 Using AND & OR Conditions
Use `AND` and `OR` to filter records based on multiple conditions:
```sql
SELECT * FROM table_name WHERE condition1 AND condition2;
SELECT * FROM table_name WHERE condition1 OR condition2;
```

### 3.3 ALIAS
Use ALIAS to rename columns or tables temporarily:
```sql
SELECT column_name AS alias_name FROM table_name;
```

### 3.4 DISTINCT
To remove duplicate entries from the result:
```sql
SELECT DISTINCT column_name FROM table_name;
```

## 4. Aggregate Functions

### 4.1 COUNT
Count the number of records in a table:
```sql
SELECT COUNT(column_name) FROM table_name;
```

### 4.2 SUM
Calculate the sum of a numeric column:
```sql
SELECT SUM(column_name) FROM table_name;
```

### 4.3 MIN
Find the smallest value in a column:
```sql
SELECT MIN(column_name) FROM table_name;
```

### 4.4 AVG
Calculate the average value of a numeric column:
```sql
SELECT AVG(column_name) FROM table_name;
```

## 5. Database Clauses

### 5.1 WHERE
Use `WHERE` to filter records based on a condition:
```sql
SELECT * FROM table_name WHERE condition;
```

### 5.2 ORDER BY
Sort the result in ascending or descending order:
```sql
SELECT * FROM table_name ORDER BY column_name ASC;
SELECT * FROM table_name ORDER BY column_name DESC;
```

### 5.3 GROUP BY
Group records that have the same values in specified columns:
```sql
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name;
```

### 5.4 HAVING
Filter records after grouping with `GROUP BY`:
```sql
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name HAVING COUNT(*) > 1;
```

## 6. Character Functions

### 6.1 LIKE
Use `LIKE` for pattern matching:
```sql
SELECT * FROM table_name WHERE column_name LIKE 'pattern%';
```

### 6.2 REGEXP
Use `REGEXP` for complex pattern matching:
```sql
SELECT * FROM table_name WHERE column_name REGEXP 'pattern';
```

### 6.3 CONCAT
Combine multiple strings into one:
```sql
SELECT CONCAT(column1, column2) AS combined_column FROM table_name;
```

### 6.4 CHARACTER_LENGTH
Get the length of a string in a column:
```sql
SELECT CHARACTER_LENGTH(column_name) FROM table_name;
```

### 6.5 LOWER
Convert string to lowercase:
```sql
SELECT LOWER(column_name) FROM table_name;
```

### 6.6 SUBSTR
Extract a substring from a column:
```sql
SELECT SUBSTR(column_name, start_position, length) FROM table_name;
```

---
This document serves as a basic guide for database and SQL operations.
