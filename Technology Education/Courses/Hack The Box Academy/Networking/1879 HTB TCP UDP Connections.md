# TCP / UDP Connections

#TCP and #UDP are two different protocols that are used in the transmission of data across the internet.

#### TCP

Transmission Control Protocol ( #TCP ) focuses on the connection between sender and receiver and is similar to a phone call where two clients remain directly connected until the session is terminated. This #protocol audits every #packet sent across the internet, and if there are any discrepancies the data is discarded and must be resent. This is the slower and more reliable of the two protocols.

#### UDP

User Datagram Protocol ( #UDP) is a connectionless protocol that does not account for the accuracy of data received. It is faster and less reliable than TCP and may lose data during transmission.

#### Packets

An #IP #packet is the data transmitted to the internet via the layer 7 of the #OSI model, the #network layer. Packets contain a #header and a #payload. Some information within the packet header includes: version, header length, class, flags, TTL values, protocol used, source, destination, and options for routing.

#### Record-Route

The #Record-Route portion of packet headers contains the IP of each hop the data made on the way to its destination. This is contained within the #ICMP Echo Reply packet that is sent back once the data is received.

#Traceroute can be used to get more detailed information about the record-route and devices the data passed through on the way to the destination. Traceroute will return 'Destination Unreachable' or 'Port Unreachable' if you try to use this with a UDP data stream

#### Blind Spoofing

Blind Spoofing is when an attacker sends erroneous information across a network without analyzing the data sent back in response.