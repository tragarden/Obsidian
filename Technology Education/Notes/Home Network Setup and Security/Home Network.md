# Home Network

### Router Setup

First, review your user manual for any #hardware before any attempts at integrating into your #network. After you have familiarized yourself with the literature, proceed to the next steps.

1. Use an #ethernet cable to connect your #modem to the #WAN port on your #router.
2. Use an additional ethernet cable to make a connection between your router's #LAN port to your computers' #RJ45 port for ethernet.
3. Use your #browser to navigate to 192.168.1.1 or 192.168.0.1 depending on what your user manual suggests.
4. Set your Default #Gateway to 192.168.1.1 or 192.168.0.1.
5. The default #subnet mask for this setup will be 255.255.255.0.
6. If using Wi-Fi, use #WPA-2 or #WPA-3 Personal Security.
7. If using an Access Point, connect from your Default Gateway's (Primary Router) LAN port to the LAN port on your Access Point (Secondary Router). The subnet mask must be the same on both devices.
8. Disable DHCP on your secondary router, as this will be handled by the Default Gateway (Primary Router).

### Wireless Setup

When setting up the #Wi-Fi for your home network, it is suggested that you use analyzer tools to determine the best layout for your devices. #Topology will be defined when you set up the hardware for your system. Placement of devices is determined during wireless setup.

#### Frequencies

There are two available bandwidths for transmitting wireless network communications, 2.4GHz and 5GHz. 2.4GHz signals have a lower #frequency and bounce off of walls and objects in the path of the signal.  This makes 2.4GHz signals better for communications in a location that has high interference or long range transmissions. 5GHz signals are faster and support greater #bandwidth, but due to the higher frequency they are not as flexible or as far-reaching. 

#### Channels

A #channel is a range of subdivisions for bands of Wi-Fi. We know that there is a 2.4GHz band, but this band is further sub-divided into smaller bands within this range.  This band is 100MHz wide, and each channel is 20MHz wide. This would allow for 5 alternative channels, or ranges of frequency. 

Use a Wi-Fi analyzer to determine what channels are being used within close proximity of your location. Figure out which of these channels experiences the least amount of traffic with preference for the highest available channel.

### Bridges

#### Repeater Bridges

Repeaters are used to facilitate a wireless connection between routers or a router and access point.  This is only used when the implementation of physical ethernet connections is not possible. When setting up, you will need to assign a static #IP on the Default Gateway (Primary Router) to the second router, which will set the local IP for the secondary router. This will allow you to access the configuration page for the second router / access point. Disable #DHCP on the secondary router and make sure the subnet mask is the same on both devices.

#### Client Bridges

Client Bridges are used to implement a second router, but instead of unifying them on one network, it will partition or subnet the networks so that devices on one subnet will not communicate with devices connected to the second router.
1. Connect an #ethernet cable from the LAN port on the Default Gateway to the WAN port on the secondary router.
-  On the second router, perform the following:
2. The Default gateway is the primary routers IP address, so the secondary router must be configured to a different local IP. If you have 192.168.1.1 as your default gateway, your secondary router should be set to 192.168.2.1 in order to subnet it as a different local network.
3. Unlike access points, you will need to ENABLE #DHCP, giving permission for the device to allocate IPs to devices that join this second network / #subnet.
4. DNS lookup will be the responsibility of the Default Gateway.

### Router Performance

There are a variety of third party software that can improve the performance of your router, although this may violate your terms of use or damage your hardware. Check out software like #DD-WRT, Tomato, or Merlin for ASUS products. 

### DHCP

A solid strategy for configuring a network is to **assign a static IP to your network hardware, and allow the hardware to assign IP addresses** to clients using #DHCP. It is very common for a network device to come with a default static IP, which is nearly always 192.168.1.1.

#### DHCP Settings

*If you try to connect two routers to your network,* keep in mind that they may get assigned the same IP if they have the same default settings. To avoid this, you will need to go to 192.168.1.1, access your router configuration page, and **change the DHCP settings to assign IP addresses within a different range than default. Lazy Admin suggest setting the range from 192.168.0.10 to 192.168.0.199. **

***If you choose the above configuration, make sure you assign your network devices with static IPs greater than 192.168.1.200. ***

#### DNS

#OpenDNS is a #CISCO service and server that offers fast connections and scans for malicious traffic. It keeps a list of malicious servers and blocks communications with them before you navigate to the page. OpenDNS is more secure and faster than 1.1.1.1, which is the next best option.

Choosing a DNS server is important, 1.1.1.1 is a common fast server to connect to that offers more privacy than others.

#### Additional Situations

When setting up multiple routers, you may experience conflict between your ISP provided router and your second router. In this case, you will likely need to put the ISP router in #DMZ / Bridge mode. 

When using an Access Point, you can disable the ISPs built-in access point if it has one.

Once you have completed these tasks, you can now safely connect the new router from the LAN port on the ISP device to the WAN/Eth0 port on the second router. Then you would connect the LAN port of your second router to your computer.

If you face confusion, see the original resource for these notes at [Lazy Admin](https://lazyadmin.nl/home-network/best-home-network-setup/ 'HELP IDK WHAT TO DO').


### Related:

- [Reddit: Networking for Beginners](https://www.reddit.com/r/HomeNetworking/comments/2905p1/networking_for_beginners/ 'The Reddit Post I Took Notes From')
- [Lazy Admin Network Setup](https://lazyadmin.nl/home-network/best-home-network-setup/ 'HELP IDK WHAT TO DO')
- [Wi-Fi Analyzer for Android](https://play.google.com/store/apps/details?id=com.farproc.wifi.analyzer&hl=en&pli=1 'Wi-Fi Signal Analyzer')
- [Net Surveyor for PC](https://nutsaboutnets.com/archives/netsurveyor-wifi-scanner/ 'Network Surveying Tool')
- [Network Security Guide](Network%20Security%20Guide.md)
- [Pi-Hole](Pi-Hole.md)
- [052 Troubleshooting Common Hardware Problems](052%20Troubleshooting%20Common%20Hardware%20Problems.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [131 Network Cables](131%20Network%20Cables.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)