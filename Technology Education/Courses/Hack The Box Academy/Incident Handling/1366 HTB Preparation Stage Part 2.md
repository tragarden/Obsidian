# Preparation Stage Part 2

The second phase of preparation is defensive - we will want to protect our systems even if that is not the primary role of an incident response team. 

### Methods for Protection

#### DMARC

*Domain-based Message Authentication, Reporting and Conformance* ( #DMARC) is an email verification protocol that builds upon the existing *Sender Policy Network* ( #SPF) and *DomainKeys Identified Mail* ( #DKIM).

DMARC is used to **detect and reject emails that pretend to originate from the same email server as you organization's emails**. This system is **easy to use but difficult to configure** properly. In most cases, it will work too well and reject real emails intended for your organization. What further complicates this is that these emails will be forever lost if this happens. With a **high-rate of false-positives**, this can be a problem.

#### Endpoint Hardening + EDR

***Client devices on our network are the most vulnerable points***  - we refer to these devices as *endpoints*. Here is a list of methods we can use to protect these endpoints:

- Disable #NetBIOS / *Link-Local Multicast Name Resolution* ( #LLMNR)
- **Remove administrator privileges from standard users**
- Implement *Local Administrator Password Solution* ( #LAPS)
- Configure #PowerShell for "*ConstrainedLanguage*" mode or disable it altogether
- Enable *Attack Surface Resolution* ( #ASR) rules for Microsoft Defender
- **Whitelist what you can** - note that #LOLBin files are the main threat vectors here
- Use a host-based #firewall to block communication between workstations
- **Use a host-based firewall** to block outbound traffic to LOLBins
- Use an **Endpoint Detection and Response** ( #EDR) anti-malware application with #AMSI.

#### Network Protections

We can **segment our network** to compartmentalize it and slow the spread of unauthorized access if we use a different #subnet for certain aspects of our #network. Any **internal resources should not have direct connections to the internet**.

Furthermore we can implement *Intrusion Detection Systems* ( #IDS) and *Intrusion Prevention Systems* ( #IPS) to **detect malicious network traffic** via #SSL / #TLS interception technology.

#### MFA + Password + Privilege Management

*Multi-Factor Authentication* ( #MFA) uses more than one means of authentication to access a resource. This **should be implemented in every case possible**. 

 **The most likely path for privilege escalation is through stolen credentials**. This can allow an attacker to successfully move to other accounts in the *Active Directory*. It should also be noted that ***administrator accounts need to have different passwords than the standard user account this administrator also uses***. 

***Passwords should be both complex and *strong***, because some complex passwords meet the criteria for password creation but are easily guessed or brute-forced by an attacker.

#### Vulnerability Scanning

Perform regular **scans of the network for vulnerabilities with automated techniques as well as manually**. While automation is useful, manual scanning will help us find inconsistencies the automated tool might overlook. 

#### Active Directory

The best perspective for protecting Active Directory is to **assume the role of an attacker and think of means of gaining unauthorized access**. This means actively **scanning through the active directory looking for logical gaps for entry**. There are common paths for exploiting Active Directory that we can look up and check for ourselves, but there still remains many vectors for escalation that are unknown. Continuous assessment of the Active Directory is necessary to ensure no flaws in logic have occured.

#### Purple Team

When we have the Red team attack our systems while the Blue team observes and reacts accordingly - this is known as purple teaming. The red team looks for means of unauthorized access so the blue team can identify and remedy these attack vectors.

### Related:

- [HTB Academy Home Page](https://academy.hackthebox.com/ 'HTB Academy home page')
- [HTB Academy 1366 Preparation Part 2](https://academy.hackthebox.com/module/148/section/1366 'HTB Academy module on preparation part 2')
- [021 Active Directory](021%20Active%20Directory.md)
- [0700 HTB Active Directory Structure](0700%20HTB%20Active%20Directory%20Structure.md)
- [0702 HTB Active Directory Groups](0702%20HTB%20Active%20Directory%20Groups.md)