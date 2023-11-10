# DNS Configuration

### DNS

*Domain Name System* ( #DNS) **translates human language into IP addresses**.  This system is **hierarchical** and uses a **distributed #database** that consists of many DNS servers, and **13 root clusters consisting of 1000+ servers**. There are hundreds of generic ***top-level domains*** such as .com, .org, .net., and there are 275 top-level domains related to country codes.  The commands ‘**dig**’ and ‘**nslookup**’ can be used in your #OS’ #terminal to learn more about the DNS interactions from your own device. 

DNS configurations are usually **saved to a text file**, and will contain the *Start of Authority* record, *Mail Exchanger* records, *canonical (#alias) names*, and IP addresses.  These can also be **saved to a web-based front end** instead of the simple text file.

### Record Types

*Resource Records* ( #RR) is a **list of domain name services in the database** that manages over 30 types of records, including #IP addresses, certificates, host alias names, and more.  These are critical configurations that must be tested and backed up.

*Address Records* ( #A or #AAAA) **defines the host address and contains data about (A) #IPv4** addresses.  In the case of #IPv6, AAAA records will reference these IPs.

*Mail Exchanger record* ( #MX) **records data related to email servers** and will be held **within an (A) type** record based in #IPv4. 

#Time-to-Live ( #TTL) is the allocated amount of time that a DNS server will remember a piece of data.

Text records based on *filetype .txt* are important and **contain public information about your server**.  It was originally intended as an informal presentation of public data, but eventually grew to serve further purposes.  It can be used to verify the user, and ***if you have access to the DNS server, you must be the administrator***.  They are **commonly used for #email security**, using external email servers to validate inbound information from the DNS. 

*Sender Policy Framework* ( #SPF) records are a protocol that **contains a list of all the servers authorized to send emails for the given domain**.   This is used to **verify the authenticity of a host, preventing mail spoofing** and making sure the information received is sent from the true host and not a phony or interceptor.  You can add this SPF data to a .txt file to configure settings for your DNS. (Basically, verifies the signature on the email from the host)

*Domain Keys Identified Mail* ( #DKIM) is a sort of digital **signature on a domain’s outgoing mail that is validated** by mail servers.  The ***public key for DKIM is found in the DKIM TXT record***. (Basically, signs the email outbound from the host to provide verification for authentication.)

*Domain-based Message and Conformance* ( #DMARC) **handles verification failures and spoof attempts and reports them** to the proper authority.  DMARC is used to decide what happens to invalid emails: send to spam, delete, reject, or otherwise.  Compliance reports can also be sent to the email administrator through this system.  DMARC can be added to your records via the .txt file as well.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/dns-configuration-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [016 Windows IP Address Configuration](016%20Windows%20IP%20Address%20Configuration.md)
- [124 Network Services](124%20Network%20Services.md)
- [125 IPv4 and IPv6](125%20IPv4%20and%20IPv6.md)
- [225 Assigning IP Addresses](225%20Assigning%20IP%20Addresses.md)

#study #professormesser #comptia #Aplus #txt #domain #email 