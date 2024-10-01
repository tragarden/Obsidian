# Records and Queries

DNS Records are instructions from authoritative DNS servers written in DNS syntax to direct the servers querying them.

Common DNS records include:


| Record | Record Type                         |
| ------ | ----------------------------------- |
| A      | IPv4                                |
| AAAA   | IPv6                                |
| CNAME  | Canonical Name                      |
| HINFO  | Host Information                    |
| ISDN   | Integrated Services Digital Network |
| MX     | Mail Exchanger                      |
| NS     | Name Server                         |
| PTR    | Reverse-lookup Pointer              |
| SOA    | Start of Authority                  |
| TXT    | Text                                |

### Tools

Tools like dig and nslookup are commonly used to send queries to DNS servers.

### NS Servers

During this course we will be automating the enumeration process for zone transfers on misconfigured DNS servers to evaluate them for vulnerabilities. When NS servers are enumerated, we can determine if zone transfer is possible and retrieve information about it's subdomains.

Name Server Records indicate which DNS server is the Authoritative one via NS records that indicate the primary and secondary servers for a given domain. Once we know our target domain, we need to know which servers handle this domain using the dig tool.

Perform an NS query using the dig tool via the following command:

>dig NS inlanefreight.com

Perform and SOA query using the dig tool with the following command:

>dig SOA inlanefreight.com

Use nslookup to perform an SPF query:

>nslookup -type=SPF inlanefreight.com

Use nslookup to perform a DMARC query:

>nslookup -type=txt \_dmarc.inlanefreight.com