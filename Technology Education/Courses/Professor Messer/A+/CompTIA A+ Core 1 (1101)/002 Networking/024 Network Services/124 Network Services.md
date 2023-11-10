# Network Services 2.4
#### Data Centers

Data centers are large spaces that contain many types of computers and #network devices operating in close quarters. 

All data centers will have a server or group of load balanced servers for their Domain Name System.  It is usually managed by your #ISP or an IT department. #DNS uses a distributed naming system and load balancing, so that users don’t encounter problems when there is high traffic from many simultaneous inbound requests. 

#### DHCP

*Dynamic Host Configuration Protocol* ( #DHCP) is an automatic #IP address configuration that is available on the type of basic #router you use at home.   Basic settings for configuring your IP include lease time allotted for each device to retain an IP address, and the range of available IPs in the selection pool.

#### Servers

##### File 

*File Servers* are **centralized storage that allows you to store files on your network** which often uses a straightforward folder system and #GUI so you can easily find and store files. The front-end, or GUI, hides the #protocol and yields an easy user interface.  #Microsoft uses *Server Message Block* ( #SMB) and #Apple uses *Apple Filing Protocol* ( #AFP).

##### Print 

*Print Servers* are hardware or software that **host printing services for all devices on the network.**  In the case of software, the hardware of the device running the software will be used to host the print server.  In the case of hardware solutions, these come as **network cards or adapters that facilitate the communications from the clients to the printers via ethernet** connection.  Some standards for printing protocols include Microsoft’s SMB, *Internet Printing Protocol* ( #IPP), and *Line Printer Daemon* ( #LPD).

##### Mail

*Mail Servers* store your incoming mail and send your outgoing mail, and this service is managed by an IT department or your ISP.  This is one of the most important services and requires constant support and monitoring.

##### Syslog

#Syslog is a standard for **logging system activities and consolidating them before sending them to a central database** to be stored.  This is **done via an event manager** often referred to as a #SIEM.  These devices store their data on very large storage systems that often have data overlap for backup.

##### Web

*Web Servers* **hosts the web pages and respond to browser requests from clients** requesting the site data.   It uses the #browser protocols of #HTTP and #HTTPS, and the web pages are constructed of #HTML and #HTML5 code. 

##### Authentication

*Authentication Servers* are **centralized management of login verification** and is almost always a service for an enterprise, NOT for home use.  This is a service that should ALWAYS be available and is an extremely important service for the network. 

#### Spam

#Spam refers to the **unsolicited messages** we are bombarded with on any email or home address.  Usually used for advertising or scam purposes, it is a significant issue in the technology world and raises valid security concerns.  We must ensure that members of the network are aware of known scams like #phishing attacks.  ***Resource utilization becomes an issue as well, since we must determine what is considered spam, where it is stored, and how long it will be stored for.***  Storing spam requires drive space and can become surprisingly costly.

##### Gateways

*Spam Gateways* can be on-site devices or cloud-based and operate with the help of a firewall.  The firewall redirects any questionable content to the mail gateway, which operates on a screened subnet of the main network.  This device then **decides the level of concern to apply to any given piece of mail,** and then either discards it or forwards it to the internal mail server.  Sometimes less malicious content will be sent to the internal network to be sorted into the individual spam folders of the user.

##### All-in-one

*All-in-one security devices* are **next-generation firewalls,** also known as *Unified Threat Management* ( #UTM) or a *Web Security Gateway*.  Some of these devices have **URL filtering, bandwidth shaper, virtual protected network, malware inspection, spam filter, and content inspection built in**.  Some also have connectivity for **CSU/DSU and WAN**. They may offer *Intrusion Detection System* ( #IDS) and *Intrusion Protection System* ( #IPS).

##### Load Balancing

*Load Balancers* are used to **allocate data traffic evenly across all available hardware**.   This prevents a single server from getting overtaxed by evenly distributing the workload across multiple devices.  This is called a ***configurable load*** and allows for management across multiple servers.  

Some features include *TCP offload*, which enables you to **maintain a direct TCP connection across your devices**.  

*SSL Offload* allows the load balancer to manage all the encryption and decryption instead of using server power.  

#Caching allows for the balancer to **retain query data so that it can respond on behalf of the servers** to web requests.  You can also set **content prioritization, as well as content switching**, delegating specific data to specific servers. 

#### Proxy

A #proxy server is used as a preliminary ‘guinea pig’ device that **receives data before you main servers**.  It does this to **verify that incoming content is not malicious**, and if it is – the ***proxy server will assume all damages*** and your important servers will be spared.  These often offer features such as **access control, caching, URL filtering, and content scanning**. 

#### SCADA

*Supervisory Control and Data Acquisition System* ( #SCADA) is a large scale, multi-site *Industrial Control System* ( #ICS).  This ***manages power generation, refining, manufacturing, facilities, energy, logistics***. These are **distributed control systems** that use real-time information for system control. 

#### Legacy

#Legacy systems are ***outdated and old*** systems that an organization is still relying on because it is too costly or there is no appropriate solution for them to switch to.  This means that someone may need to learn outdated hardware and languages in order to manage legacy technology.

#### Embedded

An #embedded system is a purpose-built system that allows access for a specific function but ***does not typically allow the user to access the operating system***.

##### Internet of Things

*Internet of Things* ( #IoT) devices usually require a segmented network or a **subnet to isolate them** from the main network, as they are often weak points in our network security.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/network-services-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [023 Malware](023%20Malware.md)
- [027 Mobile Device Security](027%20Mobile%20Device%20Security.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [123 Wireless Network Standards](123%20Wireless%20Network%20Standards.md)
- [126 DNS Configuration](126%20DNS%20Configuration.md)
- [136 Multifunction Devices](136%20Multifunction%20Devices.md)](223%20Wireless%20Network%20Technologies.md)
- [223 Wireless Network Technologies

#study #professormesser #comptia #Aplus #datacenter #loadbalancing #file #print #mail #web #authentication #gateway #ssl #TCP 