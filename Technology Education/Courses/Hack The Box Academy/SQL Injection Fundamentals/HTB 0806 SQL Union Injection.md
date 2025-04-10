# Union Clause

The SQL Union Clause is used to include output from multiple statements. This allows you to submit a query with a SELECT statement that will retrieve data from various tables and databases withing the DBMS.

Consider the following two statements that return all results from the ports and ships tables:

>SELECT \* FROM ports;

>SELECT \* FROM ships;

We can combine these two statements with the union clause to produce their combined output:

>SELECT \* FROM ports UNION SELECT \* FROM ships;

This will combine all entries from the ports and ships tables into a single output.

We can use the UNION clause to return rows from another table. Consider the following query that we will soon modify to meet our needs:

>SELECT \* FROM products WHERE product_id = 'user_input'

If we modify this statement using the union clause:

>SELECT \* FROM products WHERE product_id = '1' UNION SELECT username, password FROM passwords-- '

This exploit would fill the two columns (if there are at least two) in the products table with entries from the username and password tables.

#### Uneven Columns

Often there will be times that the original query output will not have the correct amount of columns for us to import the other tables into. If there was only one column in the original query, we could use arbitrary data for the original query to match the amount of needed columns for the queries the UNION clause is returning.

You can submit any string as arbitrary input for the original query columns. We could UNION the original query with the string 'corncob', creating the following statement:

>SELECT 'corncob' FROM passwords

This would always return 'corncob', and if you used integers instead of strings it would yield the same effect. You need to match data types when choosing the type of arbitrary data to commit.

In the example we are working through, the products table has two columns, which means we would need a UNION that also has two columns. Below is a statement that would achieve this:

>SELECT \* FROM products WHERE product_id = '1' UNION SELECT username, 2 FROM passwords

If the original query has more columns than the UNION'ed part, we need to add columns to the original:

>UNION SELECT username, 2, 3, 4 FROM passwords-- '

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB SQL Union Injections](https://academy.hackthebox.com/module/33/section/806 "HTB SQL Union Injections")