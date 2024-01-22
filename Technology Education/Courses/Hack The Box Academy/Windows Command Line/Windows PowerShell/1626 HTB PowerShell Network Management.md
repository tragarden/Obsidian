# Network Management with PowerShell

### Querying the Network

#### IPConfig

The IPConfig command outputs standard #network information related to #DNS, #DHCP, #IP addressing, #subnet mask, and the Default Gateway. It will show whether the connection is based on #ethernet or #wireless connectivity. With the /all modifier we get even more information about the network interfaces, DHCP leases, and whether the connection is dual-homed.

Use the following command to output  detailed information about the host network:

>ipconfig /all

#### ARP

Address Resolution Protocol ( #ARP) is used to translate IP addressed to physical addresses and can reveal whether or not a host has sent or received communications from other devices on the network.

We can output detailed information about our ARP communications with the following command:

>arp -a

#### DNS 

Domain Name Server ( #DNS) reads the #URL information that we submit into our browser and retrieves the correct IP address from a DNS server that stored this information. We can use the #nslookup tool to resolve addresses.

We can resolve the IP address of the #Domain Controller for Greenhorn corporation with the following command:

>nslookup ACADEMY-ICL-DC

#### NetStat

We can use the NetStat tool to view all connections and available ports with the following command:

>netstat -an

### PowerShell cmdlets

There are powerful cmdlets available to #PowerShell that can help us manage our network:

| cmdlet             | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| Get-NetIPInterFace | outputs the properties of available network adapters                   |
| Get-NetIPAddress   | outputs the IP configurations of network adapters. similar to IPConfig |
| Get-NetNeighbor    | outputs the neighbor entries from the ARP cache. similar to arp -a     |
| Get-NetRoute       | outputs the route table. similar to IPRoute                            |
| Set-NetAdapter     | outputs Layer 2 information like #VLAN ID and #MAC addresses           |
| Set-NetIPInterface | configures the interface #DHCP status and #MTU                         |
| New-NetIPAddress   | Generates or changes an IP address                                     |
| Set-NetIPAddress   | configures a network adapter                                           |
| Disable-NetAdapter | disables network adapters                                              |
| Enable-NetAdapter  | enables network adapters and allows network connections                |
| Restart-NetAdapter | restarts a network adapter after changes have been made                |
| Test-NetConnection                   | diagnostic test involving #ping, #TCP, route tracing, and more                                                                       |
#### Get-NetIPInterface

The Get-NetIPInterface cmdlet will output all the available interfaces on our host. This output can be redundant if we have both #IPv4 and #IPv6 addresses enabled on our host. Some aliases of note in this output are the ifindex and InterfaceAlias properties. 

#### Get-NetIPAddress

The Get-NetIPAddress outputs information about the index, aliases, #DHCP state, interface type, and more. These results are comparable to the IPConfig command used earlier in the module. 

#### Set-NetIPInterface

We can use the Set-NetIPInterface cmdlet to configure the status of our DHCP interface.

Change the status of the DHCP interface with the following command:

>Set-NetIPInterface -InterfaceIndex 25 -Dhcp Disabled

#### Set-NetIPAddress

We can now used the Set-NetIPAddress cmdlet to set a net IP address with the following command:

>Set-NetIPAddress -InterfaceIndex 25 -IPAddress 10.10.10.10 -PrefixLength 24

We now have a newly assigned IP of 10.10.10.10 and a #subnet mask of 24. 

#### Restart-NetAdapter

Now we can restart our network adapter with the following command:

>Restart-NetAdapter -Name 'Ethernet 3'

This command will only have output if there is an error.

#### Test-NetConnection

Now we can utilize the Test-NetConnection cmdlet to see if our changes persisted with the following command:

>Test-NetConnection

Everything that we modified throughout this module should be shown as properly configured in this output.

### Remote Access

There are a variety of methods for remote access on windows machines and PowerShell such as #SSH and #RDP. 

#### Enabling SSH

#SSH connections are established on #Windows hosts and servers using #OpenSSH since 2018. 

We can use PowerShell to enable SSH on a target host via the Add-WindowsCapability and Get-WindowsCapability cmdlets using the following series of commands:

>Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'

>Add-WindowsCapability -Online -Name OpenSSH.Client\~\~\~\~0.0.1.0

>Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'

>Add-WindowsCapability -Online -Name OpenSSH.Server\~\~\~\~0.0.0.1

>Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'

#### Starting and Configuring SSH

After installing SSH and verifying install is successful, we can employ the Start-Service and Set-Service cmdlets to configure our SSH services with the following commands:

>Start-Service sshd
>Set-Service -Name sshd -StartupType 'Automatic'

#### Connecting via SSH

Connect to the SSH client with the following command:

>ssh htb-student@10.10.10.10

This will open a Command Prompt ( #CMD) session - we can then type the command 'powershell' to initiate a #PS session.

### Linux Connection

The method for connecting to a windows machine via SSH is the same when connecting from a #Linux machine.

### Enabling WinRM

#Windows Remote Management ( #WinRM) is another method for remotely accessing a Windows machine. In this case, we will need to enable the WinRM service similar to how we enabled SSH. Additionally we will need to allow WinRM to pass through Windows Defender #Firewall on both inbound and outbound communications. Lastly, we will have to grant administrator rights to local users for them to be able to accept these connections.

This interface can become succeptible to attack unless network administrators perform the proper hardening techniques. They will need to configure a whitelist of TrustedHosts, configure #HTTPS for transport, and to join all the Windows hosts with the Active Directory Domain and use #Kerberos authentication methods.

Here is a list of steps to ensure we are enabled:

- Allow WinRM in Defender Firewall.
- Enable the WinRM service.
- Grant Administrator rights to local users.
- Whitelist all devices in TrustedHosts.
- Configure HTTPS for tansport.
- Join all hosts to Active Directory Domain Controller.
- Use Kerberos authentication

Use the following command to configure WinRM:

>winrm quickconfig

### Testing Remote Access

We can perform various tests with the Test-WSMan cmdlet by sending a request to determine if the WinRM service is running. 

Test for unauthenticated access with the following command:

>Test-WSMan -ComputerName "10.10.10.10"

This should output that the WinRM service is running on the target host.

We can now test for authenticated access with the following command:

>Test-WSMan -ComputerName "10.10.10.10" -Authentication Negotiate

This should output that the service is running and the current version of the operating system ( #OS).

### Remote PowerShell Sessions

We can use the Enter-PSSession cmdlet to initiate a PowerShell session on a remote Windows target from a Windows host or Linux host. Luckily, PowerShell is now available on Operating Systems other than Windows.

Run the following command to establish a PowerShell session on the remote target host:

>Enter-PSSession -ComputerName 10.10.10.10 -Credential htb-student -Authentication Negotiate

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Network Management](https://academy.hackthebox.com/module/167/section/1626 'HTB academy PowerShell network management guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [016 Windows Network Technologies](016%20Windows%20Network%20Technologies.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [121 Introduction to IP](121%20Introduction%20to%20IP.md)
- [0304 HTB Network Layer](0304%20HTB%20Network%20Layer.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)
- [Network Security Guide](Network%20Security%20Guide.md)