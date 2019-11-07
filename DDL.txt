# CREATE TABLE

Creating a basic table involves naming the table and defining its columns and each column's data type.

The SQL CREATE TABLE statement is used to create a new table.

Syntax
The basic syntax of the CREATE TABLE statement is as follows −

    CREATE TABLE table_name(
      column1 datatype,
      column2 datatype,
      column3 datatype,
      .....
      columnN datatype,
      PRIMARY KEY( one or more columns )
    );
CREATE TABLE is the keyword telling the database system what you want to do. In this case, you want to create a new table. The unique name or identifier for the table follows the CREATE TABLE statement.

Then in brackets comes the list defining each column in the table and what sort of data type it is. The syntax becomes clearer with the following example.

A copy of an existing table can be created using a combination of the CREATE TABLE statement and the SELECT statement. You can check the complete details at Create Table Using another Table.

Example
The following code block is an example, which creates a CUSTOMERS table with an ID as a primary key and NOT NULL are the constraints showing that these fields cannot be NULL while creating records in this table −

    SQL> CREATE TABLE CUSTOMERS(
         ID   INT              NOT NULL,
         NAME VARCHAR (20)     NOT NULL,
         AGE  INT              NOT NULL,
         ADDRESS  CHAR (25) ,
         SALARY   DECIMAL (18, 2),       
         PRIMARY KEY (ID));
         
You can verify if your table has been created successfully by looking at the message displayed by the SQL server, otherwise you can use the DESC command as follows −

    SQL> DESC CUSTOMERS;
         +---------+---------------+------+-----+---------+-------+
         | Field   | Type          | Null | Key | Default | Extra |
         +---------+---------------+------+-----+---------+-------+
         | ID      | int(11)       | NO   | PRI |         |       |
         | NAME    | varchar(20)   | NO   |     |         |       |
         | AGE     | int(11)       | NO   |     |         |       |
         | ADDRESS | char(25)      | YES  |     | NULL    |       |
         | SALARY  | decimal(18,2) | YES  |     | NULL    |       |
         +---------+---------------+------+-----+---------+-------+
         5 rows in set (0.00 sec)

Now, you have CUSTOMERS table available in your database which you can use to store the required information related to customers.

# DROP TABLE

The SQL DROP TABLE statement is used to remove a table definition and all the data, indexes, triggers, constraints and permission specifications for that table.

<b>NOTE</b> − You should be very careful while using this command because once a table is deleted then all the information available in that table will also be lost forever.

Syntax
The basic syntax of this DROP TABLE statement is as follows −

    DROP TABLE table_name;

Example
Let us first verify the CUSTOMERS table and then we will delete it from the database as shown below −

    SQL> DESC CUSTOMERS;
         +---------+---------------+------+-----+---------+-------+
         | Field   | Type          | Null | Key | Default | Extra |
         +---------+---------------+------+-----+---------+-------+
         | ID      | int(11)       | NO   | PRI |         |       |
         | NAME    | varchar(20)   | NO   |     |         |       |
         | AGE     | int(11)       | NO   |     |         |       |
         | ADDRESS | char(25)      | YES  |     | NULL    |       |
         | SALARY  | decimal(18,2) | YES  |     | NULL    |       |
         +---------+---------------+------+-----+---------+-------+
          5 rows in set (0.00 sec)

This means that the CUSTOMERS table is available in the database, so let us now drop it as shown below.

      SQL> DROP TABLE CUSTOMERS;
      Query OK, 0 rows affected (0.01 sec)

Now, if you would try the DESC command, then you will get the following error −

      SQL> DESC CUSTOMERS;
      ERROR 1146 (42S02): Table 'TEST.CUSTOMERS' doesn't exist

Here, TEST is the database name which we are using for our examples.

# ALTER TABLE

The Oracle ALTER TABLE statement is used to add, modify, or drop/delete columns in a table. The Oracle ALTER TABLE statement is also used to rename a table.

### Add column in table
Syntax
To ADD A COLUMN in a table, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      ADD column_name column_definition;

Example
Let's look at an example that shows how to add a column in an Oracle table using the ALTER TABLE statement.

    ALTER TABLE customers
      ADD customer_name varchar2(45);

This Oracle ALTER TABLE example will add a column called customer_name to the customers table that is a data type of varchar2(45).

In a more complicated example, you could use the ALTER TABLE statement to add a new column that also has a default value:

    ALTER TABLE customers
      ADD city varchar2(40) DEFAULT 'Seattle';

In this example, the column called city has been added to the customers table with a data type of varchar2(40) and a default value of 'Seattle'.

### Add multiple columns in table

Syntax
To ADD MULTIPLE COLUMNS to an existing table, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      ADD (column_1 column_definition,
           column_2 column_definition,
           ...
           column_n column_definition);

Example
Let's look at an example that shows how to add multiple columns in an Oracle table using the ALTER TABLE statement.

    ALTER TABLE customers
      ADD (customer_name varchar2(45),
           city varchar2(40) DEFAULT 'Seattle');

This Oracle ALTER TABLE example will add two columns, customer_name as a varchar2(45) field and city as a varchar2(40) field with a default value of 'Seattle' to the customers table.

### Modify column in table

Syntax
To MODIFY A COLUMN in an existing table, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      MODIFY column_name column_type;

Example
Let's look at an example that shows how to modify a column in an Oracle table using the ALTER TABLE statement.

    ALTER TABLE customers
      MODIFY customer_name varchar2(100) NOT NULL;

This Oracle ALTER TABLE example will modify the column called customer_name to be a data type of varchar2(100) and force the column to not allow null values.

In a more complicated example, you could use the ALTER TABLE statement to add a default value as well as modify the column definition:

    ALTER TABLE customers
      MODIFY city varchar2(75) DEFAULT 'Seattle' NOT NULL;

In this example, the ALTER TABLE statement would modify the column called city to be a data type of varchar2(75), the default value would be set to 'Seattle' and the column would be set to not allow null values.

### Modify Multiple columns in table

Syntax
To MODIFY MULTIPLE COLUMNS in an existing table, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      MODIFY (column_1 column_type,
              column_2 column_type,
              ...
              column_n column_type);

Example
Let's look at an example that shows how to modify multiple columns in an Oracle table using the ALTER TABLE statement.

    ALTER TABLE customers
      MODIFY (customer_name varchar2(100) NOT NULL,
              city varchar2(75) DEFAULT 'Seattle' NOT NULL);

This Oracle ALTER TABLE example will modify both the customer_name and city columns. The customer_name column will be set to a varchar2(100) data type and not allow null values. The city column will be set to a varchar2(75) data type, its default value will be set to 'Seattle', and the column will not allow null values.

### Drop column in table
Syntax
To DROP A COLUMN in an existing table, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      DROP COLUMN column_name;

Example
Let's look at an example that shows how to drop a column in an Oracle table using the ALTER TABLE statement.

    ALTER TABLE customers
     DROP COLUMN customer_name;

This Oracle ALTER TABLE example will drop the column called customer_name from the table called customers.

### Rename column in table
Syntax

To RENAME A COLUMN in an existing table, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      RENAME COLUMN old_name TO new_name;

Example
Let's look at an example that shows how to rename a column in an Oracle table using the ALTER TABLE statement.

    ALTER TABLE customers
      RENAME COLUMN customer_name TO cname;

This Oracle ALTER TABLE example will rename the column called customer_name to cname.

### Rename table
Syntax
To RENAME A TABLE, the Oracle ALTER TABLE syntax is:

    ALTER TABLE table_name
      RENAME TO new_table_name;

Example
Let's look at an example that shows how to rename a table in Oracle using the ALTER TABLE statement.

    ALTER TABLE customers
      RENAME TO contacts;

This Oracle ALTER TABLE example will rename the customers table to contacts.
