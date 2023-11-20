# User and Machine Accounts

Active Directory ( #AD) accounts serve different purposes at different levels of privilege. Within an organization, you may find that there are more user accounts than there are members of the organization. This could be because certain users have more than one user account which is used for different purposes. An additional reason for extra accounts is due to the remaining accounts of employees that are no longer employed with the organization. These accounts are often stored within their own Operational Units ( #OU) like 'FORMER EMPLOYEES' for purposes of company records and audits.

#### User Accounts

There are a range of User accounts, ranging from read-only temporary accounts, to the Enterprise #Admin account that has control over any #object within a #domain. 

User Accounts offer the greatest surface for attack vectors because accounts are often compromised by password sharing, weak credentials, unauthorized software installs, and administrative error in misconfiguration of privileges. 

#### Local Accounts

#Local Accounts are considered #Security Principals and will have both an #SID and a #GUID. These accounts are located on the device itself and is not a user account on the #network. There are default local accounts created on any Windows system:

- #Administrator is the first default account created when you install the #OS and has the #SID 'S-1-5-domain-500'. This is a powerful account that has control over nearly all resources. While this account can be renamed and disabled, it cannot be deleted or locked.
- #Guest accounts are used to temporarily log onto the machine with limited access rights. It may not have a password and is disabled by default to eliminate a possible vector for attack.
- #SYSTEM or NT AUTHORITY\\SYSTEM account is a service account that is similar to the #root account on #linux. This account runs many of the services and processes necessary for windows to work correctly. This is the highest priority account on a Windows machine and it will not be displayed as a user in User Manager and cannot be added to groups. 
- Network Service is a local account used by Service Control Manager ( #SCM ) and presents credentials to remote services.
- Local Service is also used by the Service Control Manager ( #SCM ) to run Windows services with minimal privileges. 

#### Domain Users

#Domain User Accounts are able to log into any #host within the #domain. These accounts are granted permissions from the domain itself, differing from local accounts. It is important to note the #KRBTGT account that is fundamental to the structure of the Active Domain. The Key Distribution service uses this account to access resources and authenticate users, which means it is a desirable target for attackers looking to escalate privileges. Domain users are susceptible to Golden Ticket type attacks.

#### User Naming Attributes

#UserPrincipalName ( #UPN) is the logon name for a given user, which uses their email as the default address.

#ObjectGUID is the identifier for the user - this name remains unique and is never reused even if the user account is deleted.

#SAMAccountName is used for older versions of Windows.

#objectSID is the user Security Identifier ( #SID).

#sIDHistory is mainly used for domain migration purposes and contains all previous SIDs for a given user object. When you migrate to a new domain, the old SID is added to sIDHistory and the new SID will become the objectSID.

### Joined and Non-Joined

Domain Joined hosts receive configurations and rights through the domain group policy which facilitates greater ease of resource sharing, allowing a user to use any host within the domain to access the resources within the domain. 

Non-Domain Joined hosts are able to share within their #LAN but they cannot easily access the resources on a domain like a Joined Host is able to do. 