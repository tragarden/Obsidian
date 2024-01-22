# Windows Event Log

Windows Event Log is a method of monitoring events on our machine or network and then organizing them in a way to help analyze network activities. This can be used defensively or offensively. 

#### Events

An event is any identifiable occurrence on the systems hardware or software that can be classified or otherwise observed by the overarching system. 

Common examples of events include:

- User Input - moving a mouse, pressing a key, or interacting with a peripheral.
- Application based - updates, crashes, memory utilization, processor usage.
- System based - total uptime, updates, driver activity, and logins.

#### Microsoft Defined Event Logging

#Microsoft defines Event Logging as "a standard, centralized way for applications to record software and hardware events."

The Microsoft Event Log has an #API integration with applications so they are able to manage their own logs individually. 

### Event Log Categories

| Log Category | Description                                                                                              |
| ------------ | -------------------------------------------------------------------------------------------------------- |
| System       | Records Windows system and component events like services failing to start.                              |
| Security     | Records login data, failed login attempts, file modification.                                            |
| Application  | Records software activity like starting, stopping, and failed starts.                                    |
| Setup        | Records activity from when Windows was installed or Active Directory in the scope of domain controllers. |
| Forwarded    | Records of events from other hosts on the local network.                                                                                                         |
### Event Types

| Severity    | Level | Description                                                       |
| ----------- | ----- | ----------------------------------------------------------------- |
| Verbose     | 5     | Progress or success messages.                                     |
| Information | 4     | System events that did not cause significant issues.              |
| Warning     | 3     | A problem warranting the attention of a system administrator.     |
| Error       | 2     | Related to system or services that doesn't pose immediate threat. |
| Critical    | 1     | A significant issue of immediate concern that could lead to system instability if not addressed.                                                                  |
### Event Elements 

- Log name - System, Security, or Application.
- Event Date and Time 
- Task Category - type of event recorded.
- Event ID - unique identifier for the event.
- Source - name of the application the event originated from.
- Level - Severity level of either Information, Error, Verbose, Warning, or Critical.
- User - username that logged onto the host. 
- Computer - name of the host device.

### Event Log Details

Windows Event Logs are stored in the C:\\Windows\\System32\\winevt\\logs directory with the file extension .evtx. It runs under the service host executable svchost.exe which is set to run on startup by default. 

Run the following command to view the contents of the logs file:

>ls C:\\Windows\\System32\\winevt\\logs

### Windows Event Viewer

Windows Event Viewer is the #GUI application for Windows Event Log. It can be accessed via Command Prompt ( #CMD) using the #wevtutil utility or via #PowerShell using the Get-WinEvent cmdlet. These utilities can both be used locally and remotely.

#### wevtutil

The wevtutil utility is one method of exporting, archiving, and clearing our Windows Event Log. 

##### Enumerating Logs

We can enumerate the names of all logs present on our system with the el parameter, as seen in the following command:

>wevtutil el

##### Gathering Logs

We can use the following command with the gl parameter to display configuration information about our logs such as size, permissions, location, and whether the log is enabled:

>wevtutil gl "Windows PowerShell"

We can use the gli parameter in the following command to retrieve even more information related to the lofs creation time, last access, last write time, file size, and number of logs:

>wevtutil gli "Windows PowerShell"

##### Query Events

We can use the query parameter, qe to seek more specific information about our logs.

Use the following command to find the last 5 events in text format:

>wevtutil qe Security /c:5 /rd:true /f:text

##### Exporting Events

If we have local administrator privileges, we can use the following code to export events for offline access:

>wevtutil epl System C:\\system_export.evtx

### Windows Event Log - PowerShell

PowerShell handles Windows Event Log using the Get-WinEvent cmdlet, which works quite similarly to wevtutil. 

#### Viewing Logs

We can begin with the following command to list all logs:

>Get-WinEvent -ListLog \*

#### Security Log

We can specify results from only the security log using the following command:

>Get-WinEvent -ListLog Security

#### Query Defined Amount of Logs

We can gain more granular control over our PowerShell output with the -MaxEvents and -Oldest modifiers. 

Using the following command, retrieve the oldest 5 events from the security log:

>Get-WinEvent -LogName 'Security' -MaxEvents 5 | Select-Object -ExpandProperty Message

#### Filtering

We can use various attributes to search through our logs and filter output that is excessive. If we know the Event ID of a specific event, we can filter for that and have only that event returned in our output. 

The following command will allow us to filter out all log output except for the Event ID 4625: Account failed to log on:

>Get-WinEvent -FilterHashTable @{LogName='Security';ID='4625 '}

Use the next command to filter for all logs that return a critical information level of 1:

>Get-WinEvent -FilterHashTable @{LogName='System';Level='1'} | select-object -ExpandProperty Message

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Windows Event Log](https://academy.hackthebox.com/module/167/section/1615 'HTB academy PowerShell Windows Event log guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)