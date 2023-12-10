# Service Scanning

A good first step for penetration testers is to identify the operating system used by the target, any #service that is running on that #OS, and the #IP address if possible. When we identify services that are running on the machine, we are able to investigate them and determine if there are vulnerabilities, misconfigurations, or lack of updates that would allow us to exploit these services for our purposes.

We should also consider any #port being used to facilitate a service. The first 1,023 ports are dedicated to specific common services that most machines will use. Anything beyond these static ports are known as wildcard ports and can be used for any service that is not provided by default.

### Nmap

#Nmap is a port scanning utility that identifies any active ports and can be configured to target specific items. This is a basic scanning tool that all penetration testers are familiar with. By default, nmap will scan the first 1,000 ports over a #TCP connection.

The following command would perform the default nmap scan on the IP provided.

> nmap 10.10.10.10

This would identify any open or active ports, along with the latency of the host and the service each port is providing for. The results depict the port and connection type, the state of the port, and what service is active on that port.

#### Syntax

The syntax for nmap is as follows:

> nmap --script \<script name> -p\<port> \<host>

#### Flags

Some common flags used for more granular use of nmap include:

- -sC specifies the use of scripts to obtain more detailed information.
- -sV performs a scan of the versions on the target.
- -p- will perform a scan on all 65,535 ports available on the target.

Here is an example of these flags in use:

> nmap -sV -sC -p- 10.10.10.10

This command will provide a MUCH more thorough and detailed report of the available ports and related information about them. This means that the scan will subsequently take much longer to complete. The data reveals tells us about the version of the operating system, which can yield potential vulnerabilities and flaws in that version for our exploitation needs.
Please note that version is not always a sure way to discover exploits, as older versions can run newer versions within themselves.

#### Scripts

The command -sC is useful as it runs a default list of common useful scripts, but sometimes we only want to run a specific script or one that is not included within the -sC command.

The following command would initiate a script that audits for the Citrix NetScaler vulnerability, CVE-2019-19781.

> locate scripts/citrix

### Attacking Services

#### Banner Grabbing

A #Banner is what a #service uses to identify itself after establishing a connection.

We can use the nmap syntax below for banner grabbing purposes:

> nmap -sV --script=banner \<target>

While this can be useful if we don't have netcat installed, netcat is typically a preferred method for banner grabbing. The command for banner grabbing via netcat would look like the following:

> nc -nv 10.10.10.10 21

This will reveal the version the server is running. We can automate this using nmap's scripting engine:

> nmap -sV --script=banner -p21 10.10.10.0/24

#### FTP

File Transfer Protocol ( #FTP) is a standard in networking that should be understood and evaluated by pentesters. 

We can use the following nmap command to enumerate FTP related results:

> nmap -sC -sV -p21 10.10.10.10

In the example, this reveals the version of FTP being used and that anonymous authentication is enabled, which can grant us anonymous access to the FTP #CLI via the following:

> ftp -p 10.10.10.10

While in the FTP CLI, we can use common Linux commands such as cd and ls, as well as commands for downloading files and returning their contents. We can retrieve the login.txt file information to determine user credentials for privilege escalation. 

We can return the contents of the file login.txt with the following command:

> cat login.txt


#### SMB

Server Message Block ( #SMB) is a #Windows #protocol that allows for vertical and horizontal movement throughout the system. This can be used to reveal sensitive information such as user credentials and version numbers so we can research exploits. Make sure to enumerate the entire attack surface here as it is vast and often offers a lot of opportunities for infiltration. 

We can use the following script smb-os-discovery.nse in our command to enumerate this vital SMB information:

> nmap --script smb-os-discovery.nse -p445 10.10.10.10


##### Shares

#SMB can be used to share folders and resources to be accessed remotely. We can use the tool #smbclient to enumerate SMB shares on a given system.

We can supply the following command to enumerate shares on a remote host. In the example, the -L flag specifies a list format for all available shares, and the -N flag is used to suppress the pending password prompt.

> smbclient -N -L \\\\\\\\10.10.10.10

This will reveal non-default share users, which means we will be able to log onto the guest user account:

> smbclient \\\\\\\\10.10.10.10\\\\users

The guest account is limited in what commands we can use - in fact, we cant even use the ' ls ' command under this account.

We will instead try logging in with the account ' bob ', since we discovered the credentials during smbclient enumeration:

> smbclient -U bob \\\\\\\\10.10.10.10\\\\users

Submit the password (bob:Welcome1) to gain access to the bob user account.

Now we can use ls to see files on the machine, which include a desirable target: passwords.txt.

We can download this file with the following command:

> get passwords.txt


#### SNMP

Simple Network Management Protocol ( #SNMP) can be used to discover statistic and details related to a #router or other network device. This protocol uses public and private community strings which can be problematic if they are set to a default configuration. Community strings are stored as plaintext, which means they are susceptible to discovery and an attacker can gain access to credentials.

We can use the following command to begin enumerating information related to SNMP:

> snmpwalk -v 2c -c public 10.10.10.10 1.3.6.1.2.1.1.5.0

> snmpwalk -v 2c -c private 10.10.10.10

This will tell us the public and private SNMP information that is available.

We can use the #onesixtyone tool to brute force the community strings using a dictionary file of relevant community strings, which is available in the GitHub repository for onesixtyone.

> onesixtyone -c dict.txt 10.10.10.10

