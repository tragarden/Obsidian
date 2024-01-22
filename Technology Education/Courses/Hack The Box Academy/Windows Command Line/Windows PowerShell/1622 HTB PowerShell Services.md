# PowerShell Services

#Windows Services are background components that maintain processes that allow for applications to run. They run as a single instance with the capability of running multiple processes. The fall under the categories of Local, Network, or System. Services can have a variety of states such as Running, Stopped, Paused, Automatic Start, Manual Start, or Delayed Start. Misconfiguration of services are a vulnerability and privilege escalation vector.

We use the PowerShell module Microsoft.PowerShell.Management that contains the built-in cmdlets we have been using thus far. 

Run the following command to get a list of commands relevant to services:

>Get-Help \*-Service

#### Get-Service

We can output a list of the services into Format-Table (ft) with the following command:

>Get-Service | ft DisplayName, Status

Then we can run the following command to get a total count of the services:

>Get-Service | measure

We can see that a total of 321 services are on the system in the example. This is a very large list, so being able to pare it down would be very helpful.

### Precision Searching

In the last example we had 321 services listed - let's narrow our focus to Windows Defender to improve the readability of our search and reduce the output content. 

Search for Defender related services with the following command:

>Get-Service | where DisplayName -like '\*Defender*' | ft DisplayName,ServiceName,Status

In the example given, we see that four services relevant to Defender populate the output. One of these services is toggled to Stopped, which is problematic. Lets restart it with the Start-Service cmdlet.

#### Start-Service

We identified that the service WinDefend's status was set to stopped. 

We can run the following command to start the WinDefend service:

>start-service WinDefend

As long as there was no errors in the output, this should have successfully started the WinDefend service. 

##### Verifying 

We can now run the following command to ensure that our use of Start-Service cmdlet was successful:

>get-service WinDefend

#### Stop-Service

If we see any unusual or unsavory services running on our machine, we are able to stop them in a similar way to starting them with the Stop-Service cmdlet.

Use the following command to stop the unusual 'Spooler' service from running:

>Stop-Service Spooler

Then verify that it has stopped with the following command:

>Get-Service Spooler

#### Set-Service

With the Set-Service cmdlet we are able to change the operating status of a service. This means we can change the startup status of our suspicious Spooler service.,

Use the following commands to change the startup status of the Spooler service:

>get-service spooler | Select-Object -Property Name, StartType, Status, DisplayName
>Set-Service -Name Spooler -StartType Disabled
>Get-Service -Name Spooler | Select-Object -Property StartType

Note that you should be operating as an administrator when you change service configurations like this.

#### Remove-Service

Note that Remove-Service only works if you are using PowerShell 7. If you are interacting with older versions of PowerShell, you will need to use the sc.exe tool.

### Remote Services

To interact with and manage remote services, we will need to use the -ComputerName parameter to designate the remote host we wish to modify. 

Use the following command to query a remote host with the name ACADEMY-ICL-DC:

>get-service -ComputerName ACADEMY-ICL-DC

This returned a lot of output - we can filter this output to be more readable with the following command:

>get-service -ComputerName ACADEMY-ICL-DC | Where-Object {$\_.Status -eq "Running"}

#### Invoke-Command 

The Invoke-Command cmdlet tells PowerShell that we will run a command locally or remotely. It is often useful for running commands on a remote host.

The -ScriptBlock modifier parses the intended command placed within curly braces.

Use the following command to see if the WinDefend script is running on our target host:

>invoke-command -ComputerName ACADEMY-ICL-DC, LOCALHOST -ScriptBlock {Get-Service -Name 'windefend'}

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Managing Services](https://academy.hackthebox.com/module/167/section/1622 'HTB academy PowerShell managing services guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [124 Network Services](124%20Network%20Services.md)
- [0726 HTB Service Scanning](0726%20HTB%20Service%20Scanning.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)
- [1612 HTB Managing Windows Services](1612%20HTB%20Managing%20Windows%20Services.md)