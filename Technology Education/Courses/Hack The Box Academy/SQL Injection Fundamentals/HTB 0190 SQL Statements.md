# Statements

A Statement is a term used in commands to execute something within the database.

#### INSERT

INSERT is used to add records to a table.

>INSERT INTO tablename VALUES (colval1, colval2, colval3...);

This command would require you to input all values for all columns within the table.

The following command would add new logins to the logins table with appropriate values.

>INSERT INTO logins VALUES(1, 'admin', 'password', 'dateandtime');

You could alternatively specify column names and input the values selectively:

>INSERT INTO tablename(col2, col3, ...) VALUES (colval2, colval3, ...);

Below is an example command that would input multiple records:

>INSERT INTO(username, password) VALUES ('john', 'john123!'), ('tom', 'tom123!');

#### SELECT

SELECT is used to indicate which columns and rows you want to retrieve data from.

The following command would return all values from the entire indicated table:

>SELECT \* FROM tablename;

#### FROM

FROM allows us to denote the table we are working with.

If you wanted to make your SELECT statement more specific, you could try the following command:

>SELECT col1, col2 FROM tablename;

For a more specific case, consider the following:

>SELECT username, password FROM logins;

#### DROP

DROP is used to remove tables and databases from the server. And example of it's use is below:

>DROP TABLE logins;

This would have successfully removed the table unless the table currently has dependencies from other tables.

#### ALTER

ALTER is used to change the name of tables and fields, and to add or delete columns from an existing table. Below are some use examples:

>ALTER TABLE logins ADD newColumn INT;

To rename a column, use the RENAME COLUMN statement:

>ALTER TABLE logins ADD newColumn INT;

We can modify a column using the MODIFY statement in the following way:

>ALTER TABLE logins MODIFY newerColumn DATE;

We can remove a column using the DROP statement:

>ALTER TABLE logins DROP newerColumn;

If we wanted to conditionally update individual records within the table, we would use the UPDATE statement:

>UPDATE tablename SET col1=newval1, col2=newval2, .... WHERE \<condition>;

The below statement is a way you could force password updates on all accounts besides the admin account:

>UPDATE logins SET password = 'change_password' WHERE id > 1;

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to SQL Statements](https://academy.hackthebox.com/module/33/section/190 "Intro to SQL Statements")