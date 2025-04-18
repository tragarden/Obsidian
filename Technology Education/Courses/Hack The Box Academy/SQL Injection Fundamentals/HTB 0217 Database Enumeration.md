# Database Enumeration

Enumeration is when you gather data about a target. In the case of this course, this is specifically related to acquiring information about the database you are looking to inject SQL into.

### Fingerprinting

Fingerprinting in this context refers to figuring out which type of DBMS you will be interacting with so that you know which type of queries to inject into it.

Methods for determining the DBMS are various. If you can determine via HTTP interactions whether the webserver is Nginx or Apache, you can then assume that the server is running on a Linux machine which makes it likely they are using MySQL. If the webserver is running IIS, this means it is likely a Microsoft machine also running MySQL.

If the fingerprinting process suggests that they are using MySQL, you can then begin to submit queries to determine that this is true.

| Payload          | Use Cases                            | Expected Output                         | Incorrect Output     |
| ---------------- | ------------------------------------ | --------------------------------------- | -------------------- |
| SELECT @@version | When there is full query output      | MySQL Version                           | MSSQL Version        |
| SELECT POW(1,1)  | Where there is only numerical output | 1                                       | Error                |
| SELECT SLEEP(5)  | Blind or No output                   | 5 second delay before output returns 0. | No delay of response |

### INFORMATION_SCHEMA

In order to use the UNION clause to retrieve data from tables, you will need to have the following information before crafting your SELECT statement:

- List of Databases
	- List of Tables for all databases
		- List of Columns for all tables

The INFORMATION_SCHEMA database is used to hold metadata about all tables and columns within the designated database. This is a unique database that does not allow you to call it's tables using SELECT statements. 

The dot ( . ) operator is used to reference tables from other databases. An example use case for the dot operator is below:

>SELECT \* FROM my_database.users;

### SCHEMATA

SCHEMATA is a table within INFORMATION_SCHEMA that holds information related to all databases on the server. You can use this to get the names of databases so they may be queried. There is a SCHEMA_NAME column that will hold all the names of active databases. 

Consider the following statement used against a local database:

>SELECT SCHEMA_NAME FROM INFORMATION_SCHEMA.SCHEMATA;

This would display all the databases including the 3 default databases named mysql, information_schema, and performance_schema. Occasionally you will see a fourth default database named 'sys'.

Now we will perform the same operation using a UNION injection:

>cn' UNION select 1, schema_name, 3, 4, FROM INFORMATION_SCHEMA.SCHEMATA-- -

In the example, the same default databases are displayed with the locally created databases named 'ilfreight' and 'dev', just as the previous example - only this time we retrieved this information via injection.

Now you can find the database that is currently in use with the following query that utilizes the SELECT database() query:

>cn' UNION select 1, database(), 2, 3-- -

### TABLES

You can get a list of tables from the database named 'dev' by using a select statement. When you want to find all of the tables within a specific database, you can use a table named TABLES in the INFORMATION_SCHEMA database to enumerate them. This table holds metadata about all tables within the database.

There are columns named TABLE_SCHEMA and TABLE_NAME that tell you the names of all tables and which databases they belong to. 

Here is a statement that you can use to find the tables:

>UNION SELECT 1, TABLE_NAME, TABLE_SCHEMA, 4 FROM INFORMATION_SCHEMA.TABLES WHERE table_schema='dev'-- -

This will reveal four tables within the database named dev - credentials, framework, pages, and posts.

### COLUMNS

The COLUMNS table holds information about every column within all databases.

The following statement can be used to find all the column names within the credentials table:

>cn' UNION select 1,COLUMN_NAME,TABLE_NAME,TABLE_SCHEMA from INFORMATION_SCHEMA.COLUMNS where table_name='credentials'-- -

This will reveal the columns username and password. This information can be used to retrieve further information.

### DATA

Now that we have identified the columns within the credentials column, we can use the UNION clause to retrieve the data from these columns:

>cn' UNION SELECT 1, username, password, 4 FROM dev.credentials- --

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Database Enumeration](https://academy.hackthebox.com/module/33/section/217 "HTB Database Enumeration")