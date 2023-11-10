# Remote Access 4.9

### Remote Access

*Remote Access* refers to the **ability to share one desktop from a remote location** and interact with it remotely. #RDP and #VNC are common frameworks for remote connections.

#### Remote Desktop Protocol

#Microsoft *Remote Desktop Protocol* ( #RDP) is available for #macOS, #Linux, #Unix, and more #OS's and is a common software for remote access.

#### Virtual Network Computing

*Virtual Network Computing* ( #VNC) is an #open-source remote service and uses the *Remote Frame Buffer* ( #RFB) #protocol to **facilitate connectivity between two devices.**  This is available for many operating systems.

#### Remote Desktop Security

*Remote Desktop Security* is a major #vulnerability – **if someone is able to remotely access a device** on a #network that has administrative #privileges, **they may have access to the entire network system and related databases.**  They will be able to connect and operate other devices within the network and even make purchases with the users’ bank credentials.

If #port **tcp/3389** is open – **this is a #security threat.** This is the port for remote access requests, and if an attacker identifies that this port is open, you become susceptible to #brute-force attacks. 

### VPN

*Virtual Private Networks* ( #VPN) are used to #encrypt user data traveling across a private network.  The data will **pass from the client on to a VPN #Concentrator that can encrypt and decrypt the inbound and outbound data.**  There are many options, including VPN Concentrators built-in to your #firewall and open-source #software from #Linux that interacts with #cryptographic #hardware to encrypt data.  Some VPNs are not built into your operating system or #browser.

#### Client-to-Site

*Client-to-Site* VPN gives us **on-demand access to the VPN from a remote device** via software that connects to the VPN concentrator.

**VPN data is heavily encrypted and very secure.** #Authentication is highly secure, but **if an attacker can determine the #endpoints of data transfer or gain your #credentials, then they may gain access to #encrypted data.** Make sure to enable *Multi-Factor Authentication* ( #MFA) to ensure that an attacker will need more than your credentials for access.

#### Secure Shell

*Secure Shell* ( #SSH) **(tcp/22)** is #encrypted console communication that looks and acts like #Telnet (**tcp/23**).

#Network traffic is #encrypted via #SSH #security, so an attacker doesn’t have much interest in intercepting the #packets crossing the network.  **Attackers will focus on the endpoints which are the server and the client.** SSH Authentication requires a public/private key pairing for authentication.

*Certain accounts should be disabled for SSH* access – **you DO NOT want to be able to access the #root account,** because then if your communication is hacked or otherwise compromised, you will give them full control over the system with administrative #privileges. **Consider removing password-based #authentication features. Limit access to the #SSH destination by #whitelist for approved and known #IP addresses via #firewall or network filter.**

### RMM and MSP
#### Remote Monitoring and Management

#RMM and #MSP provide many features including **operating system patching, remote login, monitoring anomalies, and inventorying hardware and software** within the network.

*Remote Monitoring and Management* ( #RMM) is a #utility for **managing a system from a remote location.**

#### Managed Service Providers

*Managed Service Providers* ( #MSP) facilitates the **management and monitoring of many customers and systems** across many different levels of service.

#### Vulnerabilities

Due to its power, the #RMM is a **popular point of attack as it yields much information and control** over the system.  Make sure to limit access to the RMM and consider who you choose to grant access to.

#### Auditing

**Auditing users and IPs that connect and interact with this network is important so you recognize and know the common users making sure that when an intruder is present,** it might be more obvious.

#### MSRA

*Microsoft Remote Assistance* ( #MSRA) is a way to **access a remote desktop without configuring your firewalls or #port forwarding.**  A user will make a request for connection and a technician will respond to the invitation with a corresponding password. 

#MRSA was **replaced by** *Quick Assist* in Windows 10 and 11.

While Quick Assist / MSRA are useful for easy Remote Desktop access, **they are susceptible to social engineering attacks,** as these applications are so easy to use that people who are unaware may click a link or grant access to an attacker without really understanding what they are agreeing to.  Be skeptical of invitation emails with links.

#### Third Party Tools

screen sharing: #GoToMyPC and #TeamViewer.

Video Conferences: #Zoom, #WebEx

File Transfer: #Dropbox, Box.com, #Google Drive

Desktop Management: #Citrix Endpoint Management, #ManageEngine Desktop Central

#### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/remote-access-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")3
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [142 Client-side Virtualization](142%20Client-side%20Virtualization.md)

#study #professormesser #comptia #Aplus #virtualization 