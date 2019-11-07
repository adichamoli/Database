# Database
SQL is a database computer language designed for the retrieval and management of data in a relational database. SQL stands for Structured Query Language.

SQL is Structured Query Language, which is a computer language for storing, manipulating and retrieving data stored in a relational database.

SQL is the standard language for Relational Database System. All the Relational Database Management Systems (RDMS) like MySQL, MS Access, Oracle, Sybase, Informix, Postgres and SQL Server use SQL as their standard database language.

Also, they are using different dialects, such as −

- MS SQL Server using T-SQL,
- Oracle using PL/SQL,
- MS Access version of SQL is called JET SQL (native format) etc.

# Applications of SQL
- As mentioned before, SQL is one of the most widely used query language over the databases. I'm going to list few of them here:
- Allows users to access data in the relational database management systems.
- Allows users to describe the data.
- Allows users to define the data in a database and manipulate that data.
- Allows to embed within other languages using SQL modules, libraries & pre-compilers.
- Allows users to create and drop databases and tables.
- Allows users to create view, stored procedure, functions in a database.
- Allows users to set permissions on tables, procedures and views.

# SQL Process

<img src="https://www.tutorialspoint.com/sql/images/sql-architecture.jpg" align="right">

When you are executing an SQL command for any RDBMS, the system determines the best way to carry out your request and SQL engine figures out how to interpret the task.

There are various components included in this process.

These components are
- Query Dispatcher
- Optimization Engines
- Classic Query Engine
- SQL Query Engine, etc.
A classic query engine handles all the non-SQL queries, but a SQL query engine won't handle logical files.

Following is a simple diagram showing the SQL Architecture −

# SQL Commands
The standard SQL commands to interact with relational databases are CREATE, SELECT, INSERT, UPDATE, DELETE and DROP. These commands can be classified into the following groups based on their nature −

## DDL - Data Definition Language
Sr.No.	 | Command    | Description
| ------ | -----------|--------------------------------------------------------------------------------- |
| 1	     | CREATE     | Creates a new table, a view of a table, or other object in the database.         |
| 2	     | ALTER      | Modifies an existing database object, such as a table.                           |
| 3	     | DROP       | Deletes an entire table, a view of a table or other objects in the database.     |

## DML - Data Manipulation Language
Sr.No.	 | Command    | Description
| ------ | -----------|--------------------------------------------------------------------------------- |
| 1      | SELECT     | Retrieves certain records from one or more tables.                               |
| 2 	   | INSERT     | Creates a record.                                                                |
| 3	     | UPDATE     | Modifies records.                                                                |
| 4      | DELETE     | Deletes records.                                                                 |

## DCL - Data Control Language
Sr.No.	 | Command    | Description
| ------ | -----------|--------------------------------------------------------------------------------- |
| 1	     | GRANT      | Gives a privilege to user.                                                       |
| 2      | REVOKE     | Takes back privileges granted from user.                                         |

## TCL - Transaction Control Language
Sr.No.	 | Command    | Description
| ------ | -----------|--------------------------------------------------------------------------------- |
| 1	     | COMMIT     | Commit changes to database                                                       |
| 2      | ROLLBACK   | Rolled back the unsaved DB changes                                               |
| 3      | SAVEPOINT  | Creates a savepoint                                                              |

# CREATE DATABASE
Syntax
The basic syntax of this CREATE DATABASE statement is as follows −
    
    CREATE DATABASE DatabaseName;

Always the database name should be unique within the RDBMS.

Example
If you want to create a new database <testDB>, then the CREATE DATABASE statement would be as shown below −
    
    SQL> CREATE DATABASE testDB;
    
# DROP DATABASE
Syntax
The basic syntax of DROP DATABASE statement is as follows −

    DROP DATABASE DatabaseName;
Always the database name should be unique within the RDBMS.

Example
If you want to delete an existing database <testDB>, then the DROP DATABASE statement would be as shown below −

    SQL> DROP DATABASE testDB;
