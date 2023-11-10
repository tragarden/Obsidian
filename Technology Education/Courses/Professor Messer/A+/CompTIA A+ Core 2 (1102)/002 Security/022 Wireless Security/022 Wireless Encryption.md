# Wireless Encryption 2.2

### Encrypting Networks

*Wireless Networks* require #security as they almost always contain confidential information, and at the very least it prevents others from using the resource and contributing to your bill.  When you secure the network, **all information is encrypted to ensure that it is kept confidential.**  *Message Integrity Checks* ( #MIC) is used to **ensure that received data matches the sent data** and has not been intercepted and tampered with.

#### WPA

#WPA2 and #WPA3 are the common forms of #encryption used today.  Before the data is transmitted by the receiver and sender antennas it is encrypted, and **any receiving device must have the encryption key to translate the message.**

*WPA/2/3-Personal / WPA/2/3-PSK uses WPA2 or 3* with a **pre-shared 256-bit key that everyone will use.**

*WPA/2/3-Enterprise / WPA/2/3-802.1X* is used for large networks and individually **authenticates each user with an authentication server such as #RADIUS.**

#### Cipher Block Chaining / CCMP

*Counter Mode with Cipher Block Chaining Message Authentication Code Protocol* ( #CCMP Block Cipher Mode), otherwise known as Counter/CBC-MAC Protocol was used by #Wi-Fi Protected Access II ( #WPA2) since 2004 to provide data confidentiality via #AES encryption and *Message Integrity Checks.*

#### Galois / GCMP

#Galois / Counter Mode Protocol or #GCMP block cipher mode uses *Message Integrity Check* ( #MIC) with *Galois Message Authentication Code* ( #GMAC) to provide confidentiality with #AES.  This is what Wi-Fi Protected Access 3 ( #WPA3) uses to facilitate encryption since 2018.

#### Threats

##### WPA2 Handshake

A common issue with #WPA2 is **attackers getting your pre-shared key** ( #PSK) **by listening to your 4-way handshakes,** although sometimes they do not even need to see your handshake to capture the hash.

##### Hash

If an attacker uncovers your #hash, they can **run it on offline applications to brute force they correct key** for the encryption.  This allows attackers to use #brute-force attacks to obtain your #PSK.

##### Brute Force

As computers have grown in strength with powerful #GPU options and could-based password cracks, it has become much easier to obtain someone’s PSK.  Weak keys are easier to crack.

#### WPA3 SAE

#WPA3 uses *Simultaneous Authentication of Equals* ( #SAE) to verify ***mutual authentication from the client to the server without transmitting a session key, hashes, or performing a 4-way handshake.***  This eliminates the chance of brute force attacks.

##### Diffie-Hellman Key Exchange

The #Diffie-Hellman key exchange is an #IEEE standard known as the *‘dragonfly handshake’* is the standard for #WPA3 authentications. 

#### Hardware

Your *Wireless Access Point* and *Wireless Router* will handle authentication for your #network, allowing for various modes of #wireless security.

Open Systems do not require #authentication – there are no passwords or permission hierarchies.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/wireless-encryption-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [022 Authentication Methods](022%20Authentication%20Methods.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [123 Wireless Network Standards](123%20Wireless%20Network%20Standards.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [223 Wireless Network Technologies](223%20Wireless%20Network%20Technologies.md)

#study #professormesser #comptia #Aplus #security #encryption #router