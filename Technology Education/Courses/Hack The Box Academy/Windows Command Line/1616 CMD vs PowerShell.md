# CMD vs PowerShell

#PowerShell is the successor to Command Prompt ( #CMD) and both are still native to modern #Windows Operating Systems ( #OS).  These applications are both command line interfaces ( #CLI) for Windows, with #PS being the newer application. 

### Comparison

| Feature            | Command Prompt                        | PowerShell                      |
| ------------------ | ------------------------------------- | ------------------------------- |
| Language           | Batch and CMD commands                | Batch, CMD, PS cmdlets, aliases |
| Commands           | Command output cannot be passed       | Command output can pass         |
| Output             | Text-based                            | Object-based formatting         |
| Parallel Execution | One line must execute before the next | Multi-threaded commands in parallel                                |
Beyond this basic chart PowerShell was designed as an extensible open-source application with integration for other applications and tools. PowerShell is also a scripting language and this further enables automation of tasks and macros. The .NET framework enabled PS to use object based output. PowerShell can also be compatible with #Linux systems. All around it is a more adaptable and robust option than the more skeletal offerings of command prompt.

Additionally, PowerShell is used by IT professionals to perform tasks CMD is incapable of:

- Installing and managing servers and server roles.
- Managing Active Directory ( #AD).
- Managing File Shares.
- Integrating with #Azure and Virtual Machines ( #VM).
- Managing directories and files.
- Gathering information about workstations and servers.
- Managing #Microsoft #Exchange email.
- Logging and Monitoring system activity.

A case for the use of Command Prompt would be a situation where we want to avoid the the thorough logging and monitoring that PowerShell provides. From the perspective of an attacker, sometimes leaving no trace of our presence in the target host is more desirable than the functionality that PowerShell offers us.

### Opening PowerShell

There are a variety of methods for opening the PowerShell application or terminal window.

##### Windows Search

Type 'PowerShell' into the windows search bar and the application will be presented for you to click.

##### Windows Terminal

#Windows #Terminal is a #CLI emulator that allows for the use of multiple command line interfaces and sub-systems and is becoming the standard terminal for Windows machines.

##### PowerShell ISE

The PowerShell Integrated Scripting Environment ( #ISE) is a great platform for development and has methods for debugging and testing scripts before they are implemented.

##### CMD

We can also open PowerShell from within command prompt. This is useful when you want to use PowerShell without opening other applications. If you have access to the command prompt on a target host, you likely have access to PowerShell as well.

#### Get-Help

The Get-Help #cmdlet is like /? or the help command in command prompt. It shows us syntax rules, the name of commands, information about aliases, and a remarks section that yields more information about a given cmdlet. There is also the option '-online' which will open the Microsoft Docs website with much more information about anything related to PowerShell.

##### Update-Help

The Update-Help cmdlet will retrieve all current content for cmdlets when there is an active internet connection. Observe how much of this download information is related to 'Test-Wsman'.

###### Test-Wsman

Use the Get-Help cmdlet to learn more about Test-Wsman:

>Get-Help Test-Wsman

##### Get-Location

The Get-Location cmdlet returns your working directory.

##### Get-ChildItem

The Get-ChildItem cmdlet will output the contents of the working directory.


##### Set-Location

The Set-Location cmdlet accepts a file path and then moves to the path described. This is our means of navigating the file system in PowerShell. Aliases for this command are the common 'cd' and 'chdir'.

##### Get-Content

The Get-Content cmdlet will output the contents of a file into the CLI window. 

##### Get-Command

The Get-Command cmdlet will output a very long list of the cmdlets and the 'verb-noun' presentation for these command. We can use cmdlet modifiers and filter for specific verbs or nouns to narrow down our search as well. 

The format for cmdlets is 'verb-noun' by default so a user can search for a verb like 'set', 'get', 'enable', 'apply' to see a full list of cmdlets that are capable of these functions. Alternatively you can search for the noun you are interacting with, like 'server', 'file', 'application', 'volume', etc. to output the full list of verb functions that could apply in the case of a 'server'.

##### Get-Command Verb

We could use the following command to reveal every cmdlet that uses the verb 'get':

>Get-Command -verb get

Alternatively you could use get* in place of -verb get. 

##### Get-Command Noun

We could use the following command to reveal every cmdlet that uses the noun 'Windows':

>Get-Command -noun windows*

##### Get-History

The Get-History cmdlet lets you access a history of commands that have been issued through PowerShell during the current session. Alternatively you can use the #PSReadLine module to see a persisting command history. PowerShell maintains a history of the last 4096 commands that have been issued, but this can be increased or decreased by modifying the \$MaximumHistoryCount variable. PSReadLine maintains its persistent history in the file \$($host.Name)\_history.txt within the \$env:APPDATA\\Microsoft\\Windows\\PowerShell\\PSReadLine directory.

When using Get-History to view our command history, these previous commands are assigned an order number. This number can be used with the 'r' alias to recall the command and use it again.

We can see an example of this recall method with the following command:

>Get-History r 14

This would recall the 14th entry in the command history.

##### Clear-Host

The Clear-Host cmdlet will clear the CLI window of all output. Alternatively you can use the aliases clear or cls.

### Hotkeys

Hotkeys are of crucial importance when we are interacting with a shell. This is especially true in the case where we do not have access to a Graphical User Interface ( #GUI) or there is no way to use a mouse. 

Here is a brief list of the most important hotkeys:

| HotKey                 | Description                                                                       |
| ---------------------- | --------------------------------------------------------------------------------- |
| CTRL + R               | Presents a searchable history. Begin typing to see entries related to this input. |
| CTRL + L               | Clears the screen.                                                                |
| CTRL + ALT + Shift + ? | Prints the list of shortcuts PowerShell recognizes.                               |
| Escape                 | Erases the current line.                                                          |
| Up                     | Scrolls upward.                                                                   |
| Down                   | Scrolls downward.                                                                 |
| F7                     | Generates a Text-based User Interface ( #TUI).                                    |
| Tab                    | Generates terms for tab completion.                                               |
| Shift + Tab                       | Cycles backward when using tab completion.                                                                                  |
### Aliases
#### Get-Alias

An Alias in PowerShell is an alternative name for a command that our CLI will accept in place of the standard 'verb-noun' pair. These are often shorter for fast and efficient use of our cmdlets. 

The Get-Alias cmdlet is a way that we can see all the associated aliases for a given cmdlet. 

#### Set-Alias 

The Set-Alias cmdlet allows us to assign a custom alias for a given cmdlet. This is very useful for improving our workflow and modifying PS to work better for our personal patterns and preferences.

The Set-Alias cmdlet follows a specific syntax to define the new name of an existing cmdlet. It is as follows:

>Set-Alias -Name \<alias-name> -Value \<name-of-cmdlet>
>Set-Alias -Name gh -Value Get-Help

#### Common Aliases

There are many shared aliases between PowerShell and Linux CLIs. If you are familiar with #Linux commands, much of this knowledge will directly translate into PowerShell.

| Alias     | Description                                                                     |
| --------- | ------------------------------------------------------------------------------- |
| pwd       | Get-Location. This prints the working directory. You can also use gl.           |
| ls        | Get-ChildItem. This lists the directory contents. dir and gci can also be used. |
| cd        | Set-Location. This changes the directory. chdir and sl can also be used.        |
| cat       | Get-Content. This prints the contents of a file. type and gc can also be used.  |
| clear     | Clear-Host. This clears the CLI window. cls can also be used.                   |
| curl      | Invoke-WebRequest. This downloads specified files. wget can also be used.       |
| fl and ft | Formats output into list and table formats.                                     |
| man       | Get-Help. This can be used in place of help.                                                                                |
### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy CMD vs PowerShell](https://academy.hackthebox.com/module/167/section/1616 'HTB academy CMD vs PowerShell module')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)