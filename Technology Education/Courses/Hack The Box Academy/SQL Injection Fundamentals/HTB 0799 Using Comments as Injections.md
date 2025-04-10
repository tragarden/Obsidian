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

