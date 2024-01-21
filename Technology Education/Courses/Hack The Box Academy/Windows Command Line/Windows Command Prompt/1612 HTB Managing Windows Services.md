# Managing Windows Services

Managing services is a key role of a system administrator. The ability to monitor and toggle services is a vital skill for both sysadmins and attackers. 

### Service Controller

Service Controller ( #SC) is a #Windows utility for managing and modifying host services. Alternatively we can use Windows Management Instrumentation ( #WMIC) and #TaskList, but working knowledge of all three of these tools is crucial.

#### Service Queries

When we use Service Controller to query services, we can learn the process state, process ID ( #PID), and service type. Additionally we will know which services are currently active and what drivers are installed on the system.

We can query services using the following command:

>sc query type= service

NOTE that the space between type= and service is required for this command to work properly.

If we want to query the service for Windows Defender, we can use the following command:

>sc query windefend

If we want to STOP a service like Windows Defender, we can use the following command:

>sc stop windefend

We will find however, that we do not have the permissions required to stop this service.

#### Stopping with Elevated Permissions

If we try to stop the Windows Defender service as administrator - we will still be denied. This is due to the fact that the service can only be stopped or started by the SYSTEM. It is important to know which services are controlled by the system and inaccesible to us. Trying to stop a service like windefend is an amateur mistake that would be easily detected by a system administrator or #IDS. 

If you want to try stopping a service, try stopping the print spooler with the following command:

>sc stop spooler

This should work successfully, but you may find that the service is still running. This is because many services can ignore our stop command regardless of our permissions or otherwise restart after they are stopped.

##### Starting Services

Starting a service is the same syntax and process as stopping them. It is worth noting that when a service is started by a user, there will be an intermediary state described as START_PENDING. This means that the service is initializing and may not be fully functional for the first few seconds. 

#### Modifying Services

Modification of services is a major point of exploitation for attackers and should be well understood by cybersecurity experts. An attacker can toggle a service to not initialize on startup, or modify the path variable so that it is accessible from a different point on the operating system. 

#### Configuring Services

When using SC to modify the configuration of services, we must supply the config parameter in our command. Please note that any changes made to a service are recorded in the Windows Registry and the Service Control Manager ( #SCM). 

##### Disabling Windows Update

If we want to disable the default windows updater, we need to consider two services related to this action:

- wuauserv - this is the Windows Update Service
- bits - this is the Background Intelligent Transfer Service ( #bits)

If we check the status of these services, you will find that bits is likely running but wuauserv is not (unless you are actively updating Windows). A good first step is to make sure both of these services have been stopped:

>sc stop wuauserv
>sc stop bits

Next we would want to modify the start type of each of these services. Disable them from initializing during startup with the following command:

>sc config wuauserv start= disabled
>sc config bits start= disabled

We can now verify that these services have been stopped by running the following command after a restart:

>sc start wuauserv
>sc start bits

If you would like to revert these changes, submit the following commands:

>sc config wuauserv start= auto
>sc config bits start= auto

 Deactivating these services from starting on system boot is a useful tool for an attacker - if the system is not updated automatically, this eventually leads to vectors for attack.

### TaskList

The #TaskList command list currently running processes on the target host. We can use the /svc parameter to designate only services in the output:

>tasklist /svc

This command will reveal all running services and their Process ID ( #PID).

### Net Start

Net Start is a command that functions similarly to the commands mentioned above. We can additionally use net stop, net pause, and net continue for more functionality.

### WMIC

Windows Management Instrumentation Command ( #WMIC) is a powerful tool that yields more information than any of the aforementioned command tools. Specific to this module, we can use WMIC to generate detailed information about the services running on the system:

>wmic service list brief

This will generate a brief list of services with information such as their Name, Process ID ( #PID), StartMode designation, State, and Status for every service on the system. 

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Windows Service Management](https://academy.hackthebox.com/module/167/section/1612 'HTB academy managing windows services module')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [018 File Systems](018%20File%20Systems.md)