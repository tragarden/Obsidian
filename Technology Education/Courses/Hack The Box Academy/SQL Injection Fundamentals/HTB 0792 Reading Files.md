# Reading Files

Within the other modules in this course, you have seen methods for retrieving information from existing fields and columns within databases. What has yet to be covered is that these fields and columns can also be modified or generated via SQL injection. 

While reading data is the most common application of injections, escalating privileges via injection can be used to further exploit and modify these systems. Within MySQL, the user needs to obtain FILE privileges in order to import data to the table.

When enumerating in these cases, you will need to reveal user privilege data in order to determine if you can gain access to writing access on the back-end. You need to know which user you are when you are accessing the database. You do not necessarily need to be an admin to do this although as time progresses the modern security conventions DO require administrative access before changes can be executed. 

The following series of statements and their subsequent alternatives can be used to determine which user we are operating as:

>SELECT USER()
>SELECT CURRENT_USER()
>SELECT user FROM mysql.user

Here is the UNION injection variant:

>cn' UNION SELECT 1, user(), 3, 4-- -

An alternative UNION:

>Lcn' UNION SELECT 1, user, 3, 4 FROM mysql.user-- -

Any of these statements could be used to detect the name of the user account we have access to. In the case of this module, the username is 'root', which is great because it likely comes with high levels of privilege.

#### Privileges

Now that we have determined which user account we have access to, we can determine the existing privileges for the user. 

The following statement can be used to determine if we have superuser privileges:

>SELECT super_priv FROM mysql.user

This can be further modified to carry a payload:

>cn' UNION SELECT 1, super_priv, 3, 4 FROM mysql.user-- -

If there are an overwhelming amount of users within the database, the following statement can be injected using WHERE user='root' to only show the privileges of the root user:

>cn' UNION SELECT 1, super_priv, 3, 4 FROM mysql.user WHERE user="root"-- -

In the case of this module, the query will return the value Y which indicates that yes, we have superuser privileges. 

With the following statement, we can look further into the privileges that we have directly from the schema:

>cn' UNION SELECT 1, grantee, privilege_type, 4 FROM information_schema.user_privileges-- -

Next, we can continue to add to this statement using the WH