# CMD Directories and Files

### Directories

#### Viewing and Listing

- dir - lists the files within the current working directory
- tree - list all directories in a particular path
- tree /F - list all files and directories in a given path
- cd - prints the working directory or changes directory when a path is given

#### Creating Directories

- md \<directoryName> - creates a new directory
- mkdir \<directoryName> - creates a new directory

#### Deleting Directories

- rd \<directoryName> - removes a directory tree
- rmdir - removes a directory tree
- rd /s - removes a directory tree and the containing directory

#### Directory Modifications

- move \<directoryName> \<filePath>
	- move directory1 C:\\Users\\htb\\Documents\\directory1

- xcopy - a more featured method for moving directories. This method removes the read-only bit from files when they are moved. Xcopy uses the following format:
- xcopy \<sourcePath> \<destinationPath> \options
	- xcopy C:\\Users\\htb\\Documents\\Directory1 C:\\Users\\htb\\Desktop\\ /E
- /E - includes empty directories in the move
- /K - retains the attributes of the moved directories

- robocopy - a more capable moving tool that succeeded xcopy. This tool is made to move large directories to different drives and across networks. It generates timestamps, ownership information, and set flags. This is not the best option for moving individual files, although it is capable of doing that. Robocopy can also be used to move system, read-only, and hidden files - although you will need to have auditing privileges and SeBackupPrivilege to do so.
- robocopy \<sourcePath> \<destinationPath>
- /MIR - permits the user to temporarily copy files. Mirrors the destination directory back to the source.
- /A-:SH - clears the attributes from the directory.
- /L - shows the results of the command issued without executing it

### Files

- more - provides information about file contents without filling up the terminal screen. You must press Enter or Space Bar to view more of the file information.
- /S - limits the amount of information output to a single line.
You can also pipe the output of a command to the more command so that it doesn't overwhelm you when you want to read output. 

- openfiles - reveals the open files for a given user on local network or a remote host. This command must be enabled on #Windows. Once enabled you can see open files, disconnect them, and block the user from seeing them.

- type - displays the contents of text files and can be used for file redirection.
	- type myFile.txt >> secretFile.txt

Tools like more and type may seem underwhelming but as an attacker, these are low-impact tools that are useful for discovery and information gathering.

#### Creation and Modification

- echo - we can use echo to redirect and create files with the following commands:
	- echo LOOK AT MY TEXT > demo.txt
	- echo MORE TEXT APPENDED TO OUR DEMO FILE >> demo.txt
	- type demo.txt

- fsutil - used for many purposes but can create files
	- fsutil file createNew newFile.txt 222

- ren(ame) - is used to rename a file

#### Input / Output

- > - sends command output to a specified or new file
- >> - appends command output to the end of a specified or new file
- < - sends input from a file to a command
	- find /i "secret" < secretFile.txt
- The above command would search for the word 'secret' within the contents of secretFile.txt
- | (pipe) - pipe allows us to submit the output of a command to another command
- & - this option will execute the command A before the &, then run command B that lies beyond the &
- && - this is the conditional version of &. it will only run part B if the part A successfully executes.
- | | (pipe pipe) - this will run part B ONLY if part A does not successfully execute

#### Deleting

- del - deletes a specified object
- erase - deletes a specified object

The del and erase commands are interoperable and both can delete a directory, file, file list, or attributes.

- /A: deletes files based on a given attribute.

To view the list of attributes, you can look at the help tool for the del command. When you know attributes, you can assign an option to the /A: command to denote that you want those attributes deleted.

- dir /A:R - would display any read-only files in the working directory.

- dir /A:H - would display any hidden files in the working directory.

##### Validation

We can validate if a moved or copied file has been modified successfully by using the -V flag.

- /V - validates that a file has been successfully copied.
	- move C:\\Users\\student\\Desktop\\bio.txt C:\\Users\\student\\Downloads


### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Windows Command Line](https://academy.hackthebox.com/module/167/section/1610 'HTB academy Windows command line guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [018 File Systems](018%20File%20Systems.md)