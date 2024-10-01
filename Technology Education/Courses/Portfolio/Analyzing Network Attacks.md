A travel agency is advertising sales and promotions on their site that the employees use while planning trips for clients.

The monitoring system alerts you that there is a problem with the web server. When you try to visit the site, you experience a timeout error message in the browser.

Using a Network Protocol Analyzer ( sniffer ) you notice a lot of TCP SYN requests from an unfamiliar IP. The server is currently overwhelmed with network traffic.

You take the server offline and configure the firewall to block the IP sending the SYN requests. This is a temporary fix and after alerting your manager, you prepare a report for your boss to inform them about what is happening.

The web server IP is 192.0.2.1
The employee computers are on the subnet 198.51.100.0/24

Consider the following questions:

- what do you currently understand about network attacks??
- Which type of attack would likely result in the symptoms described in this scenario?
- What is the difference between a Denial of Service ( #DoS) and Distributed Denial of Service ( #DDoS)?
- Why is the website taking a long time to load and report a connection timeout error?

- Currently I understand that network attacks are perpetrated by threat actors and DoS attacks are a simply employed method of attack where an attacker can spam SYN requests to a server until all of it's resources are depleted or occupied.
- I think a SYN attack is likely because the requests I am sending are taking too long to be processed by the server. This likely indicates a high level of traffic and that is a symptom of this style of attack.
- The difference between DoS and DDoS is the amount of devices used in the attack. A DDoS attack uses many machines at once to spam SYN requests, usually by using a botnet to build a small army of machines to perform the attack with.
- The site is taking a long time to respond because the resources available on the server are overtaxed with requests.

One potential explanation for the website's connection timeout error message is that a DoS attack via SYN spamming is overtaxing the web server and preventing new requests from being processed. The Wireshark log shows that initially the server is receiving SYN requests and responding to them with SYN / ACK requests, before receiving an ACK response and permitting the sender IP access to resources. The problem is that it is becoming overwhelmed by constant SYN requests. Eventually there are so many SYN requests that the server cannot respond to them frequently enough causing timeout errors when requests are not answered soon enough. Eventually the server stops responding altogether when the resources are fully occupied and many requests are not answered within the given time.

The logs show that there is a continuous influx of SYN requests to which the server is responding normally to. Eventually so many SYN requests are being processed that the server hardware is no longer capable of keeping up.

This event is likely a DoS attack in the form of SYN spam.

This DoS event is requesting too many three way TCP handshakes for the server to handle.
- The SYN request is sent to the server from the client.
- The server reads the SYN request and responds with a SYN/ACK response that acknowledges the reception of the initial SYN request. 
- The client reads the SYN/ACK response from the server and responds with it's own ACK response that acknowledges reception of the SYN/ACK response from the server..
This process takes multiple communications from the server and when too many SYN requests are submitted to the server, the reserouces on the server are overwhelmed and cannot process all of the requests.

The logs indicate that this type of process is happening to the web server and causing the timeout errors.

A potential consequence of this problem is that sales will be lost for honest clients that truly want to access the resources on the server ( the website ).

A way that the server could be secured is to configure the firewall to ignore requests from the IP of the SYN spam sender. This is a temporary fix. A Next Generation Firewall could be used to identify suspicious traffic or multiple requests from the same IP.