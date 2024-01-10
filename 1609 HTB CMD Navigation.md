# Command Prompt Navigation

C:\\ is the root drive label designation because when these systems were invented, A:\\ and B:\\ were used to designate floppy drives.

It is called the root directory because it contains every directory tree.

An absolute path is the full directory path from the system root to the specific directory we are seeking.

Below is an example of the absolute path to the Pictures folder in the example:

>C:\\Users\\htb\\Pictures

Relative paths use the period character " . " to indicate that we are using the current working directory to reference our position in relation to the directory we are seeking. 

We can use the double dot character " .. " to move up the directory hierarchy towards the root directory. We can also use slashes and multiple instances of double dot to indicate we want to go back to the root directory.

We can use the following command to return to the root directory:

>cd ..\\\..\\..\\..\\

The tree command can be used to print out an entire pathing structure for all the directories within our working directory.

We can use the command below to list out the directory tree, and then list all files or folders with the -F flag:

>tree /F

This is especially useful when hacking because we can get an overview of the whole system and seek our sensitive information. After we have viewed the information we need, we can end the tree process by pressing Ctrl + C.

### Noteworthy Directories 

- %SYSTEMROOT%\\Temp - this directory contains temporary system files that grants all users read, write, and execute permissions.
- %TEMP% - contains all user specific temporary files and is vulnerable if an attacker gains privileges over a local user account.
- %PUBLIC% - allows any account that logs in full read, write, and execute permissions over all files and folders within. Less likely to be monitored than the Windows Temp Directory.
- %ProgramFiles% - contains all the 64-bit applications on the system. A good source for enumerating application data.
- %ProgramFiles(x86)% - contains all the 32-bit applications on the system. A good source for enumerating application data.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Command Prompt Navigation](https://academy.hackthebox.com/module/167/section/1609 'HTB academy Command Prompt Navigation guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)