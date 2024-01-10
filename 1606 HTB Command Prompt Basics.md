# Command Prompt Basics

Command Prompt is a #Windows application that is also known as #CMD or by it's executable filename cmd.exe. CMD is the Command Line Interface ( #CLI) for the Windows Operating System ( #OS). Command Prompt is based off of the older COMMAND.COM #DOS interpreter from legacy systems. 

Command Prompt allows us to input commands that are directly received by the operating system and executed accordingly. Most of the OS functions can be executed through this interface. CMD offers us a lightweight method for interacting with the operating system without using a Graphical User Interface ( #GUI) which consumes more resources. There are also instances where the newer #PowerShell is locked and the only means of interaction is CMD.

### Local Access

Local access can otherwise be thought of as having a physical connection to the host you will be executing cmd.exe from. Executing cmd.exe from a Virtual Machine ( #VM) on your computer would fall under the umbrella of local access.

You can press Windows Key + R to open the run prompt. Within run prompt, you can enter 'cmd' and press enter to execute cmd.exe and open command prompt. 

Alternatively you could execute from the drive path C:\\Windows\\System32\\cmd.exe.


### Remote Access

Remote access does not require physical access to the host but instead uses virtual peripherals to access a host across the #network. There are many protocols we can use to gain remote access such as Secure Shell ( #SSH), #PSExec, #WinRM, Remote Desktop Protocol ( #RDP), or the insecure and outdated #telnet. 

Most or all system administrators will use remote access protocols for the majority of their work. This allows them to access most hosts on their network without leaving their desk. While this is highly convenient, it also poses security threats and means for attackers to gain unauthorized access. These protocols must be configured properly to prevent this.

### Directories and dir

The file structure for command prompt is hierarchical and text-based, similar to Linux command line features. The #dir command reveals the contents of a directory. Issuing commands will create a basic response and request correspondence between you and the command prompt interface. 

### Exploiting Repair Mode and Sticky Keys

Repair mode is useful when troubleshooting problems with our machines but it can lead to vulnerabilities as well. There is a common exploit of the #Windows feature 'Sticky Keys', where an attacker changes the executable binary sethc.exe for Sticky Keys with the cmd.exe binary. This means that if the machine is put into recovery mode after reboot, an attacker can press Shift  five times to open the command prompt with NT AUTHORITY \\SYSTEM permissions. 

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Command Prompt and PowerShell](https://academy.hackthebox.com/module/167/section/1604 'HTB academy PowerShell and Command Prompt')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)