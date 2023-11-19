# Network Topologies

A #Network #Topology is a depiction of the physical and logical connections within a network. It shows each piece of network #hardware and the mapped relationships they have with each other. 

### Topology Components

A topology is made up of representations of the connections, nodes, and classifications of a network. 

- Connections refer to wired and wireless connections like #ethernet, #coaxial, #fiber, #Wi-Fi, #Cellular, and #Satellite. 
- Nodes refer to Network Interface Controllers ( #NIC) which are the transmitting and receiving devices on your network, such as a #router, #modem, #gateway, #firewall, or #switch.
- Classifications refer to the eight types of network topology styles or formats.

### Topology Types

#### Point-to-Point

Point-to-Point topologies are the most basic as they are a single connection between two devices.

#### Bus

#Bus topologies represent networks where all hosts have access to the transmission medium, which is shared by all hosts. Due to the sharing nature of the network, only one host can transmit, and all other hosts must determine whether the transmission was intended for them.

#### Star

#Star topologies indicate a central network device that manages individual connections to each host on the network. All connections pass through the central device, and this device determines the routing of packets across the network. This can be taxing on the router.

#### Ring

#Ring topologies operate as a unidirectional cycle with a predetermined transmission direction. You can think of this as each device 'passing it to the left', A passes to B passes to C passes to A, and not the other way around or any variations on this. This is maintained via a #token system that passes from each device in one direction.

#### Mesh

#Mesh networks use many wireless components that are all capable of transmission and reception, working together to create a strong and far reaching network. This allows multiple devices to share traffic load via load balancing, and with the addition of more devices, the more efficiently the network operates. In a fully meshed network, all devices are connected and transmit. In a partially meshed network, there is only one connection between two nodes.

#### Tree

#Tree networks are a collection of several #star networks.  This is usually managed by a main server, and most large networks and regional networks take this structure. 

#### Hybrid

Hybrid networks are any network that uses **more than one** of the above topologies. A network using two tree topologies is only a tree topology.

#### Daisy Chain

Daisy Chain topologies indicate devices that are linked physically from one unit to the next.  This uses a #token system like #ring topologies, and are popular with automation networks.