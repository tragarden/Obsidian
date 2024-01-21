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

