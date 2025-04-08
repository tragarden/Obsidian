# MySQL

Structured Query Language (SQL) is a common language that varies in syntax depending on the RDBMS being used, but all of these variants still follow the ISO standard. With SQL commands, you can perform the following tasks in a database:

- Retrieve data
- Update entries
- Delete entries
- Create new tables
- Create new databases
- Add and remove users
- Assign user permissions

### Command Line

The command line is used to input commands that cause actions within the database. Consider the following command input:

>mysql -u root -p

- -u indicates the username
- -p indicates the password
- root logs the user in as the root user granting execution rights for all commands
- privileges can be used via the SHOW GRANTS command

In this case, the -p flag should remain blank so that you will be prompted for a more secure method for password input. When you include the password in the command submission there is a security vulnerability that would store this password within the bash_history file and terminal history. In the case where you may want to submit the password with the command, make sure there is no space between the -p and the submitted password.

#### Host Designation

When a host is not specified, the default server will be the localhost server.

Consider the following command:

>mysql -u root -h docker.hackthebox.eu -P 3306 -p

- -h indicates the host name
- -P indicates the port to be used

#### Database Designation

Once the mysql utility has been accessed we can use queries to interact with the DBMS.

Consider the following command for creating a database:

>	CREATE DATABASE users;

This command would create a database with the name 'users.' Note that MySQL requires queries to be terminated with a semi-colon.

The following command would show which databases are available through the interface and then chooses the 'users' database:

>SHOW DATABASES;
>USE users;

Note that while SQL syntax is not case sensitive in regard to commands; it is case-sensitive when referring to the name of the database 'users'. 

#### Tables

A database Tables consists of horizontal rows and vertical columns. 

A Cell is where the rows and columns intersect.

Data Types indicate the type of values that may be input into a column. Numbers, strings, data, time, and Boolean are the standard data types.

Consider the following command that creates a table named 'logins':

>CREATE TABLE logins (
>	id INT,
>	username VARCHAR(100),
>	password VARCHAR(100),
>	date_of_joining DATETIME
>);

- Creates a table with the name 'logins'
- assigns three columns: username, password, and date_of_joining
- assigns data types for each column
- assigns properties to these columns

The following command would show all successfully generated tables.

>SHOW TABLES

The DESCRIBE keyword can be used to show a list of all tables with their data type:

>DESCRIBE logins;

#### Properties

Properties can be set for each table and column. Some commonly used properties include:

- AUTO_INCREMENT - automatically increments an INT value by 1.
- NOT NULL - forces a column to have no empty cells.
- UNIQUE - forces all cell entries to remain unique.
- DEFAULT - indicates a default value for otherwise null cells.
- Now() - inputs the current time and date, sometimes useful with DEFAULT.
- PRIMARY KEY - forces unique identification for each record in the table.

An example of a thorough command for creating a table with properties is below:

>CREATE TABLE logins (
>	id INT NOT NULL AUTO_INCREMENT,
>	username VARCHAR(100) UNIQUE NOT NULL,
>	password VARCHAR(100) NOT NULL,
>	date_of_joining DATETIME DEFAULT NOW()
>	PRIMARY KEY (id)
>);

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to SQL](https://academy.hackthebox.com/module/33/section/183 "Intro to SQL")