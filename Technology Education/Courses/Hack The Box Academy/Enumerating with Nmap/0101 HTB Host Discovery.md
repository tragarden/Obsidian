# Host Discovery

The first phase of enumeration with #nmap is detecting any available hosts with an #ICMP echo request, also known as a #ping. This is a common method used for host discovery that has low impact on the target network, although a properly configured #firewall will likely block these pings.

#### Storing Results

It is advised that you save each scan result with appropriate labeling for comparison of results and later documentation. This will allow us to review all of the scans we completed and old system states.

### Scan Range

We can provide a #CIDR range to scan a specific set of #IP addresses with the following command:

>sudo nmap 10.10.2.0/24 -sn -oA tnet | grep for | cut -d" " -f5

- 10.10.2.0/24 represents the targeted range of IPs
- -sn is a flag used to disable port scanning
- -oA tnet stores the data in all formats that begin with 'tnet'

#### Scan IP List

Sometimes during a test, our client will provide us with a list of IP addresses in their network. We can import this list into nmap instead of manually designating the addresses with the CIDR list.

If we created a file with the IP addresses in question named hosts.lst, we can use the following commands to view the list and implement it into our scan:

>cat hosts.lst

>sudo nmap -sn -oA tnet -iL hosts.lst | grep for | cut -d" " -f5

- -iL performs the scan against the targets defined in hosts.lst


#### Scanning Multiple IPs

We can also specify the IPs we want to attack without using the range methods above using the following command:

>sudo nmap -sn -oA tnet 10.129.2.18 10.129.2.19 10.129.2.20| grep for | cut -d" " -f5

We can also designate a range of IPs using the last octet in the address given like the following:

>sudo nmap -sn -oA tnet 10.129.2.18-20| grep for | cut -d" " -f5

#### Scanning Single IP

Most often we will use the single scan case with the following command:

>sudo nmap 10.129.2.18 -sn -oA host -PE --packet-trace

- -PE will use ICMP echo requests 
- --packet-trace will show all sent and received packets
- -oA host stores the results of all formates beginning with 'host'

We can further determine if nmap has designated our host as 'alive' with the --reason option:

>sudo nmap 10.129.2.18 -sn -oA host -PE --reason

- --reason details why a specific result was presented

Nmap is able to discover hosts using #ARP requests and replies. If we would prefer to use only ICMP echo requests, we can disable ARP pinging with the following option:

- --diable-arp-ping

