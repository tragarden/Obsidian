# HTB Meow

#Enumeration is the initial focus of any penetration test. We will want to **look for obvious points of entry**, and looking for a vulnerable #port with #nmap scanning is a good strategy. This type of **enumeration paired with research via internet searches is a major part of testing**. It would benefit your to **prioritize thoroughness over quickness** in all of our testing.

### Enumeration

*Network Mapper* ( #nmap) is a very common tool that all pentesters use. This tool is capable of scanning every port on a target device to determine any services running on any of the ports specified.

#### Ping

To see if we have a connection to the host, we can #ping the target with the following  command:

>ping 10.10.10.10

This will likely **return statistics telling us the state of the connection**. If there is a connection established, we then know that we can begin an nmap scan of the target. We can end our ping command by pressing **Ctrl + C**. 

#### nmap

We can **use the #nmap command with the -sV flag** to retrieve a description and **version number** of any services running on the target device. We would use the following command:

>sudo nmap -sV 10.10.10.10

#### Telnet

This command may take a moment to render as it is **scanning 1000+ ports and retrieving information for any open ports**. In the case of this module, we can see that **port 23/tcp is open and running the #Telnet service**. Telnet is an older method of remotely accessing a host. With a bit of research we can **discover the default credentials for Telnet** and attempt to log in.

**Connect to a #Telnet port** on the target device with the following command:

>telnet 10.10.10.10

If we are able to connect to Telnet, it will prompt us to **enter a user name followed by a password**. Our first attempt should be to supply the known default user account names paired with a blank password. 

#### Default Credentials

With some research, or via guessing, we can **submit the following user names** hoping that this connection was configured poorly. 

The default user names we should try are:

- admin
- administrator
- root

After some attempts, we will **find that 'root' is the default username and no password** was set. We should now have access to the host via Telnet.

#### Host Access

Once we have connected via Telnet, we can then **execute Linux commands like ls and cd** to navigate around the host. 

If we **use the ls command in the home directory we can see a file flag.txt**. This is our goal for the machine and we can **display the contents of this file** with the following command:

>cat flag.txt

This will reveal the hash value to complete this machine.







### Related:

- [0728 HTB Web Enumeration](0728%20HTB%20Web%20Enumeration.md)
- [0764 HTB Common Web Vulnerabilities](0764%20HTB%20Common%20Web%20Vulnerabilities.md)