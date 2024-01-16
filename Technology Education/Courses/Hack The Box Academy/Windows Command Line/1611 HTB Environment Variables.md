# Environment Variables

Environment Variables are globally applied settings that are used to run scripts and increase the performance of applications. These variables are found on all operating systems, but each #OS implements them differently. 

For the case of #Windows machines the names of these variables are not case-sensitive and can use unique characters with the exception of equal signs and names that begin with a number. It is common for variables on the Windows system to be represented in all caps with underscores for spacing, as seen in the example below:

>%ENVIRONMENT_VARIABLES_EXAMPLE%

### Scope

The scope that variables fall within can be categorized as Global or Local. 

Global variables are accessible from anywhere in a given program.

Local variables are only available within a specific function where it was declared.

A user could create a local variable that only they have permissions to access. This means that the user has defined the variable locally and other users are unable to access it as it is not within the scope of their current environment. 

When we examine scope further, there are three types: System variables, User variables, and the unstable Process variables.

- System - this scope contains only global variables that are used to make the system operational. They begin running upon system boot and the only users with permissions to access these variables include the Local or Domain Administrators.
	- HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Environment

- User - this scope pertains only to local variables defined by the user. These variables are only accessible to the user that created them, as well as the Local and Domain Administrators. 
	- HKEY_CURRENT_USER\\Environment

- Process - these are only accessible locally and are created and maintained for the duration of a running process and then terminated. They inherit variables from the global scope, user scope, and the variables associated with the process that spawns them. The only user that can access them is the Current Active User, but the related Parent and Child processes can access it as well. 

#### Set and Echo

The set command will print all available environment variables. If you supply a given variable name after the set command, it will print the value of this variable. 

The echo command can be used to output the values contained within the named variable.

### Managing Variables

The set and setx commands can be used to display and remove environment variables. 

The set command acts within the current command prompt window and these changes will revert to their previous state when the #CMD window is closed or otherwise terminated.

The #setx command can be used to permanently create, remove, or otherwise edit the environment variables. 

In the example given, a variable is created to store the #IP address of the Domain Controller  ( #DC). If we named the variable DCIP, the command to create it would look like the following:

>set DCIP=10.10.10.10

To validate this change and make sure it's working, echo the variable name:

>echo %DCIP%

Here we can see that our variable worked! Since we used the 'set' command, these changes will only exist in the process scope and will be erased when our command prompt is terminated. If we used the setx command - these changes would persist after we exit CMD.

##### setx

If we want to implement changes to environment variables that persist beyond the lifetime of a command prompt window, we must use the setx command. The syntax for setx varies slightly from the set command, and these changes must be observed if we want the command to work properly.

The syntax for setx command execution is as follows:

>setx \<variable name> \<value> \<parameters>
>setx DCIP 10.10.10.10

Note that setx does not use the equals sign like the set command syntax requires. If syntax is correct with the setx command, we will see "SUCCESS: Specified value was saved." in our output feed. The changed variables will only be available to us in a new CMD session, and they will only be available to our system in the next logon session. 

##### Edits

To edit a setx variable value, simply re-submit the original variable name with the desired new values and parameters.

##### Removal

While we cannot delete a variable created with setx, we can set them to a null value which essentially negates their use. Simply edit the variable to have no content and it will be effectively removed from use.

### Noteworthy Environment Variables

- %PATH% - lists directories containing executables.
- %OS% - current operating system ( #OS).
- %SYSTEMROOT% - A global read-only variable containing the #Windows system folder. Core system functions stem from this variable. 
- %LOGONSERVER% - reveals the logon server for the current session and the associated hostname. From here we can see the domain or workgroup of our machine.
- %USERPROFILE% - yields the location of the current user's home directory.
- %ProgramFiles% - contains all x64 base programs.
- %ProgramFiles(x86)% - contains all x32 base programs.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Windows Environment Variables](https://academy.hackthebox.com/module/167/section/1611 'HTB academy Windows Environment variables guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [018 File Systems](018%20File%20Systems.md)