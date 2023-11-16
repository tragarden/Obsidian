# HackTheBox Networking Introduction

### Terms / Definitions

A #Network facilitates communication between at least two computers. There are many types of networks and many protocols for different forms of communicating. 

A #Topology is a representation of your network layout in diagram form. Common topology styles include star, mesh, and tree formats.

A #Medium is the method for transmission, examples including #ethernet, #fiber, #coaxial , and #wireless.

A #Protocol is the set of rules and standards used to facilitate communication between computing devices throughout a network.

A Uniform Resource Locator ( #URL) is the address of a website that is entered into a #browser by a user. This is similar to a FQDN, but provides more specific details about the address of the site.

Fully Qualified Domain Names ( #FQDN) yield a less specific address than URLs, usually leading to the home or landing page of the specified site.

- One could think of FQDN addresses as the street address of a building, while URLs add additional information like a metaphorical room number and employee name. 

A #router receives information from a #client on our local network and forwards packets to an ISP.

Internet Service Providers ( #ISP) are the companies that supply connectivity to your network and receives the requests and information from your #router in the form of a #packet before forwarding it to the appropriate DNS servers.

A Domain Name Service ( #DNS) receives the packets from your ISP and performs a lookup of the URL originally submitted by your client #browser. Once the DNS server converts the URL to the associated IP address, this information travels back across the internet to be received by your router.

A #printer cannot be secured and needs to be places on a separate network so that it does not serve as a vector for attack. Since #Windows requires administrator rights to perform a print job, printers have been issued administrator rights via #NTLMv2.  If the security of the printer is compromised by an attacker, they have an easy point of entry into your network.