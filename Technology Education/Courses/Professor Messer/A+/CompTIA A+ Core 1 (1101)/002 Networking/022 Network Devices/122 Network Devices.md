# Network Devices 2.2

#### Routers

*Routers* direct traffic to **different subnets based on the IP** addresses of incoming packets.  *Sometimes a switch contains a router*, and this internal router at stage 3 of the #OSI model is called a ‘**layer 3 switch**’. Commonly **used to connect different network types**, such as LAN to WAN or copper to fiber.

#### Switches

*Switches* are connected via copper cable.  A #switch *forwards traffic based on incoming #MAC* address data. Switches operate at **very fast speeds due to physical bridging** in their hardware, known as *Application-Specific Integrated Circuit* ( #ASIC).  This means that the forwarding **decisions happen within the hardware** itself and doesn’t use software or processing power.

***THE DIFFERENCE BETWEEN ROUTERS AND SWITCHES: 
ROUTERS FORWARD TRAFFIC BASED ON THE DESTINATION IP ADDRESS IN A PACKET, WHILE SWITCHES FORWARD TRAFFIC BASED ON THE DESTINATION MAC ADDRESS IN A PACKET.***

Some switches have hundreds of ethernet ports, and some can provide *Power over Ethernet* ( #PoE).

#Unmanaged switches are very simple devices with **few or no configuration options.**  Most will have a fixed configuration with little integration with other devices. 

- There are **no management protocols** to monitor the traffic or retrieve data from the device. 
- **No VLANs** either. 
- Low cost, *intended for home use.*

#Managed switches interconnect with other switches via 802.1Q and support #VLAN.  They allow for network monitoring and can have sophisticated integration with other devices.

- **Different sets of ports** on the same device can be **configured for different subnets**, or VLANs.  
- They can offer *Traffic Prioritization*, where you can set VoIP traffic to have a higher priority than other devices on the network.
- These are **commonly used in large businesses** or offices and may connect to other switches.  To prevent system loops, they **offer redundancy support** via *Spanning Tree Protocol* ( #STP).

#### Port Mirroring

- *Port #Mirroring* allows an admin to capture packets incoming on one port and forward the packet to its destination AND the mirror port.  Commonly **used for diagnostics and system management.**

#### Access Points

**Access Points** or Bridges are ***NOT wireless routers*** and only function as an extension of the wired network.  Its traffic **forwarding logic is based on MAC** addresses like a switch. 

#### Patch Panel

In an office scenario, you have many semi-permanent cables that connect a cubicle to a *patch panel.*  These connections are **rarely moved or modified.**  The patch panel would then connect to system switches via #RJ45 ( #ethernet) cables.

The patch panel **allows for changing the connection between user and the switch without changing the physical location** of the wires running from a certain desk.  The user can just move desks and have their location easily reassigned to the appropriate switch via the patch panel. 

All the **cables from the desks run to the back of the patch** panel, and this is usually only done once ever.  The **connections are permanently ‘punched down’** to the patch panel.  While this is permanent, connections from the patch panel to switches are not.  These connections are easily changed with the existing cables and without tools.

#### Firewalls

A #Firewall is used to **filter traffic by port numbers**, on OSI **level 4**, the TCP/UDP level.  Some firewalls have the capability to *filter application layer traffic*, these are **known as level 7 firewalls**. They can be used to **encrypt inbound and outbound network traffic**, which protects your data as it is submitted to sites. Some **can act as a proxy** for web traffic, examining incoming packets for malicious data. Some can be **used as routers with extra functionality.**

#### PoE

*Power over Ethernet* ( #PoE) allows you to run a **single cable to a device that supplies data AND power.**  This is very useful when incorporating peripherals like phones and cameras into your network.  It can also be **useful in supplying power to a difficult location.**

**Power for PoE systems can be provided by the switch**, in this case it is referred to as built-in-power or an #endspan.  If you do not have power from the switch, an *intermediary power injector* known as a #midspan must be implemented.  

There are *different power standards* for PoE dependent on the switch you are using:

- #IEEE 802.3af-2003 is the original PoE standard, yielding 15.4 watts of DC power @ 350mA.

- PoE+ : IEEE 802.3at-2009 had 25.5 watts @ 600mA max current.

- PoE++ : IEEE 802.3bt-2018 type 3 has 51 Watts @ 600mA max current.

- PoE++ : IEEE 802.3bt-2018 type 4 has 71.3 watts @ 960mA max current for 10GB/S devices.

#### Hubs

Hubs are also known as *Multi-port Repeaters* and were **used before switches** replaced them.  These are NOT sophisticated devices - data that is received by one port on the hub, is then sent to all active outbound ports and subsequent devices.  As more devices are connected to a hub, it typically loses performance. They are difficult to find, and only handle up to 100 megabits.

#### Modems

Cable #Modem allows for a #broadband connection, **transmitting across multiple frequencies** with different traffic types **over a single wire.** This is known as *Data Over Cable Service Interface Specification* ( #DOCSIS) and it allows for speeds **up to 1 gigabit/s.** They can support several services including *voice, data (internet), and video.*

*Asymmetric Digital Subscriber Line* ( #ADSL) is a type of #DSL modem where the **download speed is notably faster than the upload speed,** hence asymmetric. They can ***operate within 10,000 feet of the central office*** transmitting a signal.  52Mbs/s download and 16Mbs/s upload speeds are typical for these devices, with faster speeds occurring when nearer to the Central office.

#### Fiber Optic

*Optical Network Terminal* ( #ONT) connects your #ISP Fiber Optic network to a copper network that is likely on the outside of your house in a terminal box.  The #demarcation point (*demarc or delineation point) is the data center.*  It **translates the fiber optic signal from your ISP into the cable line** in an existing building.  Anything within your house is your responsibility, and anything past the demarc is the responsibility of your ISP.

*Network Interface Card* ( #NIC) is something that every device on your network has. This could support **ethernet, serial connections, or wireless.**

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/network-devices-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [131 Network Cables](131%20Network%20Cables.md)
- [025 Windows Firewall](025%20Windows%20Firewall.md)
- [016 Configuring Windows Firewall](016%20Configuring%20Windows%20Firewall.md)

#study #professormesser #comptia #Aplus #accesspoint #hub #fiberoptic #hardware