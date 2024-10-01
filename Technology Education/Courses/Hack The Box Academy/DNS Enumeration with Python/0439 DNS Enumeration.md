# DNS Enumeration

There are a few key pieces of information that we would want to enumerate from a DNS:

- DNS Records
- Subdomains
- Hosts
- DNS Security

There are several techniques that can be used to accomplish this:

- #OSINT 
- Certificate Transparency
- Zone Transfer

### OSINT

Open-source Intelligence ( #OSINT)  is a collection of information that is collected from publicly available sources. This is common information that is available on most search engines. [Google Dorks](https://securitytrails.com/blog/google-hacking-techniques 'google search dorking and hacking techniques')is also known as Google hacking and can be used to find security gaps in configurations and code used by websites.

Other publicly available tools like [VirusTotal](https://www.virustotal.com/ 'virustotal web service'), [DNSdumpster](https://dnsdumpster.com/ 'DNSdumpster web service'), and [NetCraft](https://searchdns.netcraft.com/ 'netcraft web service')can also be used to gather information about a given domain.

### Certificate Transparency

Certificate Transparency ( #CT) contain all certificates issued by a Certificate Authority ( #CA) for a given domain. #SSL / #TLS certificates from servers include domain names, subdomain names, and email addresses associated with the public records. This can be used to understand a companies infrastructure and there are tools that output the CT logs for a given domain. The ctfr.py file can be used to filter the CT logs.

##### CTFR.py

Execute the ctfr.py file with the following command:

>python3 ctfr.py -d inlanefreight.com


### Zone Transfer

Zone transfer refers to when zones are exchanged or transferred between DNS servers and is also known by it's technical name of Asynchronous Full Transfer Zone ( #AXFR). Zone files are often maintained with multiple identical iterations across several name servers as DNS failure can result in severe consequences. 

Zone transfer monitors transfer of files and records and detects if the integrity of this data has been compromised. Many administrators do not fully understand the technical configuration of servers and troubleshooting, which can lead to errors and vulnerabilities. These problems can lead to additional misconfigurations which could endanger the entire infrastructure of the DNS environment allowing all content from all zones to be accessible to threat actors.

#### Perform a Zone Transfer

We can use the dig tool to perform a zone transfer with the following command:

>dig axfr inlanefreight.com \@10.129.2.67