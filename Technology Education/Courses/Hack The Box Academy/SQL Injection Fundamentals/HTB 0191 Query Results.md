# Query Results

There are statements and commands that can be used to modify the way that query results are presented to us.

#### ORDER BY 

ORDER BY is used to sort query results by specifying the column you want to sort by. An example of it's use is below:

>SELECT \* FROM logins ORDER BY password;

This command would select all results from the logins table and then order them by password. The default is to display these results in ascending order, although this can be indicated by using the ASC and DESC keywords, shown below:

>SELECT \* FROM logins ORDER BY password DESC;

You can also sort by multiple columns, using a second sort parameter for duplicate values:

>SELECT \* FROM logins ORDER BY password DESC, id ASC;

#### LIMIT

LIMIT is used to reduce or limit the amount of results that will be returned. If we only wanted two results to be displayed in the output, we could use the following command:

>SELECT \* FROM logins LIMIT 2;

You can also indicate an offset to select specified results from the middle of a table:

>SELECT \* FROM logins LIMIT 1, 2;

#### WHERE

WHERE can be used to apply conditions to a SELECT statement. Below is an example:

>SELECT \* FROM tablename WHERE \<condition>;

This would return all results that satisfy the indicated condition, unspecified in the example.

Here is a more specific example:

>SELECT \* FROM logins WHERE id > 1;

This would select all records that have an id value greater than 1, skipping the first entry.

Another example:

>SELECT \* FROM logins where username = 'admin';

This would select all records related to the username 'admin'.

#### LIKE

LIKE is used to select records that satisfy the indicated pattern. 

The next example would retrieve all records containing usernames starting with 'admin':

>SELECT \* FROM logins WHERE username LIKE 'admin%';

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to Query Results](https://academy.hackthebox.com/module/33/section/191 "Intro to SQL Query Results")