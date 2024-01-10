# Firewall and IDS/IPS Evasion


A #Firewall and *Intrusion Detection Systems* ( #IDS) are **the main obstacles for an #Nmap scan**. Luckily, nmap has many methods for overcoming these systems and successfully scanning a protected target host.

### Firewalls

A #Firewall is #software that **monitors inbound #network traffic and identifies unauthorized connection attempts** from external sources. Firewalls **evaluate each #packet that reaches the network and records whether they are allowed to pass or are otherwise ignored** or blocked.

### IDS/IPS

*Intrusion Detection Systems* ( #IDS) and *Intrusion Prevention Systems* ( #IPS) are #software that **employ pattern matching and signature identification to identify threats and defend against them**. If anomalies are detected, the systems will block the connections from the source of these unusual patterns. 
### Firewall Identification

When a #firewall detects a threatening #packet, it will **respond by rejecting the packet**. Sometimes they will drop a packet, but this can occur for other reasons as well. When we are able to observe this behavior, we can begin to determine what is rejecting or dropping the packets. **In the best case scenario they will be rejected and the target host will respond with an #RST flag containing #ICMP error codes** that we can use to identify defense measures.

Common error codes include:

- Net Unreachable
- Net Prohibited 
- Host Unreachable
- Host Prohibited
- Port Unreachable
- Proto Unreachable

We can **avoid having our packets rejected by changing the type of scan** we are performing. By default, #Nmap uses #SYN ( -sS) and *Connect* ( -sT) scans that are able to be detected by defense systems. If we choose to use the #TCP-ACK (-sA) scan we can **often evade defense software because this method send s #TCP packets with only #ACK flags**. This is useful because it **forces a defense system to respond with only an #ACK flag** which the firewall cannot differentiate between internal and external packet. 

We can perform each of these scans and observe how they are different with the following commands:

##### SYN Scan

>sudo nmap 10.10.2.28 -p 21,22,25 -sS -Pn -n --disable-arp-ping --packet-trace

##### ACK Scan

>sudo nmap 10.10.2.28 -p 21,22,25 -sA -Pn -n --disable-arp-ping --packet-trace

During the #SYN scan the target host will reply with #SYN-ACK flags. When we perform this same #enumeration technique using the #ACK scan, the #RST flag is returned in the #RCVD packets because we know that port 22 is open. Port 25 returns nothing, indicating that the packets were dropped.

### IDS / IPS Identification

#IDS and #IPS systems are **harder to bypass than a typical #firewall**. This is due to the systems actively monitoring #network traffic and **using pattern recognition to determine unusual behavior and end the connection when this is recognized**. If a pattern is recognized, this system will notify a system administrator in our worst-case scenario.  

An #IDS system will **monitor every connection between each host in the network**. 

#IPS systems are configured by administrators follow certain rules and **automate the prevention of specific types of attacks**.

Although these systems seem very similar, it is important to differentiate between them. ***You can think of an IPS as a complementary feature of the IDS***.

During penetration tests, it is common to use multiple *Virtual Private Servers* ( #VPS) to identify these systems on a target network. This means that if we are detected by an administrator, the #IP address of only one of our VPS machines will be blocked. ***BE AWARE THAT IF YOUR IP IS REPORTED BY AN ADMINISTRATOR, YOUR INTERNET SERVICE PROVIDER ( #ISP) WILL DEACTIVATE YOUR INTERNET.***

The #IDS system is a tool that the administrator uses to evaluate situations and determine what actions to take. **If an administrator blocks the IP of our VPS, we can simply confirm that an IDS is present and begin attacking in a more discreet way from our other available VPS**. Occasionally admins will block all connections based on regions or associated #subnet.

### Decoys

A #Decoy is a **false #IP address that we list before our real IP address in the header of the outbound packets**. This means when the target host receives the packet and decides it's a threat, the **first IP will be blocked leaving our real #IP (the second Ip in the header) unblocked**. We can assign multiple decoy IPs to our packet headers using the -D flag.

Try the following #SYN scan on #port 80 with 5 decoy IPs to observe how this works:

>sudo nmap 10.10.2.28 -p 80 -sS -Pn -n --disable-arp-ping --packet-trace -D RND:5

With this command we have successfully manipulated the "IP ID" portion of the #packet header we sent to the target host.

We can also use  the -S flag to implement a decoy #subnet value of our choosing.

We can test the #firewall with the following command:

>sudo nmap 10.10.2.28 -n -Pn -p 445 -O

Then we can assign a different source #IP of our choice with the following command:

>sudo nmap 10.10.2.28 -n -Pn -p 445 -O -S 10.10.2.200 -e tun0

- -O will **scan for the current operating system** ( #OS) 
- -S will perform the **scan with the associated false IP address** in the packet header
- -e tun0 instructs the **scan to occur on the specified interface**.

### DNS Proxy

#Nmap performs *reverse* #DNS ( #rDNS) resolution by default, which is quite literally the reverse process of standard DNS lookups. The DNS server will evaluate a given IP and **translate it into the human-readable #domain name**. DNS queries typically occur on #UDP port 53, but with the modern advent of #IPv6 and #DNSSEC it is increasingly common to see this occur on #TCP port 53.

With Nmap, we can use the *--dns-server* option to indicate a DNS server of our choosing. We can also indicate a desired port for these scans with the *--source-port* option. If the network administrator is prioritizing firewall protections against this port instead of using IPS / IDS, we can likely pass our packets through this port.

We can perform a #SYN scan against a *filtered* port with the following command:

>sudo nmap 10.10.2.28 -p 50000 -sS -Pn -n --disable-arp-ping --packet-trace

Now we can perform a comparison #SYN scan from a **specified DNS port 53** with the following command:

>sudo nmap 10.10.2.28 -p 50000 -sS -Pn -n --disable-arp-ping --packet-trace --source-port 53

### Connect to Filtered Port

We can now use #netcat to listen and connect to the #port we accessed with the previous commands:

>ncat -nv --source-port 53 10.10.2.28 50000

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Evading Firewall and IDS](https://academy.hackthebox.com/module/19/section/106 'HTB academy evading firewalls and IDS')
- [025 Windows Firewall](025%20Windows%20Firewall.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)