# Host and Port Scanning

After our initial step of determining if a host is "alive", we will want to further enumerate information from this host. The type of **information we seek** at this stage is detailed below:

- Open Ports
- Active Services
- Service Versions
- Service Details
- Operating System Information
#### States

Any of these results can be assigned one of the following **six states**:

- Open indicates the #port was connected to via #TCP, #UDP, or #SCTP.
- Closed indicates that the port returned an #RST flag and is not open.
- Filtered indicates that there was no response or an error code. A #firewall is likely present.
- Unfiltered means the port is only accessible via TCP-ACK and whether it is open or closed is undetermined.
- open|filtered indicates no response and that a firewall or other filter is present.
- closed|filtered occurs during an IP ID idle scan indicating that nmap was unable to determine if a firewall or filter was present.

#### Open TCP Ports

When we scan with nmap, the default method is to scan the top 1,024 TCP ports via SYN scan. If we do not have root privileges then a TCP scan will be the default. The default parameters for nmap will be used unless otherwise specified.

Methods of designating ports for scanning are as follows:

- -p 22, 69, 400, 500, 666 would scan each individual port specified and ignore all others.
- -p 22-400 would scan the all ports within this given range.
- --top-ports=10 would scan the top ten ports in the nmap database.
- -p- would scan every port possible, which is a very long process.
- -F would designate a fast scan of the top 100 ports in the nmap database.

We can scan the top 10 ports with the following commands:

>sudo nmap 10.10.2.28 --top-ports=10

#### Packet Tracing

It is useful to use packet tracing to determine the pathing of the transmissions between our client and the host. We can see the requests and responses we are sending and receiving with detailed information. 

We can use the following command to do packet tracing on our target on port 21 using TCP:

>sudo nmap 10.10.2.28 -p 21 --packet-trace -Pn -n --disable-arp-ping

- -n disables #DNS resolution

#### Requests

Request headers will display a few lines that can be described in the following way:

- SENT indicates this packet was sent from our nmap tool.
- TCP indicates the protocol used.
- S indicates we sent a SYN packet.
- ttl=56 id=57322 seq= win= mss 1460 are header parameters.

#### Responses

Response Headers are similar to Response headers and contain the following:

- RCVD indicates the packet that was received from the target host.
- TCP indicates the protocol used.
- RA indicates either an #RST or #ACK flag returned by the target host.
- ttl=64 id=0 iplen=40 seq=0 win=0 represents the header parameters.

#### Connect Scan

Nmap provides a TCP Connect Scan via the -sT flag that initiates a scan that employs the TCP three-way handshake to determine the state of the target host. The target will receive a SYN packet and respond with either a SYN-ACK or RST packet inidcating the state of the port.

The Connect scan is the most discreet method for host discovery. All packet transmissions will be resolved meaning that there will be no evidence of our presence in the target network. This means that there is a lessened likelihood that we will be detected by a #firewall, Intrusion Detection System ( #IDS), or an Intrusion Prevention System ( #IPS). The scan is slower than others because it waits for a response for each individual transmission before initiating the next transmission.

We can perform a connect scan on port 443 with the following command:

>sudo nmap 10.10.2.28 -p 443 --packet-trace --disable-arp-ping -Pn -n --reason -sT

#### Filtered Ports

Filtered ports are a result of firewall protections, dropped packets, or rejected packets. We can assign a finite number of attempts using the option --max-retries to set a limit. We can then use packet tracing to see the state of our requests and further determine what is happening on the target host.

We can use the following commands to do packet tracing on port 139 and port 445:

>sudo nmap 10.10.2.28 -p 139 --packet-trace -n --disable-arp-ping -Pn

>sudo nmap 10.10.2.28 -p 445 --packet-trace -n --disable-arp-ping -Pn

#### UDP Port Discovery

User Datagram Protocol ( #UDP) is often neglected by security managers and may be susceptible to exploitation. Enumerating with UDP is not the best option due to UDPs stateless nature. We have no way of knowing if any packets we send to the target host have been received. The timeout for UDP is also much longer than TCP, meaning that all of our UDP based scans will take much longer and provide less information.

Nmap will send empty datagrams to the target and subsequently we will have no way of knowing if they were received unless the network is configured to respond to UDP transmissions. 

We can use the following command to perform a UDP scan with nmap:

>sudo nmap 10.10.2.28 -sU -Pn -n --disable-arp-ping --packet-trace -p 137 --reason

- -sU indicates that we are performing a UDP scan of the target host.

If we receive error code 3 in our response, this means the port is closed.

The following command is a UDP scan on port 100:

>sudo nmap 10.10.2.28 -sU -Pn -n --disable-arp-ping --packet-trace -p 100 --reason

#### Version Scan

A commonly used option with nmap is the version scan flag -sV. This scans the target ports and when any services are discovered on open ports, we will yield detailed information about the service name and version.

We can perform a version scan on port 445 with the following command:

>sudo nmap 10.10.2.28 -Pn -n --disable-arp-ping --packet-trace -p 445 --reason -sV

