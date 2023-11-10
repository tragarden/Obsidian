# Securing SOHO Networks 2.9

### Small Office / Home Office (SOHO)

The most important thing you can do to protect your #SOHO is to **change your #network passwords and username from the default assignment.**

#Firmware updates are vital and **making sure your network hardware is regularly updated** is important.

#### Filtering

#IP *Address Filtering* is useful to **limit traffic to routers by using deny and allow lists.**  The #firewall can stop all traffic except for exceptions from the #whitelist.  Alternatively, you can #blacklist IPs that you do not want to contact and take on the risk of unknown entities trying to access.

*Content Filtering* limits traffic **using methods like #URL filtering and Website Category Filtering to analyze the content of sites and block them accordingly.**  These are often used in the form of *Parental Controls* and are excellent **for blocking NSFW materials, viruses,** and #malware.

#### Positioning

The physical position of #hardware like a #wireless #router or access point must be considered as certain materials can impede signals and sometimes are vulnerable to outside attackers due to their accessibility.

#### IP Addressing

*Manual IP Addressing* is useful for #SOHO networks because while this increases #security, it would be extremely time consuming to implement this method to a large organization.

#DHCP reservations are **configured by the administrator and relate to a #MAC address table.**  This means that **every time a device is connected it will receive the same IP from the DHCP server.** This is also known as ***Static DHCP, Static Assignment, or IP Reservation.***

A Static #WAN IP will establish that **every time your device is connected to the internet beyond your local network, it will have the same IP.**  This is convenient and attainable in a SOHO network, allowing technicians to know the IP of a device at all times. Most #ISP's allocate WAN addresses dynamically, so requesting a static IP from them may cost extra.

#### Plug and Play

*Universal Plug and Play* ( #UPnP) means when you connect your device to the network, it will automatically configure itself, known as *Zero-Configuration.*  This will automatically generate rules for the #firewall that allow applications within your network to open inbound ports via the UPnP interface.  This is a security threat and should be disabled, only enabling it when required by an application.

#### Subnet

A *Screened Subnet,* formerly known as a *Demilitarized Zone* ( #DMZ) is a virtually separate network known as a #subnet that allows for public access to public resources while keeping the public away from private data.

#### SSID

*Service Set Identifier* ( #SSID) is the identifier of your local network – change this to something not-so obvious and disable SSID broadcasting if possible.

#### Channels and Encryption

Wireless Channels and #Encryption types:

*Open System* means there is **no password required,** there is no #authentication.

*WPA/2/3-Personal* and #PSK are both **256-bit keys** that are shared by the admin as *Pre-Shared Keys.*

*WPA/2/3-Enterprise* and 3-802.1X will use an #authentication server like #RADIUS or #LDAP to authenticate.

#Channel frequency is determined by availability – you will need to **choose the channels with the least amount of frequency interference.**

*Guest Networks* should be disabled unless you choose to encrypt them for #IoT or Lab purposes.

#### Ports

Any #Port that is unused should be disabled by the #administrator on the #switch forcing authentication via *Network Access Control* ( #NAC) on the 802.1X networks.  This will require authentication before communication can occur.

#Port *Forwarding* will **take Inbound data at a specific port and forward it to another device** on the #network.

When an **external IP or port is mapped to an internal IP,** this is called a *Destination NAT or Static NAT.*  This **translates the public IP to a private IP.**  Once implemented it must be disabled as it does not expire or time out.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/securing-a-soho-network-comptia-a-220-1102-2-9/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [022 Wireless Encryption](022%20Wireless%20Encryption.md)
- [121 Introduction to IP](121%20Introduction%20to%20IP.md)
- [125 IPv4 and IPv6](125%20IPv4%20and%20IPv6.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [225 Assigning IP Addresses](225%20Assigning%20IP%20Addresses.md)
- [227 Network Types](227%20Network%20Types.md)

#study #professormesser #comptia #Aplus #accesspoint 