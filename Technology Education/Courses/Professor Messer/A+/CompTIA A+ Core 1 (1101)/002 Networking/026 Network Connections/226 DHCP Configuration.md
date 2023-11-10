# DCHP 2.6

### Scope

#Scope must be considered when configuring your #DHCP and includes the **range of IP addresses you’re working within**, the #subnet mask, lease duration times, #DNS server information, default gateway, and #VOIP server settings.

The DHCP selects an #IP address from a *pool of addresses*, usually grouped **within different subnets**.  ***Scope is the single contiguous pool of IP addresses*** with manually configured exceptions.

### Assignment

*Dynamic assignment* means that your device will receive a lease offer from the DHCP server, and after a certain amount of time this address will be reclaimed by the DHCP server.

*Automatic assignment* **functions similarly** to dynamic assignment but **uses a list of past assignments** to remember previous address allocation.  This means that you should get the same IP address each time you use a device, and the DHCP server will not reclaim this address after #time-to-live ( #TTL) expires.

### Leasing and Reservation

*DHCP Leases* are temporary but depending on the frequency of use for your device, **may seem more of a permanent assignment**.  #Allocation is when a device is assigned an IP address from the DHCP server, and **reallocation happens when you lose power or otherwise reboot** your computer.  The device will make another DHCP request to confirm the lease.  Any client can also manually release an IP.

*Address reservation* is based on the #MAC address burned into the hardware of the device.  These reservations must be **configured by an administrator**.  This is also known as #Static DHCP, *Static Assignment*, or *IP Reservation*.

#### Lease Timers

#T1 timer checks in with the DHCP server at **50% of the lease time**, seeing if the IP address needs to be renewed.  This ***timer will reset if the client is still requesting a lease at the 50% mark***. 

#T2 timer occurs at **87.5% of the lease time** and will ***attempt to bind to any DHCP server*** if the server it is connected to is currently down.

There are **three periods within the lease time**: 
1. *Normal Operation*, or the **first 4 days within the T1** timer.  
2. *Renewal Period* occurs **after the first 4 days**, falling under the umbrella of **T2 timer**.  If renewal is requested during this time, then a new DHCP server must be contacted for this request.  
3. This leads to the *rebinding period*, which **happens on the final day** of the lease.  The DHCP server will change and allocate the existing IP address back to the client.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/dhcp-configuration-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [121 Introduction to IP](121%20Introduction%20to%20IP.md)
- [125 IPv4 and IPv6](125%20IPv4%20and%20IPv6.md)
- [225 Assigning IP Addresses](225%20Assigning%20IP%20Addresses.md)

#study #professormesser #comptia #Aplus #defaultgateway #IPreservation #network
