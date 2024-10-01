### Overview

I will analyze artifacts using VirusTotal and capture IoC details using the Pyramid of Pain. The PoP will be used to scale these artifacts and categorize them based on this hierarchy.

### Scenario

I work in the Security Operations Center ( SOC ) for a financial company that recieved an alert about a suspicious file on an employee workstation. I discovered that this file was downloaded from an email attachment disguised as a password protected spreadsheet file. The password for the file was included in the email. The employee downloaded the file and entered the password to access it, which executed a malicious payload on their computer.

After I recieved the file I created a SHA256 hash value for the file in order to identify the malware. Uploading the hashed value to VirusTotal will reveal any IoC's related to this compromised file. I will report findings within my Incident Handler's Journal to track this process.

### Project 

Timeline of Events related to the incident:

- 13:11 - employee receives the email containing file attachment.
- 13:13 - employee downloads and executes the file.
- 13:15 - multiple unauthorized executables are created on the employee workstation.
- 13:20 - Intrusion Detection System detects these executable files and alerts the SOC.

SHA256 hash value for the file: 
54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b

#### Verdict 

This file is considered malicious based on reviewing data on the VirusTotal website such as the Vendor's Ratio and Community Score. 58 of the 72 vendors flagged this executable file as malware and the community granted a rating of -81 indicating a strong trend of members indicating malicious content. 

#### Pyramid of Pain 

##### Hash Values

Other Hash Values related to this executable file are as follows:

- MD5 - 287d612e29b71c90aa54947313810a25
- SHA1 - 8f35a9e70dbec8f1904991773f394cd4f9a07f5e
- Authentihash - 019439328ea87e4559b653ad7df933d20623bdd00d3793abc7ff35e57db24853

##### IP Addresses

IP Addresses that were contacted by this malware include:

- [104.115.151.81](https://www.virustotal.com/gui/ip-address/104.115.151.81)
- [108.177.119.113](https://www.virustotal.com/gui/ip-address/108.177.119.113)
- [114.114.114.114](https://www.virustotal.com/gui/ip-address/114.114.114.114)
- [13.107.21.200](https://www.virustotal.com/gui/ip-address/13.107.21.200)

##### Domains

Domain names that were contacted by this malware include:

- [misecure.com](https://www.virustotal.com/gui/domain/misecure.com)
- [org.misecure.com](https://www.virustotal.com/gui/domain/org.misecure.com)
- [pki.goog](https://www.virustotal.com/gui/domain/pki.goog)
- [www.msn.com](https://www.virustotal.com/gui/domain/www.msn.com)

##### Network/Host Artifacts

Network and Host artifacts that were created by this malware include:

Network:

- http://172.16.1.2:5357/048da2fc-03cd-4f4f-9037-fcd5f0ea1411/
- http://crl.verisign.com/pca3.crl

Host:

- Created Processes on Windows
- Deleted Files on Windows
- Created a Process with modified I/O handles and windows

##### Tools

I did not discover any tools associated with the implementation of this malware.

##### TTPs

Tactics, Techniques, and Procedures that were used to implement this malware include:

- Process injection by spawning processes.
- Defense Evasion by obfuscating files or data.
- Shares Modules by linking functions at runtime on Windows.
- Sandbox Evasion by sleeping dynamic analysis using evasive loops.

### Notes from Exemplar

This malware is known as Flagpro which is used by the Threat Actor BlackTech.
