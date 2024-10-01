# Home Network Setup

Setting up the home network involves any device that needs an internet connection and key components like a #modem and  a #router if you choose to use one.

### Beginning

The first step in setting up a home network is to identify the location in your house where the coaxial or fiber optic cable from your Internet Service Provider is accessible. This step assumes that you have an active account and subscription with an ISP like Xfinity.

Once you have located your signal source, connect this to your modem by screwing the nut on the cable end onto the device. Once the cable is secured, you can plug in the power supply to the device, and then plug the power cable into an available outlet.

The device should boot, which may take several minutes. Pay attention to the status indicator lights on the front of the modem. Once they are all illuminated, you should be able to move onto the next step.

### Initial Setup

Once you have ensured that all status lights indicate that the modem is functioning, you can then look on the case of the device to find either a QR code or credentials for login. Once you find these credentials, you can then connect to the modem with your device of preference.

#### Logging In

Once you have connected to the device via wireless connection, you can then navigate to one of the following addresses in your browser:

- 168.192.0.1
- 168.192.1.1

These are the default assigned IP addresses for most devices. Submitting these as a URL request in your browser should take you to the homepage for your modem. If these do not take you to the homepage, review the available literature for your device.

#### Default Credentials

On the homepage you will be prompted to enter the default credentials for the admin account. Typically, these credentials are as follows:

- Username: admin
- Password: password

If you enter these credentials but are not authenticated, refer to the documentation for your modem.

Once you have logged in successfully, it is advised that you change the default credentials. If a threat actor can determine the device you are using, they can simply web search the associated default credentials and log in as an administrator. Some device homepages will prompt you to change this password.

When creating new credentials, it is advised that you change the default username as well as the default password. Changing the default username will make brute force attacks directed towards your device more difficult.

Choosing a password that uses an unpredictable combination of numbers, symbols, uppercase, and lowercase characters is advised and often enforced by the device standards. Make sure you choose a strong password. Using a password generating application or web app is useful. Using a password manager such as 1password to generate and remember your password can make this process much easier.

#### Basic Setup for Arris SBG10

Once you have accessed the administrator console for the Arris SBG10 and created new credentials, you will be presented with a page for basic device setup. This page will grant you options for designating a Host Name, 2.4GHz network SSID and Security Key, 5GHz network SSID and Security Key, and Wi-Fi Protected Setup ( #WPS) configuration.

#### WAN Settings

The WAN settings allow you to enable #DHCP for the device. What this means is that the device will send a request to your ISP requesting IP address assignment. In my case, I left all of these assignments as default to be managed by the ISP.

### LAN Settings

On the #LAN settings page, there are several headers:

- LAN IP Settings
- DHCP Server Settings
- DNS Override
- NAT
- UPnP

#### LAN IP Settings

Under the header for LAN IP, you will see the fields to submit your own IP Address and Subnet Mask. 

##### IP Address

For the IP Address, I designated an IP with the following format: 10.x.x.x. 

##### Subnet Mask

For the subnet mask, I chose the default value 255.255.255.0 which allows you to have 254 devices connected to this modem.

#### DHCP Server

I chose to enable DHCP server, which means that the modem will allocate local IP addresses to the devices that connect to it. Although the router I use can also do this, I chose to let the modem manage DHCP addressing because it can handle ethernet devices AND wireless devices - the router is strictly limited to ethernet.

##### IP Range

I chose to create a range of available IP addresses between 10.x.x.2 and 10.x.x.69 that can be allocated to devices that join the network. 

##### DNS Override

I chose to enable DNS Override, making my Primary DNS server 1.1.1.1 (CloudFlare) and my Secondary DNS 8.8.8.8 (Google).

### Client List

For the client list - I reserved three IP addresses - one for my PC, one for my router, and one for my Raspberry Pi hosting pi-hole.



#### UPnP

***NOTE: I DISABLED UPNP WHICH MAY CAUSE ISSUES WITH DEVICES CONNECTING AND IDENTIFYING EACHOTHER***

10.69.5.1
