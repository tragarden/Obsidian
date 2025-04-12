# Writing Files

While it is possible to write to files via injection, modern DBMSes are much more restrictive in which users are able to modify file contents due to the fact that attackers could potentially write a web shell via remote server to execute code and compromise the integrity of the server.

In order to gain access to file writing on a database server, you will need to meet the following conditions:

- The user must have FILE privileges
- secure_file_priv must be disabled globally
- Write access to the indicated location on the back-end

In the case of this module, you know that you already have FILE privileges. Now you will need to determine if the database itself has the privilege.

#### secure_file_priv

The secure_file_priv variable determines where files can be read and written from. 

- If the file has an empty value, you know you have the ability to read any file within the file system.

- If a directory is designated within this file, you can only read from this specified file.

- If the value is NULL, this means that you cannot read or write any file.

MariaDB sets the variable to empty by default, allowing you to modify files if you have FILE privileges.

MySQL uses /var/lib/mysql-files as the default folder. This means that by default, you cannot read or write to files anywhere in the system. 

You can user the following query to find the value of the variable in MySQL:

>SHOW VARIABLES LIKE 'secure_file_priv';

You would need to implement an injection to achieve this in our case. You will need to use the UNION and SELECT statements to achieve this. All the variables you need are stored within INFORMATION_SCHEMA database. The global variables are stored in a table named global_variables which has two columns, variable_name and variable_value.

These two columns must be selected from the INFORMATION_SCHEMA database. It should be noted that there are hundreds of global variables in the default MySQL configurations and you do NOT want to retrieve all of them. The results can be filtered so that only the secure_file_priv variable is shown via the WHERE clause.

Here is the SQL query that would achieve this:

>SELECT variable_name, variable_value FROM information_schema.global_variables WHERE variable_name="secure_file_priv"

Below is the UNION injection that you would need to use. It delivers a payload and adds columns 1 and 4 containing junk entries:

>cn' UNION SELECT 1, variable_name, variable_value, 4 FROM information_schema.global_variables WHERE variable_name="secure_file_priv"-- -

In our example, this shows that the file value is empty, meaning that files can be read and written to with FILE permissions:

### SELECT INTO OUTFILE

The SELECT INTO OUTFILE statement is used to write data from SELECT queries into files. This is often used to export output into the file we have designated.

Below is an example that would save the output from the 'users' table into the /tmp/credentials file:

>SELECT \* FROM users INTO OUTFILE '/tmp/credentials';

Now you can go back to the back-end server and cat the file to view it's contents:

>cat /tmp/credentials

This will reveal the hash values for the passwords of the admin and newuser accounts.

You can directly SELECT strings into these files which allow us to write arbitrary file content to the back-end server.

You can use the following query to test this:

>SELECT 'this is a test' INTO OUTFILE '/tmp/test.txt';

Now if you cat the file a second time, you will see the string you submitted:

>cat /tmp/test.txt

Then you can assess the read and write privileges and other information about this file with the following:

>ls -la /tmp/test.txt

This will reveal that the file creation was successful and that it is owned by the MySQL user you are operating under.

### Writing with Injections

You can use the following query to write a text file to the webroot to verify permissions:

>SELECT 'file written successfully!' INTO OUTFILE '/var/www/html/proof.txt'

If you wanted to write to the web shell, you would need to know the base web directory for the web server - also known as the web root. You can find this by using load_file to determine the server configuration. 

In the case of Apache servers, this is stored in /etc/apache2/apache2.conf.

For Nginx, this is located in /etc/nginx/nginx.conf.

IIS configuration is located in %WinDir%\System32\Inetsrv\Config\ApplicationHost.config.

If none of these are working, you can do an online search to seek out additional configuration locations.

Fuzzing can be used to scan locations and attempt file writing to different potential web roots by using Linux and Windows wordlists.

If all else fails, you can attempt to use server error output to try and discover the base web directory.