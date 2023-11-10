# Common Port Numbers 2.1

The following are commonly used ports that are standard for most applications.  You will memorize this over time, and they are ***important for #firewall configuration***. You will need to *know the #port number, protocol, and the method used by the protocol.*

#### Most Common

##### TCP

#TCP operates on port **tcp/20 (active mode data)** and port **tcp/21 (control)** to transfer files between systems. TCP will *authenticate via username and passwords*, although some systems will use anonymous login.  #FTP also allows for file management, such as copy, move, and delete.

##### SSH

#SSH commonly uses port **tcp/22.**  SSH should *always be used over Telnet for remote communications*.

##### SMTP

*Simple Mail Transfer Protocol* ( #SMTP) uses port **tcp/25** and enables *server to server email transfers*, and sends mail from a device to the intended server. 

##### DNS

*Domain Name Server* ( #DNS) uses port **udp/53** to convert URLs to IP addresses. 

##### DHCP

*Dynamic Host Configuration Protocol* ( #DHCP) **assigns new IP addresses to devices** that join the network, such as the example of connecting your laptop to the Wi-Fi of a business.  This is often done on ports **udp/67 and udp/68.**  This will *require your own server to host the DHCP requests*, but this is often included in many appliances used today.

- IP addresses are **assigned from a pool that is generated in real time**.  When you turn on your computer, it contacts a DHCP server, and this server configures all the IP configurations for your current setup and network.

- DHCP uses a **leasing system** to assign IP addresses, meaning that once a device is not actively using it’s IP for a length of time, the IP is returned to the pool of IP addresses the DHCP distributes from.

- DHCP Reservations allow you to **reserve a specific IP for a specific MAC** address.  This also allows you to change device configurations remotely, if the DHCP reservation is in place.

##### HTTP(S)

#HTTP is commonly associated with **port 80**.

#HTTPS is commonly associated with **port 443**.

##### POP3

*Post Office Protocol 3* ( #POP3) is a simple service for mail transfer, using **tcp/110**.  This method is limiting, and *only allows you to be logged into one device* at a time. 

##### IMAP4

*Internet Message Access Protocol v4* ( #IMAP4) is the protocol that allows you to sync and access your *mail on multiple devices simultaneously*.

##### SMB

*Server Message Block* ( #SMB), also known as the *Common Internet File System* ( #CIFS), is used by Microsoft Windows for **file sharing and sending jobs to printers.**

- Older systems with SMB use the *Network Basic Input/Output System* ( #NetBIOS) over a TCP/IP connection.  It usually uses **udp/137** (NetBIOS name services (nbname)), which finds devices on your network by their name.  **tcp/139** (NetBIOS session service (**nbsession**)) is *used to set up a session* to communicate between devices.

- *Modern devices* can communicate directly via tcp/ip over port **tcp/445**, which does not require the use of NetBIOS for communication.

##### SNMP

*Simple Network Management Protocol* ( #SNMP) is used for network management by **gathering statistics from network devices.**  Queries are performed via port **udp/161.**  *Traps are implemented to detect unusual or malicious activities* on a network and report data back to the admin.  ***Traps are sent via port udp/162.***

*SNMP v1* had structured tables and data was stored ‘in-the-clear’, meaning it is *unencrypted.*

*SNMP v2* allowed users to make enhancements to data type, conduct bulk data transfer, but was *still lacking encryption.*

*SNMP v3* allows for authentication and encryption, meaning **greater message integrity.**

##### LDAP

*Lightweight Directory Access Protocol* ( #LDAP) uses port **tcp/389** to collect and **access data stored in a network directory**, commonly used in Microsoft Active Directory.

##### RDP

*Remote Desktop Protocol* ( #RDP) uses port **tcp/3389** and is the standard for Remote Desktop Services for Windows. It can be used with Mac, Linux, and other OS to connect to a Windows Desktop Remotely.  It may control the entire desktop or a specific application.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/common-network-ports-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [121 Introduction to IP](121%20Introduction%20to%20IP.md)

#study #professormesser #comptia #Aplus 