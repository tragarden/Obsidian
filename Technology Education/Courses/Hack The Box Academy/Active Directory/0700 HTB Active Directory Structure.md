# Active Directory

Active Directory ( #AD) is a #Windows #service that allows for centralized management of users, machines, groups, #network devices, file shares, policies, and servers. Active Directory manages authentication and authorization for Windows #domain. 

Active Directory Domain Services ( #ADDS ) is used by an organization to grant access to users and administrators within a network. This environment is prone to problems due to misconfiguration and potential for attack.

The Active Directory is vulnerable because if it is accessed via known flaws, it allows for lateral movement into other accounts on the network, which leads to vertical movement - also known as escalation of privileges. Privilege escalation can result in unauthorized access to computers, groups, policies, users, organizational units, domain levels, and access control lists within the domain. 

Active Directory takes on the form of a hierarchical tree structure, and we call the all-encompassing domain containing these trees the forest. These forests or domains can be linked via trust relationships within an organization. Domain trusts can lead to breaches in security if not configured properly.