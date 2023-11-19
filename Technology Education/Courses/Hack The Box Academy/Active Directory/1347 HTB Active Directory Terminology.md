# Active Directory Terminology

There are many terms related to Active Directory that we must be familiar with in order to fully understand how these systems work.

### Terminology

#### Object

An #Object is any resource located within the Active Directory ( #AD).

#### Attributes

Attributes define the characteristics of any object within the active directory. Every attribute has an associated #LDAP name that can be used during queries. A router would have attributes such as default gateway, #MAC address, and hostname. 

#### Schema

The #Schema for the AD defines what objects are permitted within the AD and what attributes are associated with these objects. When we use a class to create an object, this is known as instantiation and the resulting object produced from this class is known as an #instance of that #class.

#### Domain

A #Domain is a logically created group of objects that are associated, such as all laptops for lawyers in a firm or all devices in a city. 

#### Forest, Tree, Leaf, Container

A #Forest is the containing domain for all other domains within that network. All trees for all domains within the Active Directory are within a single forest.

A #Tree is a subdivision of the forest that contains several Active Directory domains that all stem from the same root domain.

A #Container is an #object that holds other objects.

A #Leaf are at the very end of the hierarchy and do not contain other objects.

#### Global Unique Identifier

A Global Unique Identifier ( #GUID) is a 128-bit identifier that is assigned to every object within the Active Directory. #ObjectGUID is the attribute that stores the GUID for each object, user, and group. It is often useful to search through Active Directory via GUID before searching for other attributes as once a GUID is assigned, it never changes.

#### Security Principals

Security Principals refer to anything that requires authentication within an #OS. Within Active Directory, these principals are objects of the domain that can access other objects in the domain. Security Principals are managed by the Security Accounts Manager ( #SAM).

##### Security Identifier

The Security Identifier ( #SID) is a unique ID associated with a security principal or group. When the object is created, it will be assigned an SID by the #domain controller. Access tokens are granted when a given SID logs onto the domain. Identifying objects based on their SID can be useful when it is for a default object that is universally assigned.

#### Domain Component

#DC represents domain component.

### Distinguished Names

A Distinguished Name ( #DN) is a full description of all of the attributes associated with an object. This full path name is described using several attributes such as common name, operational unit, and domain.

A Relative Distinguished Name ( #RDN) can be used when there is a unique attribute present in the Distinguished Name of an object. For example, if an attribute like commonName: ron.ronronron is unique and this common name attribute is not assigned to any other object, you can use ron.ronronron as a Relative Distinguished name. 

Flexible Single Master Operation ( #FSMO) roles are means of bypassing authorization and authentication for Domain Controllers ( #DC ). There are five roles:

1. One ***Schema Master*** for each forest.
2. One ***Domain Naming*** Master for each forest.
3. One ***Relative ID*** ( #RID ) Master per domain.
4. One ***Primary Domain Controller*** ( #PDC) per domain.
5. One ***Infrastructure Master*** per domain. 


#sAMAccountName is the name of the logged in user.

#userPrincipalName is a combination of the user account name and the domain name.

A Global Catalog ( #GC) is the master catalog of all objects within the forest domain. This is used for authentication and for searching through all objects and attributes contained within the forest.

Read-Only Domain Controller ( #RODC) is a #database for the active directory that is read-only that also contains a read-only #DNS server. No passwords are stored on this controller and no changes are pushed from this database.

#Replication is applied to Active Domain objects when they are moved between domain controllers. The Knowledge Consistency Checker ( #KCC) #service forms connection objects between domain controllers to manage this replication.

Service Principal Name ( #SPN) identifies services and is used by #Kerberos authentication to find the association of a logon with the instance of a service. 

Group Policy Objects ( #GPO) are virtualized policies containing settings for files. Each GPO has it's own #GUID and can be applied to users and groups, as well as Operational Units ( #OU ).

Access Control Lists ( #ACL) contain any Access Control Entities ( #ACE) applied to an #object.

Access Control Entities ( #ACE ) identifies a user account, group, or logon session ( #trustees) and a list of their access privileges. 

Discretionary Access Control Lists ( #DACL) contain lists of ACEs and the access rights associated with security principals. The DACL will analyze a list of ACEs and determine if all entities within this list have access or not. If all entities have access permissions, the whole list is granted access.

System Access Control Lists ( #SACL) is a log of access attempts.

Fully Qualified Domain Name ( #FQDN) is the full name for a host which is composed of both the hostname and domain name. FQDNs can be used locally within Active Directories, like searching for file File1 on the domain MyFiles.LOCAL: should look something like File1.MyFiles.LOCAL. 


A #Tombstone is a container for objects that have been deleted from the Active Domain. Each Tombstone has an assigned lifetime, which is an allotted amount of time that the object can remain before it is permanently deleted.

The AD Recycle Bin was created to serve as a staging area for deleted objects before they are assigned a tombstone designation. This allows users to access objects in the recycle bin and reimplement or restore them to previous states.

#SYSVOL is a folder that contains policies and scripts. All of the contents of the SYSVOL folder are replicated to teach Domain Controller in the domain via the File Replication Services ( #FRS).

#AdminSDHolder  is an object that manages ACLs via the #SDProp process running hourly on the PDC Emulator Domain Controller. It verifies that the correct ACL is applied to each protected group on the domain. If an attacker is able to generate and implement a corrupted ACL, the SDProp process will run and remove this unknown, malicious ACL from the domain.

#dsHeuristics is an attribute with a string value that is used for configuration of the entire forest. If a group is assigned the dsHeuristics attribute, it will be excluded from the process SDProp scanning domain ADLs.

#adminCount attribute tells us which users are or are not protected by the SDProp process. An attacker can analyze this list to determine which users are protected, which also often indicates that they have admin privileges. 

Active Directory Users and Computers ( #ADUC) is the #GUI used to manage users, groups, and devices in an Active Directory.

#ADSI Edit is another #GUI tool that allows for the modification of attributes assigned to any given object. Changes using this editor can cause major problems within your Active Domain if you are not careful.

#sIDHistory is a log of any SIDs that have been associated with a given object. This is often used to facilitate domain migration, so that all configurations are maintained during this change. 

NTDS.DIT is a #database that stores data about users, groups, and password hashes within a domain controller inside C:\\Windows\\NTDS\\. If an attacker gains access to this file, they have access to your list of hashes and can attempt to crack your hashes and gain access to your domains. You do have the option of storing passwords with reversible encryption, which increases your security a bit.

#MSBROWSE is an outdated network protocol for Windows that facilitated browsing. This has been replaced by the more modern Server Message Block ( #SMB) and Common Internet File System ( #CIFS).