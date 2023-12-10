# VPN  
  
A Virtual Private Network ( #VPN ) uses a secure channel of communication to connect to a private network in order to access resources as if we have a direct connection to another machine. These networks provide encryption and a slight boost in security.  
  
All data sent will pass through a VPN concentrator that facilitates the connections, encryption, and privacy of the network.  
  
#SSL VPNs is integrated into a web browser so that the user does not need an application to log into the network - they are able to connect through the browser to access things such as email and the intranet of the organization.  
  
#Client-based VPNs use applications or software to access organization resources as if they were directly connected to the network. They may connect to the full set of resources on the target network, or a segmented portion granting limited access.  
  
VPNs have a variety of uses as different users have different reasons for using them. Some of these uses include:  
  
1. Connecting to a different region to obscure location data.  
2. Disuising your IP address.  
3. Connecting to an organization's server.  
4. Accessing resources on a remote network.  
NOTE: Please realize that VPNs still allow data logging and are NOT an effective way at blocking third parties from seeing your internet data.  
  
When connecting to HTB modules, you should consider this a hostile and dangerous environment - never connect to these modules with your own hardware. It is strongly advised that you ONLY use the provided VMs to access the remote machines as they are intentionally setup to host security threats.  
1. Connect from a Virtual Machine ONLY.  
2. Disallow password authentication when using #SSH.  
3. Lockdown any web servers you are using.  
4. Do not provide sensitive information when using the modules.  
  
The command used to connect via open VPN on HTB Academy is:  
  
> sudo openvpn user.ovpn  
  
Where sudo is used in place of Administrator, 'openvpn' indicates the client we are using, 'user.ovpn' is the file that holds the HTB VPN key we have downloaded. Ifconfig will show that we have a 'tun adapter' once we are successfully connected.  
  
If successful, you will see the line "Initialization Sequence Completed".  
  
The following command shows us any network that we are now connected to.  
  
> netstat -rn  
  
This module includes troubleshooting guides at the end.