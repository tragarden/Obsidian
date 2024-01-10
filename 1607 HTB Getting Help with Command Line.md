# Getting Help with Command Line

Getting detailed information about how to used the Command Prompt ( #CMD) is as easy as typing the word 'help'. This word is a function and if we issue this command we get a detailed list of the commands that are available to us. These functions or commands are known as #built-in commands.

We can request further information about any built-in command within the help list with the following syntax:

> help \<command name>

There are instances of commands that are not within the scope of the help command. An example of this would be the ipconfig command. If we were to type 'help ipconfig' into our command line, we would be directed to use the /? command instead. 

To get more detailed information about the ipconfig command, use the following command:

>ipconfig /?

Sometimes a command will accept both the help option and the /? option.

### Offline

The help utility exists to serve as a manual or guide for the command prompt when we do not have access to the internet. This ensures that even if you are interacting with a machine that has no internet connection, we can still get help understanding commands and their correct syntax.

### Online

While the help utility can explain a lot about the commands available to us, the internet undoubtedly has more thorough explanations, examples, and information regarding the commands we can use. [Microsoft Documentation](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands 'Microsoft's full list of commands, descriptions, and syntax')and [ss64](https://ss64.com/nt/ 'ss64 database for cmd, ps, bash')are great online resources for understanding commands.

### History and Clear

When we are working within Command Prompt it often occurs that the commands and output will crowd the window. We can clear all of this from our window with the #cls command. 

Command Prompt will store all issued commands and output from our current session, and this can be retrieved from the Command History. When we are viewing the Command History, we can navigate this window with the arrow keys, page up and down, and the function keys if using a #Windows host. It should be noted that these command are only for the current session as CMD does not provide persistent command history from other sessions.

#### doskey /history

#Doskey is a #MS-DOS utility that records your command history for later reference. We can access Doskey with the following command:

>doskey /history

#### Function Keys

The Function keys ( #F-key) add some features to the doskey /history command. 

- F3 will recall the last command you issued.
- Pressing F5 key repeatedly will cycle through your recently used commands.
- F7 Opens an interactive list of previous commands.
- F9 assigns a number to previous commands so that you can recall them.

### Ending a Process

When a process is stuck or we don't want it to keep running, press Ctrl + C to end the process.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Command Prompt Help](https://academy.hackthebox.com/module/167/section/1607 'HTB academy Command Prompt Help')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)