# Service Enumeration with Nmap

Discovering and enumerating services on a target host gives us valuable information related to finding vulnerabilities. If we can determine the version number of an active service, we can search the web for vulnerabilities and their related exploits. 

It is common to **begin with an ordinary #port scan** to see what ports are available **before scanning them for their #service versions**. Once we have enumerated the open ports, we can **negate #port scanning on our next scan** and ***selectively scan each of the known open ports*** for version details.

Pressing the *space bar* or *up arrow* during an #Nmap scan will display the current progress and estimated time remaining to complete the scan. 

We can **perform a service version scan** by using the -sV flag with the following command:

>sudo nmap 10.10.2.28 -p- -sV

If we want **more granular details** provided with our results in 5 second intervals, we can use the following command:

>sudo nmap 10.10.2.28 -p- -sV --stats-every=5s

If we want **more detailed output**, we can used the *verbose* flag -v or -vv with the following command:

>sudo nmap 10.10.2.28 -p- -sV -v

### Banner Grabbing

When nmap provides us with information about a #service and #port, it does so by **looking at the #banner of the open port** before printing them in the output. If the banners do not identify the versions of the services this way, **nmap will match the signatures of these services with data from a #database**. This is a ***very time consuming*** modification to our nmap scan.

We can use the following command to perform a scan with detailed information:

>sudo nmap 10.10.2.28 -p- -sV -Pn -n --disable-arp-ping --packet-trace

The results of this scan should provide a detailed output because it is able to grab service banners after a successful three-way handshake.

#### Banner Tools

Since nmap can be limited in the amount of information it can grab from banners, we can **examine the banners further** with tools like #TCPdump and #netcat. 

##### TCPdump

We can use #Tcpdump to **examine banners in greater detail** with the following command:

>sudo tcpdump -i eth0 host 10.10.14.2 and 10.10.2.28

##### Netcat

We can use #netcat to **examine banners in greater detail** with the following command:

>nc -nv 10.10.2.28 25

##### Intercepted Banners

When we examine the banners we can see the three responses needed to complete the three-way handshake:

- #SYN
- #SYN-ACK
- #ACK

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Nmap Service Enumeration](https://academy.hackthebox.com/module/19/section/103 'HTB academy sevice enumertaion with nmap')
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)