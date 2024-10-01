# Legacy Attacks

### Bluejacking

Bluejacking is an often harmless attack style that involves sending unauthorized text messages to or from a hacked device. This is an exploitation of the Object Push Profile ( #OPP) where they are able to send texts or images to the targeted device.

Object Push Profile ( #OPP) facilitates basic exchanges between devices, usually used for Virtual Business Cards ( #vCards), calendar entries, notes, or images. A paired connection is not required, allowing threat actors to act from stealth. 

These attacks are typically harmless and only really have an impact if used in the form of a social engineering attack. Reconfiguring default Bluetooth settings can prevent these attacks.

#### AirDrop

AirDrop is proprietary Apple technology that uses Wi-Fi and Bluetooth simultaneously. In the past, AirDrop was susceptible to an attack similar to Bluejacking. If AirDrop was configured to allow requests from 'Everyone', anyone within 30 feet could send you files.  These minor attacks were called AirDrop spamming and Cyber Flashing until iOS 16.2

### Bluesnarfing

Bluesnarfing is when unauthorized access is used for data exfiltration from a Bluetooth device. The attacker gets within range of the legacy device and exploits a vulnerability to gain access and extract sensitive information.

This is a significant attack that can be performed without notifying the device owner. Photos and videos can be extracted as well as confidential emails.

Bluetooth Special Interest Group ( #BT #SIG) is responsible for developing Bluetooth technologies and they have released security advisories and guidelines to help thwart this vulnerability. Firmware updates and patched were introduced to increase security postures of devices, making this a less common issue.

### Bluebugging

Bluebugging is when a threat actor gains full control of a Bluetooth device with permissions that allow for accessing and modifying data, making calls, sending text messages, and connecting to the internet.

This is one of the most severe form of Bluetooth attacks since the camera, microphone, and other peripherals can be controlled. The device can be effectively converted into a listening device to spy on the device owner.

The attacker discovers a vulnerable device within range before exploiting vulnerabilities that trick a device owner into believing they are making a connection to a trusted device. This may also come in the form of brute-forcing a PIN pairing request where the device owner is not prompted to connect. 

### Bluesmacking

Bluesmacking is a Denial of Service ( #DoS) attack that exploits the #L2CAP protocol for packet transfer. The attacker uses software to overwhelm the limited processing capabilities of the target device with a flood of packets.

Firmware updates and modern devices will filter these packets and reduce the effectiveness of these attacks.

