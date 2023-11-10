# Software Defined Networking 2.2

#### SDN

*Software Defined Networking* enables network devices to **have different planes of operation.**  In #cloud computing, we do not use physical hardware to be the intermediary between data transfer.  Instead, we **use virtualized versions of switches, routers, etc. to manage cloud computing.**  These virtualized hardware pieces can have each of their functions managed separately and individually.

These virtualized planes of operation occur on **three levels:**

1. *Infrastructure layer*, otherwise known as the *data plane*, **processes frame and #packet traffic** and may be responsible for forwarding, trunking, encrypting, and *Network Address Translation* ( #NAT). The Data Plane represents the ports that lead to other devices. 

2. *Control Later or Control Plane* **manages the actions of the Data Plane** and contains routing tables, session tables, NAT tables, and updates for the dynamic routing protocol. The Control Plane represents the processing aspects of the hardware.

3. *Application layer*, also known as the *Management plane*, **configures the device, and accesses SSH, browser, and API.** The Management Plane represents the main data connections and status lights.

These **three planes are derived from the physical interface** of the device.  They are called planes because **they virtually represent the ports and jacks you are looking at when you face the physical hardware.** ***There is a great illustration of what this looks like on his video.*** These layers are now modular and can be applied to other hardware.

The Data plane interacts with #network traffic, the control plane deals with dynamic routing protocols, and the management plane deals with #SSH, #SNMP. And #API.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/software-defined-networking-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [123 Wireless Network Standards](123%20Wireless%20Network%20Standards.md)
- [141 Cloud Models](141%20Cloud%20Models.md)
- [142 Client-side Virtualization](142%20Client-side%20Virtualization.md)
- [241 Cloud Characteristics](241%20Cloud%20Characteristics.md)

#study #professormesser #comptia #Aplus #virtualization #switch #router #softwaredefinednetworking #sdn 