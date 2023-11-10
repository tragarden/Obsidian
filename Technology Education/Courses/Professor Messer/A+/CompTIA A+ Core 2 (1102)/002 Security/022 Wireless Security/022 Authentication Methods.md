# Authentication Methods 2.2

### Authentication

The pathing for #authentication is the following:

>Client > Internet > Firewall / VPN Concentrator / Access Point > Authentication Server > Firewall/AP/VPN > Internal File Server

#### RADIUS

*Remote Authentication Dial-In User Service* ( #RADIUS) is a form of *Authentication Authorization and Accounting* ( #AAA) #protocol that **centralizes authentications for all users on a #network.**  This eliminates the need to authenticate every time you access a #router, #switch, #firewall, #VPN concentrator, or other parts of the wireless #network.  **RADIUS is available on nearly any type of server operating system and is a very old method of managing authentication.**

#### TACACS

*Terminal Access Controller Access-Control System* ( #TACACS) is a **remote authentication protocol used to control dial-up access** to #ARPANET.  TACACS+ was an open standard in 1993, but over time it has become mainly associated with #CISCO brand devices.

#### Kerberos

#Kerberos is another **authentication protocol where once you are authenticated, you are trusted by the system** and will not need to provide credentials again.  It was developed as a standard in the 1980s by *Massachusetts Institute of Technology* ( #MIT) and uses **mutual authentication to resist #on-path or replay attacks.** Kerberos 5.0 was standard on #Windows 2000 and compatible with many other devices and systems.

#### Single Sign-On

*Single Sign-On* ( #SSO) is the method used for the **single authentication, removing the need to constantly input your credentials.**  Although there are many methods for verifying your SSO, ***SSO only works with Kerberos.***

#### Deciding on a Method

The method that is used by your network is often determined by existing technology and standards your organization is using. If you already have a RADIUS server for your VPN access, then it makes sense to keep using it for other aspects too.  If you end up using TACACS+, there are probably a lot of CISCO devices on your network. If Kerberos is in use, you know this is a Microsoft-based network.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/authentication-methods-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)

#study #professormesser #comptia #Aplus #security 