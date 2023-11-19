# IP Addresses

### MAC Address

Media Access Control ( #MAC) addresses are associated with each networked device, or #host. While they can tell you the exact host via this identifier, you would not be able to communicate across a network with only a MAC address. Each host's MAC address is associated with an #IP address that's assigned by the DHCP server. An #IPv4 / #IPv6 address is composed of the #network address and the host address.

You can think of an IP address as the city, state, and building address, while the MAC address describes the apartment number and designated room within.

### Composition

#IPv4 addresses use 32-bit #binary composed of 8-bit units known as #octets. These octets combine to form 4 bytes.

We know that IP addresses are divided into two parts, a network part and a host part. A #router handle MAC address assignment and the network part is managed by a network administrator. 

### Subnet Mask

The #Subnet mask is used to determine which bits to use when determining the positions of the network and host parts of the IP address. 

### Gateway 

The Default #Gateway is the IPv4 address of your #router. This is used to coordinate with the protocols of the internet and manage the addressing within your network. It is common practice to assign the default gateway IP to the last available address within your subnet. 

### Broadcast 

The #Broadcast IP sends a #packet to all hosts on the network used to connect them. Once all of the hosts receive a broadcast, they know the IP of the default gateway and can begin communicating with it. 

### CIDR

Classless Inter-Domain Routing ( #CIDR) is represented by a suffix that indicates the amount of bits from the beginning of the IP address are network bits. It specifies the number of 1-bit items in the subnet mask. 

For the address 198.162.0.1/24, the /24 is the CIDR suffix that indicates what type of subnet this network is using.

/8 indicates a subnet of 255.0.0.0
/16 indicates a subnet of 255.255.0.0
/24 indicates a subnet of 255.255.255.0

In the example copied from HackTheBox, you can see that there are 3 sets of 8 bits. 255 is the equivalent of 8 consecutive 1's in binary. So 255.255.255.0 contains 24 1's - hence the /24 suffix.

```
Octet:             1st         2nd         3rd         4th
Binary:         1111 1111 . 1111 1111 . 1111 1111 . 0000 0000 (/24)
Decimal:           255    .    255    .    255    .     0
```