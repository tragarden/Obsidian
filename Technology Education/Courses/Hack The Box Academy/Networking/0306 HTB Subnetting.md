### Subnetting

#### Subnets

A #Subnet is a logical division of the range of available #IPv4 addresses within a #network. There is a given range of IPs under the umbrella of the network address. These are divided into segments of the network that can keep devices on separate subnetworks. 

The #Network part of the IP address is fixed and cannot be modified. This is used to determine the network of which the subnet is contained within.

The #Host part has bits that can be modified to indicate either the first or last address in the range. The first address in the range is the #Network address and the last address in the range is the #Broadcast address. A #router must be used to communicate between different subnets.
In other words: 
- Setting all host bits to 0 will yield the network address of the subnet.
- Setting all host bits to 1 will yield the broadcast address of the network.

A #Subnet mask determines where the divisions in the network occur.

There is a LOT of math involved in determining subnets, and this can be explored further in external sources. For practical purposes, we tend to use one of four common octet sets to determine the subnet. /8, /16, /24, and /32 octets cover all possible subnet configurations for any network. If you see an octet identifier that is not one of these, such as /17, you round up to the next octet identifier - /24 - because 17 WILL NOT fall under the umbrella of /16.

