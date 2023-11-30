# MAC Address

Media Access Control ( #MAC) addresses are a physical address of a network device in 48-bit hexadecimal format. These addresses are used in #Bluetooth, #WLAN, and #ethernet. 

A MAC address is composed of two 3 byte parts: 

The first part is called the Organization Unique Identifier ( #OUI). These identifiers are issued by the Institute of Electrical and Electronics Engineers ( #IEEE).

The second 3-byte portion of the MAC address is called the Network Interface Controller ( #NIC) or the Individual Address Part. This is combined with the #OUI to create a unique MAC address.

Address Resolution Protocol ( #ARP) uses #IPv4 to identify any MAC addresses associated with a certain #IP. 

When MAC addresses are communicating within the same #subnet, then the target IP destination for a given MAC address will be the destination computer or device. If they are on different subnets, the destination IP for the MAC address will be the Default Gateway, or #router, which manages all the #OSI Layer 2 communications. Layer 2 is the #Data-link layer.

The last bit of a MAC address indicates the state of the transmission, #Unicast or #Multicast. Unicast is represented by a 0 and Multicast is represented by a 1.

Multicast transmissions are #broadcast across the #network to all devices. The intended device(s) will respond to the broadcast 

Address Resolution Protocol ( #ARP) operates on layer 3 and layer 2 of the #OSI model, the #Network and #Data-link layers. At this stage, the IP address is resolved to a MAC address. When the multicast transmission is broadcasted across the network, the receiving device responds with it's own MAC address, confirming reception. This is known as #ARP resolution.

An ARP request is broadcated across the whole network asking to resolve a device's IP address to a MAC address. The matching device will then respond to the multicast transmission.

An ARP reply is when the receiving device responds with it's own MAC and IP addresses.

ARP is vulnerable to a few types of attack, such as:

- MAC spoofing is when the MAC address of a device is modified or changed to match a specific device on an established network.
- MAC Flooding is when an attacker spams packets to the network switch, over-taxing the MAC address table and breaking it.
- MAC address filtering is used to determine the addresses to be used in a spoofing attack.
- 