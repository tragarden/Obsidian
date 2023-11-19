# Active Directory Objects

An #Object in Active Directory ( #AD) is any resource within a given Active Directory. This could include hosts, devices, users, folders, attributes, Organizational Units ( #OU), and Domain Controllers ( #DC).

### Objects

#### Users

A User #Object has as many as 800 attributes, a Security Identifier ( #SID), and a Global Unique Identifier ( #GUID ). These objects are known as Security Principals and are NOT container objects - this is known in Active Domain as a #Leaf object. If any user objects are accessed by an attacker they may forfeit control and resources and allow the attacker to enumerate the entire forest of domains. 

#### Contacts

A Contact Object is another #Leaf object that has a #GUID but lacks an #SID. These contain standard contact information for people outside of the domain and likely outside of the organization. 

#### Printers

A Printer Object is another #Leaf object that only has a #GUID. These objects apply to any printer within the domain and will have several attributes.

#### Computers

A Computer Object is another #Leaf object that is a Security Principal, meaning it has both a #GUID and an #SID. These objects are treated similarly to user objects and are equally vulnerable to attackers. These objects are created for any computer within the Active Domain. 

#### Shared Folders 

A Shared Folder Object is a pointer for a shared folder or a computer that contains one. Shared Folders are NOT Security Principals, so they only have a #GUID. If a user is not on the ACL for a shared folder, they cannot view or list its contents.

#### Groups

Group Objects are used to manage user privileges and access to resources. Groups are considered Container Objects and often include other objects, users, and devices, so they have both an #SID and a #GUID. Since new users added to a group inherit the privileges of the group, there is a common security vulnerability where a nested group is created and yields escalated rights to users that should not have them. This turns our nested group into a vector for attack. Tools like #Bloodhound can analyze your group hierarchies and identify any vulnerabilities that would allow for an attacker to gain access and escalate privileges. 

#### Organizational Units

Organizational Units ( #OU) are used to organize groups within the organization, which is slightly confusing since we already have Group Objects. These are used in conjunction with Group Objects to yield more granular control and to manage sub-groups within a group. This is used by administrators to issue rights to a specific user without including them in a specific group.

#### Domain

#Domain Objects are Container Objects that hold users and computers, while further organizing them into Group Objects and Organizational Units. Each domain has a unique #database and #Policy configurations. 

#### Domain Controllers

Domain Controllers ( #DC) enforce security policies and store security data for every object within the domain. DCs handle authentication and verification of user before granting access to resources on the domain.

#### Sites 

A #Site in Active Domains is a set of computers used to facilitate replication across the domain controllers.

#### Built-In

When an Active Directory Domain is created, it is assigned a built-in container that holds all the default groups for the new Active Directory Domain.

#### Foreign Security Principals

Foreign Security Principals ( #FSP) is used to represent a security principal when you are communicating between two separate forests. They are used to hold the #SID of an object from a foreign forest. Windows then uses this SID to resolve the name of the object via trust link. 