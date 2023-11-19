# Wireless Networks

### Wireless 

#A #Wireless #Network uses Radio Frequency ( #RF) technology to transmit signals across a network instead of physical wires. Common methods of transmission include #Wi-Fi, #4G-LTE, #5G, and more across #LAN and #WWAN networks.

#### Access Points

Many devices, each known as a #host, are able to be integrated into a wireless network. The size of these networks can be extended using devices known as Wireless Access Points ( #WAP). 

#### Wi-Fi

#Wi-Fi is a very common method of transmission over the frequencies 2.4GHz and 5GHz. You can read more in the article [Home Network](Home%20Network.md).

#### Connecting

Any host intended to join the network must have supplied credentials to join the network. The Service Set Identifier ( #SSID), or network name, is paired with a password to gain access to the target network. The host device will send a connection request frame (aka association frame) over the #IEEE 802.11 protocol.

#SSID can be hidden from unknown hosts by disabling broadcasting on your default #gateway.

#### Connection Request Frame

The Association Frame will include information needed to securely connect to the network, including the hosts #MAC address for it's wireless adapter, the #SSID of the network, and a list of usable data rates, channels, and security protocols.

#### WEP Handshake

Wired Equivalent Privacy ( #WEP) security protocol uses a challenge-response handshake paired with secret key and authentication #packet. 
1. The #client will send an association request to the WAP, which will respond with a challenge string. 
2. The client will calculate a response to this challenge string before sending this response back to the WAP with a shared secret key. 
3. The WAP will then respond with its own calculated response before using the secret key to see if the responses match.
4. The WAP sends its response packet to the client. #CRC is used to verify if the data is valid or corrupted.

#### CRC

Cyclic Redundancy Check ( #CRC) is a #checksum used in the WEP protocol for error detection and data corruption. This is the value that is calculated by both the client and WAP during the WEP handshake. CRC values are calculated for each passing packet - if the values match, the data is valid. If the CRC values DO NOT match, this data will be discarded and transmitted again. 

There is a major flaw in the CRC checksum method where we can evaluate the plaintext data attached to the #header of each #packet. This means we can use CRC to reveal packet plaintext data even if it has been encrypted. 

### Security

Wireless #security is a major concern for protecting our privacy and personal data. There are a variety of methods employed to ensure safe communication across out network. 

#### Encryption

#Encryption uses algorithm protocols like Wired Equivalent Privacy ( #WEP) and Wi-Fi Protected Access ( #WPA2 / #WPA3) to obscure data traffic on our network. 

#### Access Control

Access Control is a system for authorizing devices on a network using MAC addresses and a password.

#### Firewall

A #Firewall use a set of predetermined rules to monitor and screen network traffic.

### Encryption Protocols

#### WEP

Wired Equivalent Privacy ( #WEP) is an older method of #encryption that is no longer supported on modern devices due to vulnerabilities with the protocol. WEP makes use of 40-bit, 104-bit, and if using #AES, a 128-bit shared key. This is all encrypted with a #RC4 cipher algorithm that stores its values in plaintext. 

Shared Keys are composed of two parts, a Secret Key and a Initialization Vector ( #IV). Due to the way this data is stored, it is susceptible to #brute-force attacks.

#### WPA

Wi-Fi Protected Access ( #WPA2 / #WPA3 ) is a more secure method of #encryption that utilizes a Pre-Shared Key ( #PSK) or an 802.11 authentication server.

### Authentication Protocols

Lightweight Extensible Authentifcation Protocol ( #LEAP) and Protected Extensible Authentication Protocol ( #PEAP) are derived from the Extensible Authentication Protocol ( #EAP) authentication framework. These protocols are used in conjunction with WEP and WPA protocols to add layers of security to a given network. 

- LEAP utilizes a shared key method of authorization that is used to both encrypt and authorize. 
- PEAP is more secure and uses digital certificates and tunnel encryption via Transport Layer Security ( #TLS) . The encryption tunnel conceals the authorization certificates from attackers. 

### TACACS+ 

Terminal Access Controller Access-Control System Plus ( #TACACS) is used for authorizing network devices on a network. TACACS+ receives its request #packet in an encrypted state to prevent attackers from intercepting them and revealing credentials. #SSL, #TLS, and #IPSec are some of the methods of encryption used for TACACS+.  

### Disassociation Attacks

Disassociation attacks are when an outside party sends disassociation frames to an access point, which will disconnect a certain device from the network. This may be used from inside or outside of a network depending on the network security present.  These types of attacks are used to inconvenience and disrupt the users on a network. 

### Wireless Hardening

There are common methods of improving the security of your wireless network:

#### Broadcasting

If your network name, or #SSID, is shown on the list of local wireless networks available, then your default gateway is broadcasting the SSID outward for all to see. By disabling broadcasting on your device, you will render your SSID undiscoverable to outside parties.

#### WPA

WPA2 or WPA3 should be used on any wireless network in 2023. There are personal and enterprise variants of these encryption methods. WPA-Enterprise works in conjunction with a centralized authentication server like TACACS+ or #RADIUS.

### MAC Filtering

MAC filtering creates a list of accepted devices based on their MAC address - devices that are not known to the network will not be able to connect.

### EAP-TLS

EAP-TLS uses digital certificates and #PKI to authenticate users and establish secure and encrypted connections.



### Related: 



#protocol #TCP #IP #TCP/IP #channel #DHCP #WPA2 #WPA3 #DNS #IP