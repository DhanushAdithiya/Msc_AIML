---
id: SQL Datatypes and Commands
aliases: []
tags: []
---

# SQL Datatypes and Commands

## SQL Datatype
### String
- CHAR(SIZE) - fixed length
- VARCHAR(SIZE) - variable length

### Numeric
- INT
- FLOAT
- BIGINT
- DOUBLE(size, d) - size is total number of digits, d is the number of digits after the decimal point


## DDL (Data Definition Language)

DDL consists of sql commands that are used to define the database scheme.It is simply used to create and modify the struce of databse objects inthe database.

### CREATE
Create database or its objects.
**SYNTAX**
```js
CREATE TABLE table_name (col1, data_tye, col2, data_type)
```
**Example**
```js
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```

### ALTER
This command is used to add, delte or modify cols in an existing table
**SYNTAX**
```js
    ALTER TABLE table_name
    ADD column_name datatype;
    DROP COLUMN column_name
    RENAME COLUMN old_name to new_name
    ALTER COLUMN column name datatype
    MODIFY COLUMN column_name datatype
```

#### Constraints
Constraints are used to specify the rules for the data in a table.
They can be specified while creating a table or can be used while modifying a table with **ALTER** command.

Some commonly used constraints are
- **NOT NULL** - Ensures that the col cannot have null
- **UNIQUE** - Ensures that all values in the column are unique 
- **PRIMARY KEY** - 
- **FOREIGN KEY** - 
    ```js
    CREATE TABLE Orders (
        PersonID int,
        FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
    );

   CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
    ); 
    ```
- **CHECK** - Ensures that each value in the column satisfies a specific condition
    ```js
    CREATE TABLE Persons (
        Age int,
        CHECK (Age>=18)
    );
    ```
- **DEFAULT** - Sets a default calue of the col if no value is specified
    ```js
    CREATE TABLE Persons (
        City varchar(255) DEFAULT 'Sandnes'
    );
    ```

### DROP
This command is used to drop an existing table in a databse
**SYNTAX**
```js
DROP TABLE table_name;
```
### TRUNCATE
This command is used to delte the values but not the table
**SYNTAX**
```js
TRUNCATE TABLE table_name;
```

## DML (Data Manipulation Language)
The SQL commands that deal with the manipulation of data present in the database.

### INSERT INTO
Used to insert new records in a table
**SYNTAX**
```js
INSERT INTO table_name
VALUES (val1, val2, val3)
```

### UPDATE
Used to modify the existing records in a table
**SYNTAX**
```js
UPDATE table_name
SET col1 = new_val, col2 = new_val
WHERE col = val
```

### DELETE
The delete statement is used to delte existing records in a table
**SYNTAX**
```js
DELETE FROM table_name WHERE condition
```

