# Active Directory Functionality

### FSMO

Flexible Single Master Operation ( #FSMO ) roles are used to divide administrative power into five roles:

1. Schema Master manages the definition list for all attributes and manages the read/write copy of the Active Domain #Schema.
2. Domain Naming Master ensures that each domain name is unique within the same forest.
3. Relative ID Master ( #RID) ensures that only one object is assigned to each unique #SID.  Domain Object SIDs are the domain SID combined with the objects' RID.
4. PDC Emulator is the Domain Controller ( #DC) that maintains domain time, Group Policy Objects ( #GPO), password changes, and any requests for authentication. 
5. Infrastructure Master facilitates communication between multiple domains within a single forest. It translates attributes like #GUID, #SID, and #DN between two domains. If there are problems with the Infrastructure Master, you will not see fully resolved names in your ACLs.

### Forest Functional Levels

Domain and Forest Functional Levels were created by #Microsoft to specify which #Windows server OS can operate a given Domain Controller.

### Trusts

A #Trust is a link of authentication formed between two domains or two forests that allows users on one domain/forest to access or allocate resources on the linked domain/forest.

There are two groups of trusts: transitive and non-transitive.

#Transitive trusts are extended via trusted relationships a child domain has.

#Non-Transitive trusts mean only the child domain is trusted.

Trusts can be bi-directional or single direction relationships. 

Parent-Child trusts are domains within the same forests where the child domain has two-way transitive trust with the parent.

Cross-Link trusts exist between child domains for faster authentication. 

External trusts exist between two domains in two separate forests that do not have an existing trust between them ( the forests ). #SID filtering is used to create this non-transitive trust.

Tree-Root trusts are two-way transitive trusts between a forests' existing root domain and a new one. 

A #Forest is a transitive trust between two root domains. 

Trust vulnerabilities are a major consideration for organizations and bad trust relationships can lead to privilege escalation and access to resources.





#Kerberoasting