# Cyber Kill Chain

The *Cyber Kill Chain* ( #CKC) is a **seven stage flowchart that describes the lifecycle of a cyber attack**. This is useful in understanding the process of attacking and determining how far into the network the attacker has gained unauthorized access.

### The Seven Stages

The seven stages of the Cyber Kill Chain are:

1. Recon
2. Weaponize
3. Deliver
4. Exploit
5. Install
6. Command and Control
7. Action

#### Reconnaissance

The first stage of the cyber kill chain is the *reconnaissance*, or recon stage, and is **the information gathering stage** of an attack.  This is when an **attacker familiarizes themselves with the organization** they are attacking. The will read social media ports, articles about the organization, read about company partnerships, read job ads, and read about technology the organization uses. During this phase they will begin **scanning the network to determine applications and #IP addresses** being used.

#### Weaponization

The *Weaponization* stage is when the attacker **develops a method of attack through malicious payloads and #malware**. They will determine how to **implement this #payload without triggering the security measures** in place based on the information they gathered during the reconnaissance stage.

#### Delivery

The *Delivery* stage is when the **attacker sends their payload to the victims** in an attempt to get them to execute the payload, **usually via social engineering**. The social engineering methods that are typically employed include email #phishing attacks, phone call phishing attacks, malicious websites that imitate a site from the organization, and on rare occasions - physical installation of the payloads using #USB drives or similar. This is ***almost always executed by tricking someone*** within the organization.

#### Exploitation

The *Exploitation* phase begins as soon as a victim or the **attacker executes the payload** within the target network.

#### Installation

The *Installation* stage occurs **after the payload has been delivered and executed** within the target network. There are multiple ways this can be accomplished, a few of them include:

- #Droppers are **small code blocks with payloads** that are delivered and executed on the target.
- #Backdoor attacks use malware to **create a constant means of access** for the attacker on the target system. This allows the attacker to continuously access the network over time.
- #Rootkit attacks **install malware into the core directories of the #OS, bypassing most anti-virus and anti-malware methods** of detection. These are powerful attack methods that are ***very difficult to detect and remove*** once installed.

#### Command and Control

The *Command and Control* ( C&C) stage of an attack is when **remote access is established** by the attacker on their target system. This attack is usually done **using modular stagers that add more scripts and malware** to the target system over a period of time.

#### Action

The *Action* stage is the objective of the  attacker - this is **when they accomplish their goal of either exfiltrating sensitive data or escalating privileges** in order to lock the organization out of their network with a #Ransomware attack.

#### Linearity 

**Although this cyber kill chain has been presented in a linear way, this is not how attackers operate** because in most cases they will return the the recon stage multiple times during their attack. This is the same as when we oscillate between the Information Gathering stage and the Vulnerability Assessment stage during our penetration tests.


### Related:
- [HTB Academy](https://academy.hackthebox.com/ 'HTB Academy home page')
- [HTB Cyber Kill Chain 1363](https://academy.hackthebox.com/module/148/section/1363 "HTB Academy module on cyber kill chain")
- [024 Social Engineering](024%20Social%20Engineering.md)
- [0938 HTB Information Gathering](0938%20HTB%20Information%20Gathering.md)