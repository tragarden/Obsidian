# Union Injection

If we want perform an easy test to determine if a submission form is vulnerable to SQL injection, you can simply enter a single apostrophe ( ' ) into the submission field. If it returns an error, this may mean that the page is vulnerable to SQL injections.

Once you have determined that the page could be susceptible to injection, you would then need to determine the number of columns that are selected by the server. This can be accomplished by using either of the following methods:

- ORDER BY
- UNION

#### ORDER BY 

You can use ORDER BY to sort results by an indicated column until an error is displayed indicating that the indicated column does not exist. You can count the amount of columns that are accepted before the error occurs to determine how many there are in the given table.

If you were to ORDER BY 1 and then sort by the first column, this would indicate that there is at least one column in the table. Then you would iterate through ORDER BY 2, ORDER BY 3, etc. until an error is displayed in the output or no output is displayed at all. 

This stage means that we have reached the end of the table in regard to columns. For example, if ORDER BY 9 is the first query to return an error or no output, this would mean the table has 8 viable columns.

When performing an injection like this, you would use a submission similar to the one below:

>' ORDER BY 1-- -

If this is successful, you would change the integer to 2 and repeat these iterations until you recieved an error or no output.

Note that as you change the integer in the ORDER BY injection, the output will change to reflect that integer you are ordering by. 

#### UNION

Alternatively you could try UNION injections with different numbers of columns until you return output successfully. Note that this is the opposite of the ORDER BY strategy - now we will return errors on all submissions until we submit the correct number of columns.

The statement below is an example of how you would use the UNION clause to achieve this:

>cn' UNION SELECT 1,2,3-- -

This would return an error, and we know from the ORDER BY statements prior that this table has four columns, so this makes sense.

If we changed the statement to the following, we would return output successfully.

Once you have determined the correct amount of columns in the table, you can begin to craft a payload.

#### Location

When performing these tests, the queries we are submitting may indicate there are multiple columns that the output is not displaying. In order to view the output from our injected query, we would need it to inject it into one of the columns that is displayed in the output.

A method for doing this is to inject the numbers 1, 2, 3, 4 into their respective columns - the numbers that are output indicate the column numbers that are being returned. 

In the case of the example, you can see that columns 2, 3, and 4 are being printed.  This means that anything injected at the beginning, aka column 1, would not be printed to output. The reason that numbers are used instead of NULL is so that we can identify the columns. 

The \@@version query can be used as a test to determine what version of the database is being used:

>cn' UNION select 1, \@@version, 3, 4-- -

This would successfully inject and display the database version currently being used.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Union Injection](https://academy.hackthebox.com/module/33/section/216 "HTB Union Injection")