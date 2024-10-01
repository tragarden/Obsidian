# DNS Structure

Domain Name Service ( #DNS) takes #FQDN information submitted to a client and looks this name up to retrieve the related #IP address.

DNS components are:

- Name servers
- Zones
- Domain names
- IP addresses

Within the name servers are zones or zone files. The zone file is a list of entries that correspond to domain names and hosts. These files exist on all systems using Linux or Windows, and this is called the 'hosts' file.

In the hack-the-box VMs, this is located within /etc/hosts.

If we examine the structure of an FQDN like \www.domain-A.com, we can see that it has a hierarchical structure when we look at the directory tree

![[DNS Diectory Tree Dark.png]]
![[DNS Domain Structure dark.png]]

### Structure Components

Each domain consists of two parts:
- Top-level Domain ( #TLD)
- Domain Name

DNS servers are categorized into four types:
- Recursive Resolvers ( DNS Recursor )
- Root Name Server
- TLD Name Server
- Authoritative Name Servers

### Recursive DNS Resolver

The recursive resolver is an intermediary between the client and server that receives the query from the client and either responds with cached data or sends the query to a root name server. If it queries the **root name server**, it will then pass the query to a **TLD name server** and finally to an **authoritative name server.**

Once the authoritative name server responds with an IP address, the recursive resolver passes this back to the client. The recursive resolver will cache the information it recieved from the queries allowing it to respond to future requests without querying the name servers.

### Root Name Server

There are 13 root name servers maintained by a non-profit organization named the Internet Corporation for Assigned Names and Numbers ( #ICANN). These servers have zone files containing all domain names and IP addresses for each TLD, and every recursive resolver knows these 13 servers. These 13 servers are on the domain root-servers.net and there are over 600 copies of them internationally.

You can run the following command to see these 13 servers named by letters a-m:

>dig ns root-servers.net | grep NS | sort -u

### TLD Name Server

Top Level Domain Name Servers manage domains that share a TLD and fall under the jurisdiction of the Internet Assigned Numbers Authority ( #IANA). In other words, every .net site is managed by a .net TLD name server. 

### Authoritative Name Server

The Authoritative Name Servers store the DNS records for domains and provide the IP addresses and entries for a website. This is the last stage of DNS domain name resolution.