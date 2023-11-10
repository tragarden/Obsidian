# Logical Security 2.1

### Security Concepts
#### Principal of Least Privilege

*Least Privilege* is a concept where a **user is only allowed to access the bare minimum of secured data to complete their work.**  ***All applications will run with the lowest needed permissions to perform their tasks.*** Preventing users from having administrative #privileges means that any viruses or #malware on their machine will only have the permissions allocated to this user.  Since employees may not be as security savvy as a #sysadmin, this cuts down on threats.

#### Access Control Lists

*Access Control Lists* ( #ACL) are used to **allow or deny traffic** within a #network, #NAT, #QoS, or file system.  They can **evaluate traffic data** like source #IP, destination IP, #TCP and #UDP port numbers, and #ICMP data.  A set of criteria is evaluated and if the traffic does not meet certain requirements, it will be disallowed. 

#### MFA / 2FA

*Multi-Factor Authentication* ( #MFA) **requires more than one security method to validate a user.** These methods include:

>Something you are/have/know.

>Somewhere you are.

>Something you do.

##### MFA Authentication Methods

A *pseudo-random number generator* is often a small device that **generates a new security code every 30 seconds** or so, which correlates to a server that secures the device you are trying to access. 

*Software Tokens* are an **alternative to the handheld number generator** and is available on your smartphone, therefore eliminating the need for a second device. This is a more **cost-effective method of generating tokens.**

*Short Message Service* ( #SMS) is a way to **securely log-in via text messages** in conjunction with your username and password.  Your **login factor can be texted to you,** and then you enter the number you received into a SMS code prompt within the login form.

**Threats to SMS methods include phone number reassignment, intercepted SMS messages, and spoofing** of the SMS messages.

*Voice calls* are similar to SMS methods and share similar disadvantages as well.

#### Email Filtering

*Email Filtering* is used to **block unwanted emails at the local gateway.** This technology is either on-site hardware or cloud-based and also scans incoming data for threats and will block #malware and viruses from reaching the users on your network.  **Great for blocking executables, exploits, 
#phishing attempts, and #spam.**

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/logical-security-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [021 Active Directory](021%20Active%20Directory.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)

#study #professormesser #comptia #Aplus #filesystem #gateway #email #security 