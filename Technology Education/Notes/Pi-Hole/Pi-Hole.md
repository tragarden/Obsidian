# Pi-Hole with Raspberry Pi

### What is a Pi-Hole?

A #Pi-Hole is a device that blocks ads across your entire #network via a single-board #Linux based Raspberry Pi (or other) computer.  #DNS queries from your network will be filtered through the pi, which will block ads, #malware, and tracking methods. If you DO NOT have a Raspberry Pi device, you can use a #Docker container or a Network Attached Storage ( #NAS) device.

### Materials

You will need a few parts to set up a Pi-Hole: 

- Raspberry Pi device with an #Ethernet port as wireless connectivity is not used with Pi-Hole.
- #microSD card with at least 4GB of storage - you will want to opt for a high quality card capable of fast data transfer so #DNS lookups don't slow down your network.
- Raspberry Pi Imager software is used to format your #microSD card and install an #OS onto your Pi. 
- A kill-switch from a company like #Canakit is useful for toggling power.

### Process

#### Imager 

Download the Raspberry Pi #Imager and insert a microSD card so your machine can format the card. Once the R-Pi reads the microSD card, you will be prompted to install the OS of your choosing from the imager. Choose the option "Raspberry Pi OS Light (64-bit)" as you will not need access to the #Raspian #GUI. 

From the Imager window: 

1. Open the settings menu.
2. Check the box for 'Set Hostname' and choose a name for your Pi-Hole.  
3. Check the box for 'Enable SSH' and select 'Use Password Authentication'.
4. Set up credentials for accessing your Pi-Hole via #SSH.
5. 'Set Locale Settings' is optional and sets your time zone and keyboard layout.
6. Click 'SAVE'.
7. Click 'WRITE' and the OS will be written to your R-Pi within 3-4 minutes.

#### Initial Boot

Plug in the power cable and the ethernet cable, then turn on the device. When you do this, your device will retrieve an #IP address from your network #DHCP server. You will need to know which IP has been assigned to your device, and this can be accomplished in two ways.

The first method entails checking the DHCP lease table for your router, where you will be able to see all active leases for your #LAN #network.  

The second method entails using the command line ( #CLI) on your Raspberry Pi to enter the command '> ip a' to reveal the IP address of your device. 

#### SSH

Once you identify the IP address of the device, open #Windows command prompt and SSH to your Pi-Hole via: 

>'ssh piHostName@IPaddress'

#### Update the OS

You will need to update all of the packages on your OS, which should take about 4-5 minutes via:

> 'sudo apt update && sudo apt upgrade -y'

#### Setting Static IP

We need to make sure that the Raspberry Pi device does not get a new IP assignment from the #DHCP server. You can either set up a DHCP reservation on your #router, or define a static IP on the Raspberry Pi device. 

##### DHCP Reservation

DHCP Reservations mate a designated IP to a designated #MAC address.

##### Static IP

To set a static IP for your device, you will need to access your 'dhcpcd.conf' file and modify it. To open this file, use the command:

>'sudo nano -w /etc/dhcpcd.conf'

Once you have the file opened, scroll down until you find a section with the title "Example Static IP Configuration". These lines are commented out, so you will need to uncomment certain lines to submit your own network information and IP address.  The lines you will uncomment include: interface, static ip_address, static routers, and static domain_name_servers.  Supply the correct credentials and set your 'static routers' to your #gateway #IP and set two #DNS servers.

>press CTRL + X to exit, then press 'Y' and ENTER to save.

>'sudo reboot' to implement the new network settings

#### Install Pi-Hole

After setting the static IP and rebooting the device, make sure you are connected to the new statically assigned IP address. Once you have established connection to the static IP, run the following command to run the installation wizard for pi-hole #software.

> 'curl -sSL https://install.pi-hole.net | bash'

Navigate through these prompts until you get to the window asking you to verify that the address shown is the address for the pi-hole. There will be several windows begging you to make sure that your IP is set statically and matches the IP presented in the setup wizard. If the wrong IP is depicted in these windows, you need to cancel the process and reboot the device.

##### Upstream DNS

Choosing an upstream DNS provider will designate the server that the pi-hole will use for initial DNS lookups.  The guide suggests using #Unbound to make your own DNS lookups from the primary root domain servers for the Internet.  This is set up later, and for this example the author chooses to use #CloudFlare.

You do not have to use Unbound for selecting your DNS server. When selecting an Upstream DNS, consider that not all of these DNS providers offer the same routing and filtering.  Some may have more intense content and #malware filtering than other providers, so do your homework and decide which you would prefer to use.

##### Block Lists

The install wizard will ask if you would like to use the default block list from StevenBlack. The author suggest installing and using the StevenBlack block list.  There are more block lists available from the pi-hole community. 

##### Admin Web Interface

The Admin Web Interface is what allows us to configure the device, so select YES and install this.

##### Query Logging

Query logging will record and monitor your DNS lookups - typically we allow this logging, but if you're worried about security and having your DNS logged, select NO.

##### Privacy Level

For this tutorial, the author doesn't go into great detail about this window, merely suggests to go with the default setting of 'Show Everything'.

#### Logging In

##### Change Default Credentials

The Pi-Hole Admin GUI will come with default credentials that your NEED to change.  You can use the following command to log in and modify these credentials:

>'pihole -a -p'

##### Pi-Hole GUI

Once you've established your own login credentials, you are ready to log into the Admin GUI through your #browser. To do so, you will type in the IP address of your device into you #URL bar followed by '/admin' to access the GUI as seen below:

>'\http://192.168.xxx.xx/admin'

#### Pi-Hole Dashboard

The dashboard provides colorful boxes with statistics related to your DNS queries and the total amount of blocked domains and on the left is a menu.

#### Query Log

The Query Log shows you the list of DNS Queries you've made with the most recent submissions at the top of the list. This includes a list of accepted and blocked domains with the option of adding any of these entries into the #whitelist or #blacklist.

##### Adlists

There are many blocklists available and it is important to remember that more is not always better. When you increase the amount of sites within your blacklist or add too many filters, eventually you will encounter issues with your applications breaking and the internet intermittently working. 

The author recommends #Firebog as a resource for acquiring block lists. Browse the lists they have available and add them to your Pi-Holes catalogue of sites to block. 

Once you have  added all the block lists you intend to, you will need to update Gravity - the list of all blocked domains.

##### Gravity

#Gravity is the list of all blocked domains for your pi-hole.  After you add blocklists from a site like the Firebog, you need to navigate to 'Tools > Update Gravity' to add your new list of URLs to the designated block list.

#### Disabling Blocking

Occasionally blocked URLs result in applications breaking or an inability to access certain sites or data. You will need to log into the Admin GUI via browser to disable blocking.  This can become annoying and time consuming because you will need to reenter credentials to every pi-hole you have, every time you need to block filtering.  

##### Scripting

We often need to log into our Admin GUI to disable blocking when something on our network is no longer working properly.  This can be scripted and hotkeyed using the #URL:

>\http://192.168.xxx.xx/admin/api.php?disable=300&auth=PASSWORDHASH

To obtain the PASSWORDHASH indicated above, look in the file /etc/pihole/setupVars.conf by logging into your Raspberry Pi directly or via SSH, then entering the following command:

>'cat /etc/pihole/setupVars.conf | grep WEBPASSWORD'

This command will reveal your hashed password, you can now append this to the end of your URL and run the script within your browser. When the script runs, this will disable blocking for 5 minutes. This can be used to disable multiple pi-holes.

#### Teleporter

The Teleporter tab lets you back up your Pi-Hole settings so that you can apply these configurations to other pi-hole devices on your network, or re-configure your main device if you make changes you are not satisfied with.

### Unbound

#Unbound is an app that bypasses the typical third-party upstream #DNS providers like Google and CloudFlare to directly query the DNS #root #domain servers for any uncached requests. You can install unbound with the command:

>'sudo apt install unbound -y'

After successful install, you will need to open the .conf file for unbound and the pi-hole. We must append a large block of text to these documents to configure pi-hole and unbound.

>'sudo nano -w /etc/unbound/unbound.conf.d/pi-hole.conf'

Below is the link to the text that must be added to the file:

[Pi-Hole Documentation for Unbound](https://docs.pi-hole.net/guides/dns/unbound/ 'Documentation for Pi-Hole with Unbound')

Save the changes to the file and then restart the Unbound service via:

>'sudo service unbound restart'

then

>'sudo service unbound status'

which should indicate that Unbound is running and active.

To ensure that Unbound is working, we can send a DNS query to the port and IP designated within the Unbound configuration file using the command:

>'dig crosstalksolutions.com@127.0.0.1 -p 5335'

which should yield a status of NOERROR with a retrieved IP address for crosstalksolutions.com.

#### Using Unbound with Pi-Hole

If you were successful with the last section of the setup, then you are ready to change the DNS settings for your Pi-Hole so that Unbound is set as your default DNS provider.

1. Log into the Pi-Hole Admin #GUI.
2. Go to Settings > #DNS.
3. Uncheck the box next to CloudFlare (or other provider).
4. Add a new custom entry for Unbound 

>127.0.0.1#5335

5. Save and exit. Congratulations.

You can test ad-blocking by using a tool such as this: [d3ward on GitHub](https://d3ward.github.io/toolz/adblock.html 'A useful tool for testing blocking.')

#### TailScale

#TailScale provides a personal #VPN for all of the devices on your network. It also allows you to choose what DNS server you would like to use.

Install TailScale by connecting via SSH to the Raspberry pi and running the following command:

>'curl -fsSL https://tailscale.com/install.sh | sh'

Since we are using our Pi-Hole as a #DNS server, we have to make sure that the device does not try to use itself as the upstream for queries. This can be avoided with the command:

>'tailscale up --accept-dns=false'

Once you do this and install TailScale onto your other devices, you need to set your Raspberry Pi as your dedicated DNS server.

Go to the TailScale Admin Console, then head to the DNS page to enter your Pi-Hole's TailScale IP address from the 'Machines' page of the console. Make SURE you toggle 'Override Local DNS' after adding the Pi-Hole TailScale IP. 

Head back to the 'Machines' tab and make sure you 'disable key expiry' on all Pi-Holes. If you do not do this, you will experience DNS interruptions when TailScale requires you to re-authenticate your networked machines.

The above steps ensure that when you log in to TailScale, the Pi-Hole will automatically be used for DNS Queries. 

Sharing Nodes is a feature of TailScale that allows you to invite your friends to your subnet, where they can use your Pi-Hole to block ads on their own devices.

#### Updating Pi-Hole

SSH into your device and run the following command:

>'sudo pihole -up'

This should be done monthly, and you can set a #chronjob to schedule this instead of manually doing it.

### Related:

- [CrossTalk Solutions Pi-Hole Guide](https://www.crosstalksolutions.com/the-worlds-greatest-pi-hole-and-unbound-tutorial-2023/ "CrossTalk Solutions Pi-Hole Guide")
- [CanaKit Kill Switch](https://www.canakit.com/raspberry-pi-4-on-off-power-switch.html 'Kill Switch for Raspberry Pi')
- [Pi-Hole Block Lists](https://avoidthehack.com/best-pihole-blocklists 'Suggested Block Lists')
- [Firebog Block LIsts](https://firebog.net/ 'The Firebog')
- [Commonly Whitelisted Domains](https://discourse.pi-hole.net/t/commonly-whitelisted-domains/212 'Common Whitelisted Domains')
- [122 Network Devices](122%20Network%20Devices.md)
- [124 Network Services](124%20Network%20Services.md)
- [227 Network Types](227%20Network%20Types.md)