# DNS Security

DNS vulnerabilities are known and this is often addressed with dedicated servers, scanning, and vulnerability assessments. DNS servers are now being recognized as an active line of defense. The useful position of DNS servers being fundamental to every network connection allows them to be a centralized control point for analyzing requests.

### Threat Intelligence

DNS Threat Intelligence can be integrated with open-source applications and analytics software like Endpoint Detection and Response ( #EDR) and Security Information and Event Management ( #SIEM) tools. 

Additionally DNS Security Services coordinate by sharing Indicators of Compromise ( #IOC) and Indicators of Attack ( #IOA) along with firewall data, network proxies, endpoint security, Network Access Control ( #NAC), and vulnerability scanners.

### DNSSEC

Domain Name System Security Extensions ( #DNSSEC) is used to secure DNS servers by ensuring authenticity and integrity of data by issuing digital certificates to records. This is done via private keys, and at times a Resource Record may be signed multiple times with several private keys.  

#### Private Keys

A DNS server will sign it's sent resource records using it's only private key. Each zone has it's unique zone key which consists of a private and public key. DNSSEC indicates a new resource record type with #RRSIG that contains the signature for the record and a specific validity period with start and end dates.

#### Public Keys

The public key is used to verify signatures of the data recipients. This key must be supported by the DNS provider and the requesting client via the DNS zone public key.