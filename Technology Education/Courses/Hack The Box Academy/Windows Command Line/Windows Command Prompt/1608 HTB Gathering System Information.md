# Gathering System Information

Information Gathering is an important skill for penetration testers and system administrators. This is also known as host #enumeration and provides valuable data for both red team and blue team members. This module will show you how to use Command Prompt to gather the information from a target host.

Possible targets you will want to enumerate are represented in this great hierarchy from HTB:

![Types of Information](https://academy.hackthebox.com/storage/modules/167/InformationTypesChart_Updated.png)
Ultimately we are seeking information from the four distinct categories outlined above:

- System Information - host name, #OS details, and patches.
- Networking Information - Host #IP, network interfaces, subnets, DNS servers, known hosts, and resources on the network.
- Domain Information - Active Directory information from the target system's domain.
- User Information - local user information, environment variables, running tasks, and services.

### Enumeration Methods

#### systeminfo

The systeminfo command is a good single method for enumerating a lot of data about the target host. When we want to avoid multiple command submissions, this is an excellent tool because it provides a lot of viable information with a single execution. This is useful for not being detected when executing commands on a remote host. 

##### hostname

We can reveal the hostname of the target host with the hostname command.

##### ver 

We can reveal the version number of the target hosts #OS with the ver command.

##### ipconfig

The ipconfig command lists any #TCP/IP configurations on the target host such as Domain Name, #IPv4 address, #Subnet Mask, and Default #Gateway.

- /all - this option in conjunction with the ipconfig command will reveal more detailed information about the target network configurations. This will reveal information about #MAC addresses, #DHCP configurations, and what #DNS servers the target host uses.
##### arp

Address Resolution Protocol ( #ARP) can be used in conjunction with the arp tool in command prompt to examine the arp cache. This tool provides a lot of information and will be thoroughly explained in later modules.

#### whoami

The whoami command reveals information about the user, group, and the privileges of the current user. If the current user is not within the domain of the network the #NetBIOS name will be used instead. This is often the current hostname being used.

- /priv is an option we can use with whoami to see the privileges of the current user.
- /groups is another option for whoami that reveals any groups the user is in.
- /all will reveal the information for both /priv and /groups

#### net user

The net user command reveals all users on the target host and information about them. With this tool you can also create and delete users.

#### net group

The net group command works similarly to net user, but for groups. You can create and delete groups with this command. This command must be used against a domain server. If you want to run this command against a specific host, you need to use the net localgroup command.

#### net share

Network shares are used to share resources across a network. These often contain sensitive information and are particularly vulnerable. We are able to employ the net share command to reveal any shares on the network. Shares can be used to gain lateral movement through a network and should be thoroughly investigated any time we are enumerating. 

#### net view

The net view command can be used in cases where net share are not fully useful. It will enumerate shared resources including domains, shares, printers, and other objects within the network. 

### Remember

It would be unusual for anyone to use command prompt to enumerate a target host, but it is certainly possible as demonstrated here. Using net * commands is also highly unusual and risks detection by an administrator. A properly monitored network with appropriate measures for logging should be able to detect either of these methods of enumeration. 

