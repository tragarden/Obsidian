# Statements

A Statement is a term used in commands to execute something within the database.

- INSERT is used to add records to a table.

>INSERT INTO tablename VALUES (colval1, colval2, colval3...);

This command would require you to input all values for all columns within the table.

The following command would add new logins to the logins table with appropriate values.

>INSERT INTO logins VALUES(1, 'admin', 'password', 'dateandtime');

You could alternatively specify column names and input the values selectively:

>INSERT INTO tablename(col2, col3, ...) VALUES (colval2, colval3, ...);

Below is an example command that would input multiple records:

>INSERT INTO(username, password) VALUES ('john')