# Common Terms

### Shell

A #Shell is a #comand-line interface that takes user input from a keyboard and submits typed commands to the operating system. Before the advent of the Graphical User Interface ( #GUI), #CLI was the only way to interact with a computer. Examples of shells include #Linux terminal, Linux Bourne Again Shell ( #BASH), #Windows command-line ( #cmd), and Windows #PowerShell.

Bourne Again Shell ( #BASH) is a common method of interacting with an #OS and is derived from the #sh shell from #Unix. Shells similar to BASH include zsh, tcsh, ksh, and Fish Shell.

"Getting a shell" refers to an attacker accessing a compromised shell where they are able to execute commands on someone else's machine.

### Shell Connection Types

Reverse Shell uses a listener on the attack box to initiate and maintain a connection.

Bind Shell binds to a port on the target host until a connection to the attack box is established.

Web Shell is established through a browser and is limited in functionality. 

### Ports

A #port is a virtual point of connection to a network that can be opened or closed. They are based on software installed on the host device. Some ports are associated with specific purposes, processes, or data types. 

Ports fall under two categories: TCP connections and UDP connections. Both TCP and UDP are issued a mind-blowing 65,535 total ports. Some commonly associated ports include:
- 20/21 #FTP 
- 22 #SSH 
- 23 #Telnet 
- 25 #SMTP 
- 80 #HTTP 
- 88 #Kerberos
- 161 #SNMP 
- 389 #LDAP 
- 443 #HTTPS ( #SSL / #TLS)
- 445 #SMB 
- 3389 #RDP 

# OWASP Top 10

The #OWASP Top 10 is a list of the priorities a pentester should be considering when evaluating network security. This list includes:

1. Broken Access Control - an attacker escalates their privileges to access other users' accounts or resources they are not supposed to be able to access.
2. Cryptographic Failure - sensitive data is revealed through flaws in cryptography.
3. Injection - user submissions are not properly filtered and sanitized appropriately and malicious code is able to be submitted through input portals on a site.
4. Insecure Design - security flaws in the design of an application.
5. Security Misconfiguration - hardening procedures have been improperly implemented or absent altogether.
6. Vulnerable and Outdated Components - network components that are out of date or unsupported.
7. Identification and Authentication Failure - exploitation of user identities or session management features.
8. Software and Data Integrity Failures - code and  infrastructure is compromised, such as malicious plug-ins or extensions. 
9. Security Logging and Monitoring Failures - when proper logging is not implemented, there is no record of how a breach occurred.
10. Server-Side Request Forgery - #SSRF occurs when a user submitted #URL is not validated and the web application fetches a resource for an invalid user.