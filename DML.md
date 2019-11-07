# INSERT

The SQL INSERT Statement is used to add new rows of data to a table in the database.

Syntax
There are two basic syntaxes of the INSERT statement which are shown below.

    INSERT INTO TABLE_NAME (column1, column2, column3,...columnN)  
    VALUES (value1, value2, value3,...valueN);

Here, column1, column2, column3,...columnN are the names of the columns in the table into which you want to insert the data.

You may not need to specify the column(s) name in the SQL query if you are adding values for all the columns of the table. But make sure the order of the values is in the same order as the columns in the table.

The SQL INSERT INTO syntax will be as follows −

    INSERT INTO TABLE_NAME VALUES (value1,value2,value3,...valueN);

Example
The following statements would create six records in the CUSTOMERS table.

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (1, 'Ramesh', 32, 'Ahmedabad', 2000.00 );

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (2, 'Khilan', 25, 'Delhi', 1500.00 );

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (3, 'kaushik', 23, 'Kota', 2000.00 );

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (4, 'Chaitali', 25, 'Mumbai', 6500.00 );

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (5, 'Hardik', 27, 'Bhopal', 8500.00 );

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (6, 'Komal', 22, 'MP', 4500.00 );

You can create a record in the CUSTOMERS table by using the second syntax as shown below.

    INSERT INTO CUSTOMERS 
    VALUES (7, 'Muffy', 24, 'Indore', 10000.00 );

All the above statements would produce the following records in the CUSTOMERS table as shown below.

    +----+----------+-----+-----------+----------+
    | ID | NAME     | AGE | ADDRESS   | SALARY   |
    +----+----------+-----+-----------+----------+
    |  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
    |  2 | Khilan   |  25 | Delhi     |  1500.00 |
    |  3 | kaushik  |  23 | Kota      |  2000.00 |
    |  4 | Chaitali |  25 | Mumbai    |  6500.00 |
    |  5 | Hardik   |  27 | Bhopal    |  8500.00 |
    |  6 | Komal    |  22 | MP        |  4500.00 |
    |  7 | Muffy    |  24 | Indore    | 10000.00 |
    +----+----------+-----+-----------+----------+

Populate one table using another table
You can populate the data into a table through the select statement over another table; provided the other table has a set of fields, which are required to populate the first table.

Here is the syntax −

    INSERT INTO first_table_name [(column1, column2, ... columnN)] 
      SELECT column1, column2, ...columnN 
      FROM second_table_name
      [WHERE condition];

# SELECT

The SQL SELECT statement is used to fetch the data from a database table which returns this data in the form of a result table. These result tables are called result-sets.

Syntax
The basic syntax of the SELECT statement is as follows −

        SELECT column1, column2, columnN FROM table_name;
Here, column1, column2... are the fields of a table whose values you want to fetch. If you want to fetch all the fields available in the field, then you can use the following syntax.

    SELECT * FROM table_name;
    Example
    Consider the CUSTOMERS table having the following records −

    +----+----------+-----+-----------+----------+
    | ID | NAME     | AGE | ADDRESS   | SALARY   |
    +----+----------+-----+-----------+----------+
    |  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
    |  2 | Khilan   |  25 | Delhi     |  1500.00 |
    |  3 | kaushik  |  23 | Kota      |  2000.00 |
    |  4 | Chaitali |  25 | Mumbai    |  6500.00 |
    |  5 | Hardik   |  27 | Bhopal    |  8500.00 |
    |  6 | Komal    |  22 | MP        |  4500.00 |
    |  7 | Muffy    |  24 | Indore    | 10000.00 |
    +----+----------+-----+-----------+----------+

The following code is an example, which would fetch the ID, Name and Salary fields of the customers available in CUSTOMERS table.

    SQL> SELECT ID, NAME, SALARY FROM CUSTOMERS;
        This would produce the following result −

    +----+----------+----------+
    | ID | NAME     | SALARY   |
    +----+----------+----------+
    |  1 | Ramesh   |  2000.00 |
    |  2 | Khilan   |  1500.00 |
    |  3 | kaushik  |  2000.00 |
    |  4 | Chaitali |  6500.00 |
    |  5 | Hardik   |  8500.00 |
    |  6 | Komal    |  4500.00 |
    |  7 | Muffy    | 10000.00 |
    +----+----------+----------+

If you want to fetch all the fields of the CUSTOMERS table, then you should use the following query.

# Update

The SQL UPDATE Query is used to modify the existing records in a table. You can use the WHERE clause with the UPDATE query to update the selected rows, otherwise all the rows would be affected.

Syntax
The basic syntax of the UPDATE query with a WHERE clause is as follows −

    UPDATE table_name
    SET column1 = value1, column2 = value2...., columnN = valueN
    WHERE [condition];

You can combine N number of conditions using the AND or the OR operators.

Example
Consider the CUSTOMERS table having the following records −

    +----+----------+-----+-----------+----------+
    | ID | NAME     | AGE | ADDRESS   | SALARY   |
    +----+----------+-----+-----------+----------+
    |  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
    |  2 | Khilan   |  25 | Delhi     |  1500.00 |
    |  3 | kaushik  |  23 | Kota      |  2000.00 |
    |  4 | Chaitali |  25 | Mumbai    |  6500.00 |
    |  5 | Hardik   |  27 | Bhopal    |  8500.00 |
    |  6 | Komal    |  22 | MP        |  4500.00 |
    |  7 | Muffy    |  24 | Indore    | 10000.00 |
    +----+----------+-----+-----------+----------+

The following query will update the ADDRESS for a customer whose ID number is 6 in the table.

    SQL> UPDATE CUSTOMERS
    SET ADDRESS = 'Pune'
    WHERE ID = 6;

    Now, the CUSTOMERS table would have the following records −

    +----+----------+-----+-----------+----------+
    | ID | NAME     | AGE | ADDRESS   | SALARY   |
    +----+----------+-----+-----------+----------+
    |  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
    |  2 | Khilan   |  25 | Delhi     |  1500.00 |
    |  3 | kaushik  |  23 | Kota      |  2000.00 |
    |  4 | Chaitali |  25 | Mumbai    |  6500.00 |
    |  5 | Hardik   |  27 | Bhopal    |  8500.00 |
    |  6 | Komal    |  22 | Pune      |  4500.00 |
    |  7 | Muffy    |  24 | Indore    | 10000.00 |
    +----+----------+-----+-----------+----------+
        
# DELETE

The SQL DELETE Query is used to delete the existing records from a table.

You can use the WHERE clause with a DELETE query to delete the selected rows, otherwise all the records would be deleted.

Syntax
The basic syntax of the DELETE query with the WHERE clause is as follows −

    DELETE FROM table_name
    WHERE [condition];
You can combine N number of conditions using AND or OR operators.

Example
Consider the CUSTOMERS table having the following records −

    +----+----------+-----+-----------+----------+
    | ID | NAME     | AGE | ADDRESS   | SALARY   |
    +----+----------+-----+-----------+----------+
    |  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
    |  2 | Khilan   |  25 | Delhi     |  1500.00 |
    |  3 | kaushik  |  23 | Kota      |  2000.00 |
    |  4 | Chaitali |  25 | Mumbai    |  6500.00 |
    |  5 | Hardik   |  27 | Bhopal    |  8500.00 |
    |  6 | Komal    |  22 | MP        |  4500.00 |
    |  7 | Muffy    |  24 | Indore    | 10000.00 |
    +----+----------+-----+-----------+----------+
The following code has a query, which will DELETE a customer, whose ID is 6.

    SQL> DELETE FROM CUSTOMERS
    WHERE ID = 6;

Now, the CUSTOMERS table would have the following records.

    +----+----------+-----+-----------+----------+
    | ID | NAME     | AGE | ADDRESS   | SALARY   |
    +----+----------+-----+-----------+----------+
    |  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
    |  2 | Khilan   |  25 | Delhi     |  1500.00 |
    |  3 | kaushik  |  23 | Kota      |  2000.00 |
    |  4 | Chaitali |  25 | Mumbai    |  6500.00 |
    |  5 | Hardik   |  27 | Bhopal    |  8500.00 |
    |  7 | Muffy    |  24 | Indore    | 10000.00 |
    +----+----------+-----+-----------+----------+

If you want to DELETE all the records from the CUSTOMERS table, you do not need to use the WHERE clause and the DELETE query would be as follows −

        SQL> DELETE FROM CUSTOMERS;
Now, the CUSTOMERS table would not have any record.
