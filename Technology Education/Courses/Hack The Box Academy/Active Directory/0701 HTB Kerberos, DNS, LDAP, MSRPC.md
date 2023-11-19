# Active Directory Protocols

Lightweight Directory Access Protocol ( #LDAP) is the #Microsoft version of Kerberos that is used in conjunction with #DNS and #MSRPC. DNS is used for communication and authentication, ad MSRPC is used for client-server applications. 

#### Kerberos

#Kerberos is a ticket-based #stateless #authentication #protocol that verifies users by mutually authenticating the client and server. Communications for Kerberos occur on #port 88 for both #TCP and #UDP.

Each Domain Controller  ( #DC ) has a Kerberos Key Distribution Center ( #KDC) that generates tickets when a user logs on. The user sends a login request that contains the user's encrypted password. When this encrypted password is received ( #AS-REQ), it is decrypted and if it is correct, a Ticket Granting Ticket ( #TGT) is passed to the user. This TGT is encrypted with a #NTLM #hash and presented to a Domain Controller's Ticket Granting Service ( #TGS). Finally the TGS is presented to the application which will then grant access.

This may seem like a convoluted system, but it exists to decouple user data and resources from the credentials supplied to authorize the user.

##### Kerberos Process in Steps

1. User logs in and their password is converted to NTLM hash that encrypts the TGT ticket, effectively decoupling the credentials from any resources.
2. The KDC inspects the AS-REQ service request and transmits a TGT to the user if correct.
3. The user client provides the TGT to the Domain Controller requesting the TGS-REQ response. This step is used to generate a TGS ticket.
4. The generated TGS is encrypted via NTLM hash of the service or computer is transmitted to the user as TGS_REP.
5. The client shows it's TGS to the service or computer, which is then authenticated for access to the given resource, or AP_REQ.

Steps 1-4 are communications between the client and the Key Distribution Center ( #KDC).
Step 5 is between the #client and the #database server, granting access to the resource.

Domain Controllers can be found by performing #nmap scans of Kerberos port 88.

### DNS

Domain Name Service ( #DNS) is used by the Active Directory Domain Services ( #ADDS) to allow clients within the domain to locate Domain Controllers ( #DC) and for those domain controllers to host directory services and communicate to other DCs. 

Service Records ( #SRV) allow clients within the Active Domain to locate services and edit the DNS #database. Hostname and Domain name DNS lookups can be used locally or across the internet. Clients are able to query the SRV to find a specific domain controller or service.

### LDAP

Lightweight Directory Access Protocol ( #LDAP)