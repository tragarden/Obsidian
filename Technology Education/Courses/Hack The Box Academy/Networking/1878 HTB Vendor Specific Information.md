# Vendor Information

### Cisco

#Cisco #IOS is the operating system for Cisco brand devices and is required for the operation of these devices. Command Line Interface ( #CLI) is the method for interacting with the Cisco IOS, although #GUI options are available as well.

Included within the Cisco operating system is a range of services and protocols that facilitate access and setup for the different aspects of the devices and network. 

#### Services and Protocols

Routing Protocols determine where data packet traffic is directed.

Switching Protocols manage the switch devices on your network via VLAN Trunking Protocol ( #VTP) and Spanning Tree Protocol ( #STP).

Network Services manage IP addressing and network configuration via Dynamic Host Configuration Protocol ( #DHCP).

Security features include Access Control LIsts ( #ACL) which determines which devices on the network get access to resources on the network. 

#### Passwords 

There are a few types of password types associated with Cisco IOS that yield varying levels of security and access.

- User passwords are used to log onto Cisco IOS. 

- Enable passwords are used to toggle 'enable' mode on your devices.

- Secret passwords are used to limit access to remote management services.

- Enable Secret passwords are used for the highest level of security within the #OS, toggling 
enable mode for all services and configurations. 

#### SSH and Telnet

You can configure Cisco devices remotely using #SSH and #Telnet. When accessed remotely, you will see the User Access Verification message after you supply the needed credentials to access the network. 

### VLAN

A Virtual Local Area Network ( #VLAN) is used to logically segment a network or device, which allows you to effectively turn a single #switch into several smaller, logically separate switches. This is done by creating a logical grouping of network endpoints associated with specific ports on a switch. This means that each VLAN created will need to have it's own #subnet.

VLANs are useful for separating different parts of a network and placing vulnerable devices within a network that has less privileges and access than other subnets. You can put a certain department of a company within its own subnet.

You can choose between #static and #dynamic VLANs depending on the situation. Static VLANs are more secure, while Dynamic VLANs are more convenient but require more administration. 

#### Access and Trunk Ports

Each individual switch port must be defined as either an access #port or a trunk port. Access ports facilitate the transmission traffic of a single VLAN. Trunk ports are able to carry multiple VLANs' traffic and trunk links are able to connect two trunk ports on separate switches.

Standard #Ethernet do not contain VLAN information in their transmissions. This information must be logged and two different trunking methods are used to achieve this.

##### Inter-Switch Link

Inter-Switch Link ( #ISL) is an outdated trunking protocol that is proprietary to Cisco devices.

#### IEEE 802.1Q

#IEEE 802.1Q is a protocol that is used to add a header to an #ethernet frame. This header contains a Tag Protocol Identifier ( #TPID), a Priority Code Point ( #PCP), a Drop Eligible Indicator ( #DEI), and a VLAN Identifier ( #VID).

##### TPID

Tag Protocol Identifier ( #TPID) is used to identify the ethernet frames as an 802.1Q frame by using a zeroed out 16-bit field.

#### NIC

Network Interface Cards ( #NIC) are pieces of #hardware within a device that allow it to be identified and communicate across a network. 

#### Assigning NIC as VLAN in Linux

BRUH just seek out the documentation this shit too crazy to outline fr. 

IN OTHER WORDS I DID NOT FINISH THIS CRAZY ASS MODULE BC THERE IS JUST TOO MUCH DAMN INFO THAT FEELS USELESS TO ME UNLESS I AM ACTIVELY CREATING A VLAN ON WINDOWS OR LINUX

THERE IS A LOT OF INFO IN THE END OF THIS MODULE BUT WTF IT IS OVERWHELMING AND SO PROPRIETARY TO CISCO I HATE IT LOLLLLLL WTF

#### VLAN Hopping

VLAN hopping is an exploitation of Cisco's Dynamic Trunking Protocol ( #DTP) which is used to facilitate a connection between two Cisco devices while bypassing the #router. This attack can only be perpetrated if the attacker is able to physically connect to a port on the switch to install DTP packets on a DTP enabled device. This will allow for 

#### VXLAN

#### CDP

Cisco Discovery Protocol ( #CDP) is used by devices on the network to identify other devices they are directly connected to. This is useful for mapping out a network and generating the natural topology of relationships between devices.