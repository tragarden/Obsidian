# IP Standards 2.5

### IP Standards

#IPv4 addresses are what most people recognize as an #IP.  It is the primary #protocol and existed before IPv6. #IPv6 is now incorporated into all major operating systems and is used in all internet infrastructure.

#### Octets and Binary

IP happens on **layer 3** of the #OSI model.  The address **contains 32 bits, or 4 bytes, or 4 binary octet**s.

- 192.168.1.131 = 11000000. 10101000. 00000001. 10000011

- ^ 8 #bit = ^ 1 #byte = ^ 1 #octet

**Each octet** equates to a #binary value of or **between 0 and 255**. 

#### Why IPv6?

IPv4 was used exclusively until its **capacity for usable addresses started to become an issue**, which is when ***IPv6 was introduced with 128-bit addresses as a standard***.  128-bit standard meant that now each one of the 7 billion+ people on earth can have trillions of individual IPs.  This makes your DNS very important, as these IPs are difficult to remember and are very long with many characters.  The **first 64 bits is considered the network prefix** (/64) and the **last 64 bits is the host network address**.

#### Subnet Mask

#Subnet *mask* (ex: 255.255.255.0) is used by the local device to determine its current #network.  The **subnet mask is not shown in transactions across the network**, so you will need to ask someone for the subnet of a given item all the time.  IPs work in conjunction with subnets. 

#### Default Gateway

*Default Gateway* is the #router that **connects your network to your ISP**.  This MUST be an IP on the local subnet. 

#### Domain Name Server

#DNS servers **translate a human language request** of names via URL or search bar, **into a set of IP addresses** that a router can understand.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/ipv4-and-ipv6-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [126 DNS Configuration](126%20DNS%20Configuration.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [227 Network Types](227%20Network%20Types.md)

#study #professormesser #comptia #Aplus #defaultgateway