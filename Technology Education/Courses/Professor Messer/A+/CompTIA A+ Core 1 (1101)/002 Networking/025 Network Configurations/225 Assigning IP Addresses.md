# Assigning IP Addresses 2.5

### IP Addresses

#IPv4 address assigning *used to be a manual process*.  **You would have to set** #IP, #subnet mask, #gateway, #DNS, #NTP, and others on your own.  In October 1993, #BOOTP was created as a #bootstrap #protocol for automatically configuring and allocating IP addresses on your system. It requires some manual configurations, and** you must manually inform the system that a previously used IP is once again available**.  #DHCP replace this system in 1997, fully automating the distribution of IP addresses.  Multiple DHCP servers are often used in conjunction in case one happens to fail. 

#### DHCP

DHCP processes are described by the acronym #DORA:

- **Discover** a DHCP server.  This can be imagined by a **client workstation (WITHOUT IP) broadcasting** to all devices on the network **via port udp/67**, seeking IP address assignment. 

- **Offer**  get an IP offer from the DHCP server.  Once the #broadcast from the client is received, the **DHCP server sends a broadcast over port udp/68** that should be received by the client that sent the request broadcast.  The **client may receive multiple offers** from several DHCP servers.

- **Request** the IP offer from the DHCP.  This comes in the form of a **second broadcast across port udp/67**.

- **Acknowledge** the assigned IP via **DHCP server confirmation**.  This response is a confirmation **of successful IP address assignment** and is once again broadcasted across **port udp/68**.

DORA process happens every time a device requests an IP address from a DHCP server.

A DHCP #proxy is a #router with *DHCP Relay* (IP Helper) enabled.  Typically, ***routers do not allow the passing of broadcast signals***.  This can be **bypassed by programming the router** to allow broadcast signals to reach the DHCP server.

DHCP assigns IP addresses from what is called a *pool of IP addresses*.   If you want a device to retain an unchanging IP address, an **administrator can disable DHCP on a device** and manually assign the IP.  An alternative and possibly better solution is to **configure an IP reservation on the DHCP server**, where a MAC address is associated with the IP you want to reserve. DHCP **reservation is preferable as manual assignments** are time consuming and must be manually updated. 

*Automatic Private IP Addressing* ( #APIPA), also known as a *link-local address*.  Usually, devices on this network **can only communicate locally**, and **cannot be forwarded** to another network by a router.  #IETF reserved the IP range 169.254.0.0 through 169.254.254.255, reserving the first and last 256 addresses.

*Address Resolution Protocol* ( #ARP) is used to **confirm that an IP address isn’t currently in use** before it is assigned.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/assigning-ip-addresses-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [126 DNS Configuration](126%20DNS%20Configuration.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [226 DHCP Configuration](226%20DHCP%20Configuration.md)
- [227 Network Types](227%20Network%20Types.md)

#study #professormesser #comptia #Aplus