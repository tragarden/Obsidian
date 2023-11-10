# Introduction to Internet Protocol (IP) 2.1

#### IP Addresses

You can think of an #IP as the license plate on a truck that is driving across the road-like networks of the internet, *crossing ethernet, DSL, and cable systems.* 

Boxes within the truck are akin to the packets of data that are sent via TCP and UDP in coordination with the IP address.   The main role of the IP is to get the ‘boxes’ delivered to a specific place in one group.

Each ‘box’ or #packet is stored within each other in a process called #encapsulation.  IP > Packets > Data

##### Payloads

Each time data is submitted, this is called a #payload.  When data is sent via packets as a payload, **this information is sandwiched between a data header and data trailer.**  This is information at the beginning and end of a payload that tells the recipient what to expect and a request for information we are seeking. 

The data within the IP payload may include a smaller payload like TCP payloads or HTTP payloads.  These *encapsulated payloads will have their own header and trailer* while being contained within the IP payload and headers.  This means that IP contains TCP which contains HTTP in this scenario. 

#### Protocols

*TCP and UDP are encapsulated by the IP protocol* and are common protocols used to move data securely from place to place.  They are active on #OSI Layer 4: the Transport Layer.  These protocols utilize multiplexing so that many different applications can be used at the same time. 

##### TCP

*Transmission Control Protocol* ( #TCP) is a connection-oriented protocol and is known for reliable delivery.  It uses a formal connection for setup and closure and is considered reliable because it offers recovery from errors and can manage out-of-order transmissions and re-transmitted data. 

*Flow Control* is available as well, allowing for receivers of TCP data to throttle the amount of data transmitted.

##### UDP

*User Datagram Protocol* ( #UDP) does not require a formal connection and is *known as the ‘unreliable’ protocol as there is no error recovery or reordering of unsorted data.*  There is *no flow control* either.  This protocol is most **associated with real-time communication.**  UDP is advantageous in scenarios such as a phone call because there is no way to rewind the call data to a previous point in the conversation.  The ***data will be sent across the network without confirmation of receiving it.*** 

##### Connection-Oriented

*Connection-oriented protocols* required a confirmation of receipt.  

*Hyper-text Transfer Protocol Secure* ( #HTTPS) and *Secure Shell* ( #SSH) are examples of these types of protocols.  These use TCP exclusively and will resend the data until the receipt is validated from an authenticated source. 

#### DHCP

*Dynamic Host Configuration Protocol* ( #DHCP) and *Trivial File Transfer Protocol* ( #TFTP) are **connectionless protocols** that are known for using UDP.  If it is determined that sent data has not been received, it is the role of DHCP to correct that issue, not the role of UDP. 

#### Ports

*Port number* determines which application at a designated IP will receive a packet of data.  IPv4 sockets manage IP addresses, protocols used, and respective port numbers.

*Non-ephemeral ports* are ***permanent*** #port numbers 0 – 1023 which are usually found on a server or service.

*Ephemeral ports* are ***temporarily available ports***, numbered 1024 – 65,535 and are *determined in real-time by the client* submitting data. 

**Port 80 is commonly associated with HTTP.**

**Port 443 is commonly associated with HTTPS.**

**Most servers use non-ephemeral port numbers,** but there are cases where they use dynamic ports that often change. 

***Ports are used for communication, NOT for security purposes.***


### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/introduction-to-ip-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [226 DHCP Configuration](226%20DHCP%20Configuration.md)
- [125 IPv4 and IPv6](125%20IPv4%20and%20IPv6.md)
- [225 Assigning IP Addresses](225%20Assigning%20IP%20Addresses.md)
- [127 Internet Connection Types](127%20Internet%20Connection%20Types.md)

#study #professormesser #comptia #Aplus 