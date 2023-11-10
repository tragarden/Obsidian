# Windows Network Command Line 1.2

### Configuring IP

‘ #ipconfig’ is often the** first step in diagnosing issues** with your #network.  This command will tell you #TCP/IP information, info about the local #router, #gateway #DHCP server, #DNS server, and information about your devices and adapters. 

‘ #ping’ command tells you about the **round-trip time for data requests** to be sent and responded to by the #server.  It includes data about any #packet sent, the number of bytes submitted, #latency or response time, and the Time to Live ( #TTL) for each of these requests.  Below this provided data is a **loss percentage indicating the success rate** of your ping attempts.  This uses the *Internet Control Message Protocol* ( #ICMP) to reach out from the client to the host and back again. 

‘ #netstat’ is a #utility that is available on most operating systems. 

Flag **‘-a’** will show **all active connections.**

Flag **‘-b’** will **show binaries for Windows** #OS and requires you to ***run as administrator. ***

Flag **‘-n’** will stop resolving names and **return all device names as #IP addresses.**

‘ #nslookup’ will allow you to **inspect the query sent from your client to a DNS server** and the subsequent resolution of *Fully Qualified Domain Name* ( #FQDN) to IP address.  This will ***tell you the server used, IP addresses, name of the website, and addresses of the servers*** associated with that domain name.

‘ #net’ is used in conjunction with flags and modifiers to achieve a specific outcome. 

**'net view' \<server> or /workgroup:\<workgroupname> will tell you about the indicated destination.** 

**'net use'** will **submit a network share to an indicated drive.**
**
'net user'** will **tell you user account information** and password reset prompts.

‘ #tracert’ will **show us the route a #packet takes** to the requested destination.  It **maps the entire path of the packet using** #ICMP #TTL Exceeded error messaging.  In these cases, **TTL indicates the total #hops,** or how many devices must be accessed before this packet is delivered. 

**Sometimes tracert will fail because the destination for the request is using a firewall** to filter ICMP requests or the ICMP requests are set to a low priority and are not getting through.

Tracert command is **useful in diagnosing pathing on your local network,** you can see the path of each request as it is passed through your local #network and observe any bottlenecking on unnecessary hops.

‘ #pathping’ is included with *Windows NT* and all later versions. This process begins with a #traceroute phase that **maps out the hops, and a second ping phase that measures the duration of request completion and any packet loss that occurred.**

#### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/the-windows-network-command-line-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [011 An Overview of Windows](011%20An%20Overview%20of%20Windows.md)
- [011 Windows Features](011%20Windows%20Features.md)
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [018 Operating Systems Overview](018%20Operating%20Systems%20Overview.md)
- [021 Active Directory](021%20Active%20Directory.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)

#study #professormesser #comptia #Aplus #software #CLI #commandline 