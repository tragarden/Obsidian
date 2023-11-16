# Proxies

### What is a proxy?

A #proxy is when a mediator is able to intercept data moving across a connection before forwarding it to wherever the proxy chooses. If there is no ability to mediate the middle of the connection, then this is an example of a #gateway and not a proxy.

### Types of Proxies

#### Dedicated / Forward

A Forward Proxy is when a request is sent from a client to another computer, and the computer acts on the received request. This is often used on corporate networks so that workstations must pass internet requests through another computer that is the proxy between the client and the internet. #Burp Suite is an example of this type of proxy.

#Firefox uses #libcurl instead of #WinSock, which is #Windows' native #API. #Chrome, #Edge, and #Explorer all use WinSock, making them more prone to #malware.

#### Reverse

A Reverse Proxy is the opposite of a Forward Proxy - it filters incoming requests instead of outbound requests from a client on the network. #CloudFlare is an example of this type of proxy and is capable of robust defense against #DDOS and malicious traffic. #ModSecurity is a Web Application Firewall ( #WAF) that uses this type of proxy to identify suspicious traffic. 
Penetration testers will use reverse proxies to monitor an endpoint that has been infected to analyze the incoming data.

#### Transparent

Transparent proxies are unknown to the client that it is interacting with, being used as a partner in communication.

Non-Transparent proxies are known to the client and usually are used to communicate with another non-transparent proxy on another known client. This proxy must be configured to receive packets from the client before forwarding them to the internet.