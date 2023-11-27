# Active Directory Security

Active Directory ( #AD) is designed to centrally manage shared information across a large userbase where access ranges in privilege and access. Active Directory can be an insecure environment due to this, but there are methods for hardening our AD.

### CIA Triad

The CIA Triad is a visually represented set of values that are keystone in developing strong security practices. The three key tenets are confidentiality, availability, and integrity. This means data is always accessible, private, and true.

### Hardening Methods

Methods for hardening include: inventory audits, vulnerability patching, managing configurations, protecting endpoints, user awareness, subnetting, and more.

#### LAPS

#Microsoft Local Administrator Password Solution ( #LAPS) is used to rotate #administrator passwords on any #host running a Windows #OS. This is a useful password management tool and prevents lateral travel between accounts, which can lead to privilege escalation.

#### Audit Policy

Logging and Monitoring activity on your network and within domains is important for detecting unauthorized access and monitoring the activity of attackers once your network has been compromised.

#### Group Policy

Group Policy Objects ( #GPO) are configuration settings stored virtually that apply policies to different users and groups at the level of Organizational Units ( #OU). There are several #security policies useful for hardening the Active Domain.

Account Policies manage user accounts within a given domain.

Local Policies apply to a device and involve the audit policy, rights assignments, and permissions like driver install, enabling administrator accounts, and preventing devices like printers from being installed.

Software Restriction Policies set limits on what software can be used on a given host.

Application Control Policies is used to manage the applications allowed on the devices of specific users or groups. A common practice is to restrict access to applications like CMD and PowerShell, as well as other executables. #AppLocker is another similar application that can restrict file and application access.

Advance Audit Policy Configuration is used to audit file modification and access, account logons, and changes to rights, permissions, and policies.

#### Update Management

Windows Server Update Service ( #WSUS)  is installed on #Windows #Server to automate patching and updating across the domain or network. 

System Center Configuration Manager ( #SCCM) builds upon the WSUS application as a paid solution to make sure patches are deployed quickly across a large array of devices.

#### Group Managed Service Accounts

A Group Managed Service Account ( #gMSA) is a high level security account that provides automated password management via the Domain Controller ( #DC). 

#### Security Groups

Security Groups allow for granular management of permissions across many account, group, and domain types.

Built-In groups are created during the creation of any domain, and provide default accounts for administrators and users alike. 

#### Account Separation

Administrators must have two accounts: one for daily use like checking emails and web browsing, and another that is strictly for purposes of administration. This means that if the admin falls prey to a phishing attack or trojan horse, then this malware or unauthorized user will be confined to the account without administrator rights.

#### Password Policies

Password guidelines should be known by all users on the network and enforced by administrators and splash screens. Passwords should be at least 12 characters long with varying cases and symbols. In an ideal situation, an organization should have enterprise password technology that randomly generates and submits credentials with a random password generator.

Multi-Factor Authentication is important and should be enforced throughout an organization and for personal use as well. This uses another credential in addition to standard submission of a password.

#### Domain Admin Accounts

Domain Admin accounts should never be used as a login for workstations or clients, it should only be used for logging into Domain Controllers ( #DC).

#### Auditing

Old user accounts and unused objects that remain in the domain are an attack vector, they should be routinely purged periodically throughout the working year.

Access Control audits will analyze the domain for unnecessary administrator accounts, which can create a large attack surface, especially if they are unused or outdated.

Restricted Groups can be used to limit the access of administrator accounts and domain admin accounts with the additionally control over the memberships of Enterprise Admins and Schema Admins.

#### Limiting Server Roles

It is important to keep servers somewhat limited in the tasks and services they perform. If you are using a server as a Domain Controller, then it would be unwise to install a Internet Information Server ( #IIS) application as this will increase the surface for attack, compromising the #DC.
