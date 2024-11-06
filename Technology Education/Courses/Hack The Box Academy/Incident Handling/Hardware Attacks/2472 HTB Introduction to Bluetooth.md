# Introduction to Bluetooth

Bluetooth is used to wirelessly transfer data over short distances from fixed and mobile devices by establishing personal area networks ( #PAN) via radio frequencies. It is expected that shipments of Bluetooth devices will exceed 7 billion by 2026. 

The frequencies occur on the ISM band between 2.402 GHz and 2.480 GHz. It was designed to be an alternative to RS-232 cables. 

The name Bluetooth is derived from the name of a tenth-century king - Harald Bluetooth - who is remembered for unifying Denmark and Norway. 

### Connecting

Bluetooth connections are established by performing the following steps:

- Discovery - the device is set to 'discoverable' so it can broadcast it's presence.
- Pairing - a second device discovers the first one and sends a pairing request.
- Authentication - the devices share a link key or long-term key, sometimes required a PIN.

A Piconet is the name of the small network that is formed by up to seven active client devices.

 Scatternet is when multiple Piconets are integrated into a larger network. Some of the devices in the piconet serve as a bridge device to other piconets.

### Transfer Methods

There are two types of data transfer links for Bluetooth:

- Synchronous Connection-Oriented ( #SCO) links
	- steady connections that reserve slots at regular intervals, primarily used for audio.

- Asynchronous Connection-Less ( #ACL) links
	- does not reserve slots and transmit whenever they are able to. Used for all other types of data.

### Bluetooth Risks

The nature of the Bluetooth connection means that it is vulnerable to exploits of remote unauthorized access like data theft and control of devices.

- Unauthorized Access - threat agents can gain access to devices and intercept data exchanges to collect sensitive information.
- Data Theft - exfiltration of data like contact lists, messages, passwords, and financial data.
- Interference - Bluetooth uses 2.4GHz frequencies that are shared by a variety of other devices meaning that these signals can be disrupted or corrupted leading to data loss and instability.
- Denial of Service ( #DoS) - the devices are overwhelmed with requests when the protocols are exploited. This can render a device unresponsive and unable to perform.
- Tracking - physical locations of devices can be tracked leading to stalking and opportunities for crime. 

### Attacks

| Method            | Description                                                                                                                                         |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Bluesnarfing      | unauthorized access to data via Bluetooth                                                                                                           |
| Bluejacking       | sending of unsolicited messages via Bluetooth                                                                                                       |
| Bluesmacking      | Denial-of-Service attack that overwhelms Bluetooth connections                                                                                      |
| Bluebugging       | gaining control of a device via Bluetooth connections                                                                                               |
| BlueBourne        | a set of vulnerabilities that enable attackers to control devices or install malware via Bluetooth                                                  |
| KNOB              | Key Negotiation of Bluetooth where data encryption processes are manipulated during connection establishment.                                       |
| BIAS              | Bluetooth Impersonation AttackS where vulnerabilities in the pairing process are exploited allowing attackers to impersonate the device.            |
| Car Whisperer     | Targeting passenger cars to unlock doors or start the engine remotely, which can lead to theft.                                                     |
| Man-in-the-Middle | Interception and manipulation of data by someone in the middle of the connection between two devices.                                               |
| Key Extraction    | Retrieval of encryption keys used in the connection process.                                                                                        |
| Eavesdropping     | Threat actors intercept and listen to the communications, capturing this data for analysis like password discovery and financial data exfiltration. |

