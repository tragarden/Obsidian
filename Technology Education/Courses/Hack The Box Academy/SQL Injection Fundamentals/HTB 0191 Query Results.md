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

