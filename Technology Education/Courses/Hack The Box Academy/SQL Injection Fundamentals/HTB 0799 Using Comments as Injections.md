# Using Comments

We can use comments within our injections to bypass or escape certain parts of the SQL code on the backend. Comments in SQL are used to either document information related to submitted queries or or ignore certain segments within the query.

There are three ways of commenting in MySQL:

-  \-- (two hyphens)
- \# 
- \/\*\*\/ (single line comment that is rarely used within MySQL)

An example of how someone would use a comment to document their query:

>SELECT username FROM logins; \-- Selects usernames from the logins table

This comment simply describes what the SQL statement does for notation purposes.

Note that in order to use the \-- method for commenting, you MUST include a space after the two hyphens. Sometimes URL encoding will display the comment with no space as \--+, where the ( +) is representative of a space. Good practice is to include a space and an additional hyphen after the commenting hyphens, like \-- -.

When you are using the \# symbol, consider that within a web browser this is considered a tag and will not be passed to the backend as part of the URL. You will need to use the URL encoded representation for \# which is %23.

The following code will inject 'admin '-- ' into the SQL statement:

>SELECT \* FROM logins WHERE username='admin'-- ' AND password = 'something';

This would resultantly make the username admin and then comment out the rest of the statement. This will successfully grant us access to the example admin page.

#### Order of Operations

SQL allows you to use parenthesis to indicate that you want to prioritize one condition over others, making them higher in precedence.

Remember that the statement being used to assess credential submissions is shown below, with out previously successful submission of the username ' admin'-- '.

>Executing Query: SELECT \* FROM logins WHERE username='admin'-- ' AND password='a';

Sometimes a condition is placed that prevents the admin account name from being submission. In this case the user ID number is used to ensure that the account number 1 is unable to be submitted. We will attempt to bypass this.

Here is the example of the query with the condition barring the admin account ID number:

>Executing Query: SELECT \* FROM logins WHERE (username='admin' AND id>1) AND password='password';

This statement means that even if you knew the correct credentials for the admin account, you would be prevented from accessing it anyway. Other accounts will experience no problems authenticating when supplied with the correct credentials.

We will now need to comment out the part of the query that prevents ID number 1 from being accessed.

In the case where we try to input the username ' admin' -- ' we are unable to successfully submit our query due to syntax errors.

Alternatively we are able to use the username admin')-- to comment out the rest of of the query:

>Executing Query: SELECT \* FROM logins WHERE (username='admin')-- ' AND id>1) AND password='password';

This effectively make the submitted query:

>Executing Query: SELECT \* FROM logins WHERE (username='admin')

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Using Comments for Injection](https://academy.hackthebox.com/module/33/section/799 "HTB Using Comments for Injection")