# Linux Commands 1.11

### Command Line

The *Command Line Interface* ( #CLI) is the main way we interact with #Linux operating systems, and typically you will use #Terminal or #XTerm.  You will notice similar commands to macOS – largely because they are both based on #Unix.  You can **create bootable media** with Linux #OS on it or **install a virtual machine** on your current OS.  This demonstration was performed via #Ubuntu on a Virtual Machine.

#### Common Commands

The ‘ #man’ command is **short for manual** and is used to get more information about other commands.

The ‘ #ls’ command is similar to ‘ #dir’ in #Windows and is used to **list files and directories,** which may be color coded depending on the version of Linux you are using.  The **-l flag** indicates **long output** and will give you a more detailed readout.  This readout can be broken down into smaller segments by #piping the ‘ #more’ command, which will reduce input to individual ‘pages’ that are easier to read through.  **Ctrl-C or Q will exit** these commands.

The ‘ #pwd’ command will **print the current (working) #directory and pathing.**  This is useful when you are changing directories and unsure of where you are when lacking a #GUI.

The ‘ #mv’ command **renames a file or directory** using the format ‘ mv SOURCE DESTINATION ‘ or ‘mv firstFile.txt second.txt’.

The ‘ #cp’ command works similarly to the move command but **duplicates or copies the file** instead.

The ‘ #rm’ command **removes files** from the file system.  This **will not work with directories unless you use the -r flag** to recursively apply the remove command to the entire directory.

#### Managing Permissions

The ‘ #chmod’ command changes the mode of an object in the file system.  The **permissions associated with this are indicated by an r (readable), w (writable), or x (executable).**  You can set these permissions for the file **owner (u), a group (g), other users (o), or everyone/all (a).**  #Octal notation is acceptable for interacting with these permissions.

The #permissions above are **expressed as a 10-character code within the file information.**  The first character indicates the type of data you are interacting with. Basic **files are indicated by a hyphen (-), directories are indicated by a (d), and symbolic links use (s).**  The **next 9 characters represent 3 groups of 3 to express the read/write/execute permissions of the user, group, and other users.**

##### Binary and Octal

#Octal methods are applied for these permissions with a number that indicates the level of permissions for each group.  The **code ‘744’ would indicate r/w/x permissions for the user (their binary representations add up to 7)** and read only rights for the group and other users (their #binary representations add up to 4, each).  *** (9-minute mark on this vid will explain this better) ***

>chmod 744 first.txt would yield full rights to user, and read-only rights to all others.

>chmod a-w first.txt would ban writing to first.txt for all users.

>chmod u+x would make it so only the file owner can execute it.

The ‘ #chown’ command is used to **change the file owner, group, and to modify file settings.**

sudo chown OWNER:GROUP file

sudo chown tragis myfile.sh

#### Superuser

The ‘ #sudo’ or ‘ #su’ command allows us to **execute commands as the #superuser** or a different user, quite similar to running as #administrator on windows. You can also run the terminal as a superuser to have superuser rights applied to all executions within that session.

#### Packaging Tools

‘ #apt-get’ is the *Advanced Packaging Tool* for Linux and allows us to **install and remove #applications** and utilities from our operating system.

sudo apt-get install wireshark

*Yellowdog Updater Modified* ( #YUM) is used on #RedHat versions of Linux to **install, delete, and update apps.**  It manages #RPM packages via *Red Hat Package Manager* or *RPM Package Manager.*

#### Network Management

The ‘ #ip’ command is used along with several options to manage your network interface.  You can **configure #IP addresses, their routing, the #ARP #cache, and enable/disable devices.**

‘ip address’ will allow you to see the addresses of your local devices.

‘ip route’ will display the IP routing table.

‘sudo ip address add 192.168.121.241/24 dev eth0           will configure an IP address.

#### Disk Management

The ‘ #df’ or *Disk Free* command will **show the available free space on our system drives.**  The **flag ‘-h’** is important when using this command, as it will **present the data in a human readable way.**

#### Grep

The ‘ #grep’ command **searches for text** within many files at a time. 

grep failed auth.log         would display all of the failed login attempts.

#### Processes

‘ #ps’ is the #processes command and will **show you all active processes and their associated process ID** ( #PID). The **‘-e’ flag will show more processes** – it is useful to use this in conjunction with #piping and the ‘ #more’ command to break the large amounts of data into pages.

The ‘ #top’ command **provides an overview of active processes** and is similar to Windows Task Manager. You can view all active resources like #CPU usage, #RAM usage, and other metrics.  In addition to active metrics, you can observe load over time in one, five, and fifteen minute observation periods.

#### Locating Files

The ‘ #find’ command **locates a file by either its name or extension type.** An asterisk preceding the file extension type is a form of #RegEx that searches for any file with that extension type.

#### Dig and DNS

The ‘dig’ command uses the *Domain Information Groper* ( #DIG) to obtain detailed information from your #DNS server such as **canonical names, IP addresses, cache timers,** and more.  This can also be added to Windows.

#### Concatenation

The ‘ #cat’ command **concatenates things together** into one item. 

cat file1.txt file2.txt         would print both of these files to the display.

cat file1.txt file2.txt > both.txt     would copy both file contents within both.txt.

#### Nano

‘ #nano’ opens a text editor that is often included with Linux distributions that is similar in function to graphically based text editors.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/linux-commands-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [018 File Systems](018%20File%20Systems.md)
- [111 Linux Features](111%20Linux%20Features.md)
- [133 Storage Devices](133%20Storage%20Devices.md)

#study #professormesser #comptia #Aplus #software #kernel