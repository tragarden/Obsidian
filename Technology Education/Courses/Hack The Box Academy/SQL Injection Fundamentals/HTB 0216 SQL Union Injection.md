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

If this is successful, you would change the integer to 2 and repeat this process 