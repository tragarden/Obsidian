# Modern Bluetooth Attacks

Modern attacks can be perpetrated against modern devices with firmware upgrades. Attacks like BlueBourne, KNOB, and BIAS can be problematic even on new devices.

### BlueBourne

BlueBourne was discovered in 2017 as a substantial threat where connections are exploited to gain full control of the target device. These attacks pose significant threat to IoT devices, TVs, watches, and medical devices although devices like PCs and cars are at risk as well. 

This attack corrupts a device without requiring pairing and can be performed with discoverable mode disabled. Armis labs discovered eight zero-day exploits related to this attack style. 

Hackers are able to execute code remotely through this attack style. It is considered to be a severe form of attack and highlights the flaws and vulnerabilities associated with the technology.

### KNOB

Key Negotiation of Bluetooth ( #KNOB) is an exploitation of the Bluetooth standard encryption used with connections. This was discovered in 2019 by Daniele Antonioli, Nils Ole Tippenhauer, and Kasper Rasmussen. 

An encrypted link is used for Bluetooth connections, where an encryption key is shared. When the connection is configured, the two devices agree on a length for the encryption key. This communication is intercepted by a threat actor who sets the key length to the minimum requirement of one byte. The attacker then cracks this key via brute force methods.

All devices are vulnerable to KNOB attacks as they do not require knowledge of keys shared previously. You can protect against these attacks by updating your software and firmware to the newest iterations. This will increase the minimum encryption keys to seven bytes by default.

### BIAS

Bluetooth Impersonation AttackS ( #BIAS) were discovered in 2020 by the same people that discovered the KNOB attacks. This attack is an exploitation of the Bluetooth Basic Rate and Enhanced Data Rate ( #BR/EDR) or Bluetooth Classic pairing and connection process. 

The attacker authenticates themselves by connecting to the target device and impersonating a device that is already paired with the target. This attack does not require mutual authentication as long as the attacking device verifies the connection. Once established, the attacker and read and modify data on the target device.

This attack can be perpetrated against any device using the #BR/EDR protocols. These attacks can be mitigated through updates of firmware on Bluetooth Classic devices.

### Mitigation

Here is a short list of ways you can protect your devices and mitigate these attacks:

- Update Devices 
- Disable Bluetooth when not in use
- Enable Device Pairing Authentication
- Limit Device Visibility - set devices to invisible or undiscoverable
- Use Caution in Public - do not accept pairing when in crowds

