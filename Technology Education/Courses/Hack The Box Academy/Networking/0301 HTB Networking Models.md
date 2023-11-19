# Network Models

The #network models we use are known as the #OSI model and the #TCP/IP model.

### OSI

The Open Systems Interconnection ( #OSI) model is also known as the ISO/OSI layer model, which illustrates the means of communication between networks using seven layers. This was created by teamwork between the International Telecommunication Union ( #ITU) and the International Organization for Standardization ( #ISO).

### TCP/IP

Transmission Control Protocol / Internet  Protocol  ( #TCP/IP) are each a #protocol that facilitates the transmission of packets of data. The acronym is used as a generic term to include more than just these two protocols. #ICMP and #UDP fall under the umbrella of TCP/IP, which includes many other associated protocols. 

When considering the two models, we can think of TCP/IP as flexible with general guidelines and lightly enforced rules. OSI is a more strict protocol that facilitates communication from the network to the clients.

### Packet Transfer

#Packet transfer occurs accross several logical layers of the TCP/IP and OSI models before being applied to the #physical layer - where hardware becomes involved and the information is sent outside of your network. This information is transferred in a format called Protocol Data Units ( #PDU).

#### Headers

As PDUs pass through the layers of the models, each layer will process the incoming data and add a #header to the upper layer to identify the #packet. The combined header and PDU are what compose the packets. 

When the packet reaches the receiver, it reverses the entire layering process, using the headers to identify the packets. Once all the packets have been received the process ends and the data can now be used.

From the perspective of a #penetration tester, we should consider each model as a different tool. TCP/IP is useful for analyzing how the connection is formed. OSI yields more granular details about the network traffic and headers of the packets.