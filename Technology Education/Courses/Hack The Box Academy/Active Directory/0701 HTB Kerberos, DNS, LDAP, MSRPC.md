# Active Directory Protocols

*Lightweight Directory Access Protocol* ( #LDAP) is the #Microsoft version of #Kerberos that is used in conjunction with #DNS and #MSRPC. **DNS is used for communication and authentication**, and **MSRPC is used for client-server applications**. 

#### Kerberos

#Kerberos is a ticket-based #stateless #authentication #protocol that verifies users by **mutually authenticating the client and server**. Communications for Kerberos occur on #port 88 for both #TCP and #UDP.

Each Domain Controller  ( #DC ) has a Kerberos Key Distribution Center ( #KDC) that **generates tickets when a user logs on**. The user sends a login request that contains the user's encrypted password. When this encrypted password is received ( #AS-REQ), it is decrypted and if it is correct, a *Ticket Granting Ticket* ( #TGT) is passed to the user. This TGT is encrypted with a #NTLM #hash and presented to a *Domain Controller's Ticket Granting Service* ( #TGS). Finally the TGS is presented to the application which will then grant access.

This may seem like a convoluted system, but it exists to **decouple user data and resources from the credentials supplied** to authorize the user.

##### Kerberos Process in Steps

1. User logs in and their **password is converted to NTLM hash that encrypts the TGT** ticket, effectively decoupling the credentials from any resources.
2. The KDC inspects the #AS-REQ service request and transmits a TGT to the user if correct.
3. The user client **provides the TGT to the Domain Controller** requesting the TGS-REQ response. This step is used to generate a TGS ticket.
4. The generated **TGS is encrypted via NTLM hash** of the service or computer is transmitted to the user as TGS_REP.
5. The **client shows it's TGS to the service** or computer, which is then authenticated for access to the given resource, or AP_REQ.

Steps 1-4 are communications between the client and the Key Distribution Center ( #KDC).

Step 5 is between the #client and the #database server, granting access to the resource.

Domain Controllers can be **found by performing #nmap scans** of Kerberos port 88.

### DNS

Domain Name Service ( #DNS) is used by the *Active Directory Domain Services* ( #ADDS) to **allow clients within the domain to locate Domain Controllers** ( #DC) and for those domain **controllers to host directory services** and communicate to other DCs. 

*Service Records* ( #SRV) allow clients within the Active Domain to **locate services and edit the DNS** #database. Hostname and Domain name DNS lookups can be used locally or across the internet. **Clients are able to query the SRV to find a specific domain controller or service**.

### LDAP

*Lightweight Directory Access Protocol* ( #LDAP) is an #open-source and #cross-platform authentication protocol that is used by a variety of directory services. **LDAP uses #port 389, and LDAP over #SSL ( #LDAPS) uses #port 636**. 

LDAP is the #protocol that **facilitates communication between the #network and the active directory**, allowing for sharing of account and security information. **To initiate an LDAP session, the client connects to a Directory System Agent**, or LDAP server. Domain Controllers in the Active Domain listen for LDAP requests.

You can think of an Active Directory as a server that uses the LDAP protocol.

Simple Authentication means that credentials have been submitted, creating a #BIND request for authentication on the LDAP server.

#SASL Authentication uses the *Simple Authentication and Security Layer* ( #SASL) framework in conjunction with other authentication services to **bind the LDAP server to that authentication service**. LDAP will communicate with the authorization service to initiate challenge/response handshakes.

It is worth noting that ***LDAP messages are cleartext by default***, so a #MITM attack can detect these messages if you choose not to encrypt them. 

### MSRPC

*Microsoft Remote Procedure Call* ( #MSRPC / #RPC) **facilitates communications between client-server applications** and for access to Active Directory using one of four RPC interfaces.

1. #lsarpc refers to the RPC calls for Local Security Authority ( #LSA ) to **manage local policies, audit policies, and manage domain security** policies. 
2. #netlogon is a #Windows #process that runs in the background, **authenticating users and services** within the domain.
3. #samr refers to *Remote SAM* and **manages the domain database, users, groups, admins, and computers**. Attackers that gain entry to Remote SAM  can collect information about the domain and objects within that domain. An app like #Bloodhound can track and route these vulnerabilities or attack paths. ***You should change your windows registry key so that only your admins have access to remote SAM***.
4. #drsuapi is the #API that initializes *Directory Replication Service* ( #DRS) Remote Protocol to **manage replication tasks across many domain controllers**. ***This is a problem as an attacker will be able to copy your Active Directory Database with all account hashes and cleartext password information***.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Kerberos, DNS, LDAP, MSRPC](https://academy.hackthebox.com/module/74/section/701 "HTB Kerberos, DNS, LDAP, MSRPC module")
- [021 Active Directory](021%20Active%20Directory.md)
- [126 DNS Configuration](126%20DNS%20Configuration.md)
- [9999 Active Directory Bonus Content](9999%20Active%20Directory%20Bonus%20Content.md)