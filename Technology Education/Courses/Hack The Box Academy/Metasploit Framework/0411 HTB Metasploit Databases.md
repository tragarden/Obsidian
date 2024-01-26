# Metasploit Databases

Metasploit uses a #database to track the results of enumeration and access, as manipulating many devices across the breadth of a network can be time consuming and complicated. It will log search results, entry points, detected issues, discovered credentials, and many more metrics that would be difficult to monitor manually. 

#Msfconsole uses the #PostgreSQL databases to log scan results that are easily imported and exported to integrated third-party tools. These can even be integrated with modules to fill parameter details automatically. 

### Database Setup

First we will see if a PostgreSQL database server is currently running with the following command:

>sudo service postgreSQL status

##### Starting PostgreSQL

We will begin by 

>sudo systemctl start postgresql

##### Initiate a Database

We will then need to initialize our database with the following command:

>sudo msfdb init

If you encounter an error, this is likely due to Metasploit being out of date. Update it with the following command:

>sudo apt update

Once you think the database is initialized, verify this with the following command:

>sudo msfdb status

### Connect to Initiated Database

Now that the database is up and running, we can execute msfconsole and connect to it with the following command:

>sudo msfdb run
>run

#### Reinitiate the Database

If you cannot change the MSF password after the database is configured, use the following commands:

>msfdb reinit
>cp /usr/share/metasploit-framework/config/database.yml \~/.msf4/
>sudo service postgresql restart
>msfconsole -q

For more information about the database interface, run the following command:

>help database

### Using the Database

The database has many features including importing and exporting mechanisms, as well as data back up. There are tools like #nmap, credential storage, service management, and workspaces.

#### Workspaces

In the context of Metasploit databases, workspaces function like folders. Each workspace can hold different scan results, host information, groups of hosts, extracted data, #IP addresses, and #subnet, #network, and #domain information.

You can view the list of current workspaces by executing the 'workspace' command. Additionally you can use the -a or -d switches to add or delete workspaces if you supply the designated name of the workspace after the switch. The default workspace is called 'default' and will be the only available workspace on a new database. 

View the list of available workspaces with the following command:

>workspace

Add a new workspace with the following command:

>workspace -a myNewWorkspace

Similarly you can delete this workspace with the following command:

>workspace -d myNewWorkspace

Select the workspace with the following command:

>workspace myNewWorkspace

If you need more information about the switches related to workspace commands, use the -h switch:

>workspace -h

#### Importing Scans 

We can import a saved #nmap scan with the db_import command. If we have  the results of a scan saved as a \*.nmap file, we can import it to the database.

In the case of the file target.nmap, we would import this into our database using the following command:

>db_import target.xml

This will import the scan results and parse them into our database.

#### Nmap within MSFconsole

You can use the db_nmap command to perform an nmap scan within the MSFconsole interface as follows:

>db_nmap -sV -sS 10.10.10.8
>hosts
>services

The commands following db_nmap will present the list of scanned hosts and services respectively. 

#### Data Backup

We can use the db_export command to backup our database to the location of our choosing. 

For more information about the db_export command, use the -h switch:

>db_export -h 

To save the database to our working directory, use the following command:

>db_export -f xml backup.xml

This information can now be imported back into msfconsole as needed.

#### Hosts

The hosts command will automatically populate host IP addresses, hostnames, and related information to a database table in our output. This feature can integrate with scanner plugins that provide OS detection, #Nessus, #NexPose, and #Nmap. Additionally you can manually input host data using the custom host feature. Modification of the table format and structure as well as including comments is possible as well.

For more information about the hosts command, use the -h switch:

>hosts -h

#### Services

The services command works similarly to the hosts command. It offers descriptive information about the services on hosts and offers many modifications and integrations.

For more information about the services command, use the -h switch:

>services -h

#### Credentials

The creds command outputs credentials discovered during the enumeration process. Credentials can be added manually with port specifications as well.

Use the -h switch to learn more about the creds command:

>creds -h

#### Loot

The loot command works with the support of the creds command. It shows the list of owned services and users via hash dumping from system types, hashes, passwd, shadow, and other sources.

Use the -h switch to learn more about the loot command:

>loot -h
