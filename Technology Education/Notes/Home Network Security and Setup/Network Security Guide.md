 # Network Security

### Securing Routers

#### Router Selection

A first consideration when focusing on your #network #router is to avoid using any devices provided by your #ISP. You should avoid these devices because they have stored credentials for support reasons - a technician or attacker with these default support credentials can access your network. These devices are less configurable and do not get updates as frequently as third party devices.

#### Default Credentials

When you install your network #hardware you will need to reconfigure the default credentials for username and password. This is something you should perform on each device on your network. It's a major vulnerability to keep default controls, as anyone can find out the default credentials and gain administrative privileges within your network.

#### Updating Firmware

Each device on your network will eventually fall prey to exploited vulnerabilities. Update the hardware #firmware often so old vulnerabilities are eliminated and you have the most current security features for your device. 

#### Remote Access

Many devices allow for access to the management interface for your router from the internet.  This is a vector for attack, so it is wise to disable this ensuring that the device can only be managed locally.

#### DNS Server Selection

You #ISP will provide default #DNS servers to perform #URL lookups, usually prioritizing a server close to your physical location. Choosing a DNS server that offers security features is preferable to using the default server.

#OpenDNS is a #CISCO server that redirects you to an ideal server while also protecting you from #malware, #phishing attacks, #botnet attacks, and other malicious agents. OpenDNS works up to 3 times as fast as DNS servers assigned by your ISP. Configuring your router to choose a secure DNS server will increase security across your entire network.

#### Firewalls

A #Firewall is used to prevent unknown or suspicious traffic from entering your network. The best choice for a firewall is a hardware solution, such as a dedicated firewall device or a router with built-in firewall. DO NOT disable your firewall, but rather disable blocking on a specific #port or manage your port forwarding.

### Wireless Network Management

#### Passwords

Changing your default credentials is vital and a point that is worth reiterating. Default hardware credentials are easily determined using online resources. The best method of protecting yourself is to use secure passwords generated and maintained by a password management software.

#### Wi-Fi Protected Setup

Wi-Fi Protected Setup ( #WPS) is a method of connecting to a wireless network by pushing a physical button on the #router or by submitting a 4-digit code. When the WPS button is pressed, a broadcasted invitation to join the network is transmitted by the device.  This broadcast remains active for several minutes, allowing a potential attacker to intercept the signal and join the network without entering #security credentials. WPS can additionally be activated by submitting a 4-digit #PIN to the router, which is easily cracked. Active WPS is a security threat and should be disabled in most cases.

#### Default Network SSID

When you use your hardware to generate a new network, it uses a preconfigured wireless network as default. This default network name ( #SSID) and password are often located on the back of the device on a label. Attackers may be able to recognize the default name and determine the make and model of your device. This would allow them to find the default password associated with it and any known vulnerabilities associated with the device.

#### WPA3

A note about #WPA-3 to consider is that if your network device has this protocol, you will need all associated devices to also support this standard.

#### MAC Filtering

#MAC filtering uses the known identifiers on devices on your network to limit what devices have access to the network. You can set your router to only permit known devices onto the network. This must be done manually and is a time-consuming process, and while these MAC addresses can be spoofed, this is a very strong improvement to your home security. Using a tool such as [Advanced IP Scanner](https://lazyadmin.nl/go/program/advanced-ip-scanner/ 'Tool for Identifying MAC Addresses').

#### Guest Network

A guest network is a good way to keep visitors to your network in a state of quarantine, preventing any viruses they may have on their device from infiltrating your network and infecting your other devices. Lazy Admin has an article explaining how to set up a guest network [here](https://lazyadmin.nl/home-network/howto-setup-unifi-guest-portal/ 'Guest Network Setup Guide').

### Securing Clients

#### Updating Clients

Make sure that all the devices on your network are regularly updated. While it is important to keep your network devices updated, the devices that connect to them are just as important.


#### VPN

A Virtually Protected Network ( #VPN) creates a tunnel of #encryption for your data transmissions, giving you anonymity on the internet. It is important to use a VPN if you frequently connect to public or other insecure networks.

#### Anti-Virus

Software to defend against viruses and other malware is something that should be actively used on your devices. Lazy Admin recommends using #Sophos.

#### Email Vulnerabilities

If your e-mail accounts are compromised and sites have leaked your data in the past, attackers can determine your credentials and personal information. [HaveIBeenPwned](https://haveibeenpwned.com/ 'Check if your email is compromised here')is a good resource for identifying any times your email may have been leaked by a compromised website.


### Related:

- [Network Security Guide](https://lazyadmin.nl/home-network/home-network-security/ 'Study Resource for these Notes')
- [Wi-Fi Analyzer for Android](https://play.google.com/store/apps/details?id=com.farproc.wifi.analyzer&hl=en&pli=1 'Wi-Fi Signal Analyzer')
- [Net Surveyor for PC](https://nutsaboutnets.com/archives/netsurveyor-wifi-scanner/ 'Network Surveying Tool')
- [Home Network](Home%20Network.md)
- [Pi-Hole](Pi-Hole.md)
- [052 Troubleshooting Common Hardware Problems](052%20Troubleshooting%20Common%20Hardware%20Problems.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [131 Network Cables](131%20Network%20Cables.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)