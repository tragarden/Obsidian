# Windows Command Line Tools 1.2

### Administrator Privileges

Many utilities and applications will require you to **‘Run as Administrator’ as well as be a part of the Administrator’s Group.**  ***Right-click command prompt and select ‘Run as Administrator’ to elevate your privileges*** and access *Command Prompt* by typing #cmd in run or pressing Ctrl-Shift-Enter at the desktop. 

#### Basic Commands

Typing ‘help’ + **command** or **command** /? will give you very detailed info on how to use commands.

‘ #cls’ **clears the terminal** of all command prompt data. 

‘ #dir’ will **list all system files and directories**.

‘ #cd’ or ‘ #chdir’ is used to **change the working directory** via text input.  ***‘/’ is used to delineate between files*** and denote which file name or volume to inspect. 

‘..’ indicates a **return to the containing folder** for the object we are currently interacting with.

‘ #mkdir’ and ‘ #rmdir’ commands are used to **make and remove directories**, respectively.

### Names and Identifiers

*Drive Letters* **indicate which #partition of the system drives we are actively using.**  C: is used as the reference letter for your primary storage device.

‘ #hostname’ command is useful when we have multiple terminal windows open that are interacting with different devices.  Using the ‘hostname’ command, **we can know what the Windows Device name is.**

‘ #winver’ will **tell you the current version** of #Windows that is being used by the system.

#### Managing the OS Version

‘ #format’ is used to **format a disk to be used with Windows.** ***BE VERY CAREFUL WHEN USING THIS COMMAND TO AVOID DATA LOSS.  IT IS GOOD PRACTICE TO BACK UP YOUR SYSTEM AND FILES BEFORE ATTEMPTING TO USE THE FORMAT COMMAND.*** The format command is **used to designate a drive to use and then create a partition on that drive for the new file system.**  By default, *File Allocation Table* ( #FAT) 32 will be used as the default file system.  A *Volume Label* will be created to name the system, and a message indicating total disk space will be included.

The ’ #copy’ command acts in a way we are familiar with **while adding the ‘/v’ flag to verify the file copy matches the original, and ‘/y’ used to skip prompts** asking if you want to overwrite data.

> The format for the copy command is ‘copy **sourceFile**'

‘ #xcopy’ command is used to **copy multiple files and even directory trees.**  The **flag ‘/s’ will include subdirectories,** meaning that the copy will be applied to our current folder, as well as every folder contained within it. When designating a destination, for example the folder ‘backups’ on drive M:

> C:\Users\administrator>xcopy /s Documents m:\backups

‘ #robocopy’ represents **‘robust copy’** and is seen as a **better version of xcopy.**  This command is included with Windows 10 and 11.  Robocopy **allows for very granular management of #automation** of the copy command.  You can designate certain hours when this action will be performed, and #blacklist other times when you do not want it to be operational.

‘ #shutdown’ command is used to **power off the device** and can also be used to restart. The **‘/s’ flag indicates that you want the system to shut down while the ‘/r’ flag indicates a restart.**  The **‘/t’ flag indicates the amount of time you want the system to wait** before shutting down, **indicated by seconds via the ‘nn’ flag.**  If you need to abort this timed shutdown for any reason, use the command with the **flag ‘/a’ to abort the shutdown.**

#### Partitioning

‘ #diskpart’ command allows you to **manage the partitions and configurations of your disks.** ***DO THIS CAREFULLY AND BACKUP DATA AS YOU CAN LOSE DATA WITH THIS COMMAND.*** You will need to **run as administrator** to access the diskpart command. 

While in the #DiskPart interface, you will have **additional commands like ‘list’** that yields a few suggestions for appropriate source names.  **‘list disk’** command will list all the disks within the system. **‘list volume’** will generate a list of all volumes contained on the designated disk.

#### Group Policy

*Group Policy* allows us to **manage multiple devices at once via** the *Active Directory Domain.*  Group Policy gets updated during login.

‘ #gpupdate’ **forces a Group Policy update upon all target devices** on the local network.  This allows users to **update without being forced to go through the login process** and additional time.  An example of this command is using it to apply a new Shortcut to every designated computer.

‘ #gpresult’ will verify the policy settings for a certain computer or user.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/windows-command-line-tools-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [011 An Overview of Windows](011%20An%20Overview%20of%20Windows.md)
- [011 Windows Features](011%20Windows%20Features.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [018 Operating Systems Overview](018%20Operating%20Systems%20Overview.md)
- [019 Installing Operating Systems](019%20Installing%20Operating%20Systems.md)
- [021 Active Directory](021%20Active%20Directory.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)

#study #professormesser #comptia #Aplus #software #OS #commandprompt #CLI #commandline #grouppolicy #directory #activedirectory 