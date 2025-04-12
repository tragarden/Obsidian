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

- If a directory is designated within this file, you can only read from