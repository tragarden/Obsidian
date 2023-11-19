# Virtual Private Networks

A Virtual Private Network ( #VPN) is a secure method of communication between two devices. VPNs form an encrypted connection from one device to another, obscuring the transmitted data from outside sources.  This is a technology that is often used to connect to a company network remotely. Once a connection is established, the device is assigned a Local #IP on the network it is accessing, allowing access to network devices and resources.

These connections are made with the help of a #protocol, often Point-to-Point Protocol ( #PPTP) or #IKEv1 / #IKEv2.  PPTP uses #port TCP/1723 and IKE protocols use port UDP/500 for VPN connections. 

When we examine activity at the #TCP/IP layer, the connection will use Encapsulating Security Payload ( #ESP) protocol for both encryption and authentication. 

The VPN #Client is installed on the client device in order to connect via VPN.

The VPN #Server receives the encrypted data from the client and routes traffic between the client and the private network it's accessing. 

### IPSec

Internet Protocol Security ( #IPsec) is a protocol that encrypts and authenticates connections using two protocols. It encrypts every #IP #packet and adds an Authentication #Header ( #AH), which is one of the two protocols mentioned. 

Authentication Headers (AH) are a protocol that attaches a header to each IP packet that is compared to a #checksum after transmission to ensure that the data has not been corrupted. 

Encapsulating Security Payload ( #ESP ) is used to encrypt the data within each packet.  This protocol may also add headers and authenticate if desired.

#### IPsec Modes

Transport Mode is used for encrypting and authenticating end-to-end communication WITHOUT encrypting the Authentication Headers. 

Tunnel Mode will encrypt and authenticate the packets AND headers. This is usually associated with a VPN connection,

### Additional Important Protocols

The following protocols are used to encrypt and authenticate data traffic operating within the realm of the VPN.  These protocols protect your data from interception and modification.

#### Internet Protocol

Internet Protocol ( #IP) is the foundational protocol that facilitates all internet traffic. IP operates on port UDP/50-51.

Internet Key Exchange ( #IKE ) maintains a VPN connection via the #Diffie-Hellman algorithm which securely transfers key exchange information. This uses port UDP/500.

Encapsulating Security Payload ( #ESP) creates the tunnel of #encryption between the client and intended network. This uses port UDP/4500. 

Point-to-Point Tunneling Protocol ( #PPTP) is used to create the VPN and encapsulate your data within a tunnel of encryption. This form of encryption is no longer used due to known vulnerabilities with the authentication method #MSCHAPv2.