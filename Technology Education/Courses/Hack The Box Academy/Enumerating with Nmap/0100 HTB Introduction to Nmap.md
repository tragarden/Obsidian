# Introduction to Nmap

Network Mapper ( #Nmap) is a free and open-source ( #FOSS) network analysis tool used to scan networks to determine ports in use and the name and version of services running on each port. Nmap is written in C, C++, Python, and Lua.

### Use Cases

Nmap is one of the most frequently used tools for any person working in cybersecurity. There are many applications for this tool, including but not limited to:

- Security Auditing
- Network Auditing
- Penetration Testing
- Checking Firewall configurations
- Checking Intrusion Detection Systems ( #IDS)
- Determining connection types
- Network mapping
- Response Analysis
- Determining open ports
- Identifying active services
- Determining operating systems
- Vulnerability Assessment

#### Nmap Design

There are five scan types available within Nmap:

- Host Discovery
- Port Scanning
- Service Detection 
- Operating System ( #OS) Detection
- Nmap Scripting Engine

#### Syntax

>nmap \<scan type> \<options> \<target host>

#### Techniques

We can see all of the techniques available within Nmap with the following command:

>nmap --help

Here we can see all of the techniques represented by their associated option flag. We implement these flags in the the previously mentioned syntax pattern to execute that scan type.

#### TCP-SYN 

The #TCP-SYN scan is represented by the -sS flag and is used by default unless otherwise specified by the user. This scans thousands of ports per second by sending a #SYN #packet to the scanned port, actively avoiding the three-way handshake and never establishing the full #TCP connection.

If the target host in our scan responds with a #SYN-ACK packet, nmap will describe the #port as open. 

If the target host responds with an #RST flag, nmap will describe the port as closed.

If no packet is returned by the host, nmap will describe this port as filtered. This response often indicates the presence of a firewall.

We can execute a #TCP-SYN scan with the following command:

>sudo nmap -sS localhost

The results will be provided in a table format similar to the following:

| Port Number | Status | Service |
| ----------- | ------ | ------- |
| 22/tcp      | open   | ssh     |
| 80/tcp            | open       | http        |
| 5432/tcp            | open       | postgresql        |
| 5901            | open       | vnc-1        |
