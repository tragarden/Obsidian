---
aliases:
---
# Scripting and Automation with PowerShell

#PowerShell was designed to facilitate automation through the use of scripting and control through it's modular design. It is powerful due to its ability to process multiple coding languages, cmdlets with various functions, backwards compatibility with command prompt ( #CMD), and cross platform compatibility. Automation can be done via single scripts in the .\\script syntax and modules can be imported using the Import-Module cmdlet.

### File Extensions

| Extension | Description                              |
| --------- | ---------------------------------------- |
| ps1       | \*.ps1 for executable PowerShell scripts |
| psm1      | \*.psm1 for PowerShell modules           |
| psd1      | \*.psd1 for PowerShell data files in key/value pair format                                         |
### Module Creation

We often end up repeating a similar process over and over again to a point of monotony. When we have to do this hundreds or thousands of times - automation saves a lot of time and effort while lowering the chance for human error. 

In the situation presented in the coursework, we want to create a PowerShell module that outputs the host computer name, #IP address, domain information, and output the content of the C:\\Users\\ directory so we can see who has recently logged in. 

#### Module Components

There are four key components to every module:

1. A containing directory that contains all files and content relevant to the module. This is located within the $env:PSModulePath.
2. A manifest file that lists the location of all files, scripts, authors, dependencies, usage examples, and information related to the module. 
3. Either a PowerShell script or module file (.ps1 or .psm1) that contains script functions.
4. Help files and other support documents.

#### Containing Directory

The first step to creating a module is to create a directory to contain it. This must be located within the $env:PSModulePath variable. In the case of this module we will create it within the file path C:\\Users\\MTanaka\\Documents\\WindowsPowerShell\\Modules.

Navigate to the directory C:\\Users\\MTanaka\\Documents\\WindowsPowerShell\\Modules and create a new directory named quick-recon with the following command:

>mkdir quick-recon

#### Module Manifest

A module manifest is a .psd1 file containing a hash table. The manifest describes the content and attributes of the module and defines prerequisites that the module depends on to function properly. This manifest will determine how the components of the module are processed. If the manifest is within the PowerShell module file - the module can reference multiple files singularly. 

The manifest contains a few key items:

- #Metadata like version number, author, and description.
- Prerequisite dependencies required to import the module successfully. This would include PowerShell version number, common language runtime ( #CLR) version, and other modules it is dependent on.
- Processing directives - scripts, formats, and types that will be processed.
- Export restrictions such as aliases, functions, variables, and cmdlets.

##### New-ModuleManifest

We will use the following command to create the manifest with the New-ModuleManifest cmdlet.

>NewModuleManifest -Path C:\\Users\\MTanaka\\Documents\\WindowsPowerShell\\Modules\\quick-recon\\quick-recon.psd1 -PassThru

The -PassThru modifier prints the contents of the manifest file to the console so we can see what we need to modify to configure it properly. Every line in the manifest is optional with the exception of the ModuleVersion line. Modifying the manifest is easiest when using a #GUI, but #VSCode or text editors work in cases where GUI is unavailable. We will return to the manifest file we just created later to add functions, cmdlets, and variables before exporting it.

#### Creating Script Files

Creating the file for our script is done with the New-Item cmdlet in the following command:

>New-Item quick-recon.psm1 -ItemType File

#### Importing Modules

We need to add a string to the beginning of our script file that will call the Import-Module cmdlet and retrieve the ActiveDirectory module. This will function as if we executed it within PowerShell - the quick-recon module we created will call and load the ActiveDirectory module before the script is executed.

Add the following line utilizing the Import-Module cmdlet to the beginning of the quick-recon.psm1 file:

>Import-Module ActiveDirectory

#### Functions

The module we are creating has four goals:

- Retrieve the host ComputerName.
- Retrieve the host IP configuration.
- Retrieve domain information.
- Retrieve the output of the C:\\Users\\ directory.

##### Retrieving ComputerName

We will use the environment variable $env:ComputerName to retrieve the hostname and return it in our output, which will be stored within the $hostname variable. 

##### Retrieving IP Address

We will use the IPConfig cmdlet to retrieve the #IP address and the output will be stored within the $IP variable. 

##### Retrieving Domain Information

We will use the Get-ADDomain cmdlet to output the domain name and store it with the $Domain variable.

##### Retrieving Usernames

We will use the Get-ChildItem cmdlet to list the user folders within C:\\Users\\ directory in our output and store it in the $Users variable. 

#### Variable Creation

We will now assign the indicated variable names to the related commands, cmdlets, and environment variables by using the equals sign to set the variables. Each variable will run a singular command or function and return the output to be stored within the variable name.

Place the following code into the quick-recon.psm1 script file to assign the variables to their associated values:

>Import-Module ActiveDirectory
>\ 
>$Hostname = $env:ComputerName
>$IP = ipconfig
>$Domain = Get-ADDomain
>$Users = Get-ChildItem C:\\Users\\

#### Formatting Output

The variables now store the functions we implemented and the next step is to utilize the New-Item and Add-Content cmdlets to format the output. 

We will create a function we can easily call by the name Get-Recon:

>Import-Module ActiveDirectory
>\ 
>function Get-Recon {
>	
>	$Hostname = $env:ComputerName
>	
>	$IP = ipconfig
>	
>	$Domain = Get-ADDomain
>	
>	$Users = Get-ChildItem C:\\Users\\
>	
>	New-Item \~\\Desktop\\recon.txt -ItemType File
>	
>	$Vars = "\*\*\*---Hostname Info---\*\*\*", $Hostname, "\*\*\*---Domain Info---\*\*\*", $Domain, "\*\*\*---IP Info---\*\*\*", $IP, "\*\*\*---Users Info---\*\*\*", $Users
>	 
>	 Add-Content \~\\Desktop\\recon.txt $Vars
>}

- In our function, the New-Item cmdlet creates the output file. 
- The $Vars variable stores the formatted output.
- The -Add-Content cmdlet appends the generated data to a file called recon.txt to record the results within the $Vars variable. 

#### Explanatory Comments

We will now add some comments to the code we wrote to explain what we did and why we did it:

>Import-Module ActiveDirectory
>\ 
>function Get-Recon {
>	
>	\# Collect the hostname of the PC.
>	$Hostname = $env:ComputerName
>	
>	\# Collect the IP configuration.
>	$IP = ipconfig
>	
>	\# Collect the domain information.
>	$Domain = Get-ADDomain
>	
>	\# Output the users that have logged in and build out a basic directory structure in "C:\\Users\\".
>	$Users = Get-ChildItem C:\\Users\\
>	
>	# Create a new file to place our reconnaissance results in.
>	New-Item \~\\Desktop\\recon.txt -ItemType File
>	
>	# A variable that holds the results of the other variables.
>	$Vars = "\*\*\*---Hostname Info---\*\*\*", $Hostname, "\*\*\*---Domain Info---\*\*\*", $Domain, "\*\*\*---IP Info---\*\*\*", $IP, "\*\*\*---Users Info---\*\*\*", $Users
>	
>	 # The function executes.
>	 Add-Content \~\\Desktop\\recon.txt $Vars
>}

#### Including Help

PowerShell can create Comment-Based help where you embed your own help instructions that can be called with an alias of your choosing. This means creating a comment block at the beginning or end of the script that can be called with the Get-Help cmdlet. You can also create Comment-Based help for functions by placing the comment block at the top of the function.

We will include a Comment-Based help section above our created function that explains the functionality and syntax used, as well as how to implement the function, example output, and other notes related to the module we created.

We will only include the first cmdlet and the first line of the function to demonstrate the placement and implementation of the Comment-Based help section:

>Import-Module ActiveDirectory
>\ 
><# 
>.Description
>This function performs some simple reconnaissance tasks for the user. We import the modules and issue the 'Get-Recon' command to retrieve our output. Each variable and line within the function and script are commented for our understanding. Right now, this module will only work on the local host from which you run it, and the output will be sent to a file named 'recon.txt' on the Desktop of the user who opened the shell. Remote Recon functions are coming soon!
>\ 
>.Example
>After importing the module run "Get-Recon"
>'Get-Recon
>\ 
>\ 
>	Directory: C:\\Users\\MTanaka\\Desktop
>\ 
>\ 
>Mode                               LastWriteTime                        Length   Name
>\----                                   \---------------                        \-------- \------
>\-a----                              11/3/2022 12:46                              0 recon.txt  \'
>\ 
>.Notes
>Remote Recon functions are coming soon! This script serves as our initial introduction to writing functions and scripts to make PowerShell modules.
>\ 
>#>
>\ 
>function Get-Recon {
>\<SNIP>

##### Keywords

In out Comment-Based Help section, some of the words are preceded by a period ( . ) - this indicates that they are a keyword. There are more common predefined keywords, as shown in the following link [Comment-Based Help Keywords](https://learn.microsoft.com/en-us/powershell/scripting/developer/help/comment-based-help-keywords?view=powershell-7.2 'a list of keywords for comment-based help').

#### Protecting Functions

We can use the Export-ModuleMember cmdlet to protect our function from being exported or to explicitly set it to be available for export. This means we are able to block it from being shared, or if we want others to access it or implement it into their own scripts - we can enable that. 

We can include the Export-ModuleMember in our wuick-recon.psm1 script to prevent it from being modified or used.

If we want to export all functions and variables, include a \* after the -Function modifier as follows:

>Export-ModuleMember -Function \* -Variable \*

If we WANT to export the module, we can include the following line at the end of our quick-recon.psm1 script:

>Export-ModuleMember -Function Get-Recon -Variable Hostname

#### Scope

In the context of scripts, Scope is how PowerShell recognizes and protects objects in the command line. It can prevent modification and restrict access and has three distinct levels:

- Global - all objects in a PowerShell session fall under the Global scope by default. 
- Local - This is your active scope, which is usually the default scope unless you are operating a child scope that has inherited modified objects from the parent.
- Script - This is the scope for all scripts. It is temporary and is not known by resources outside of itself. 

### Summary

After following all of the steps detailed above we now have a fully functional module with Comment-based help, functions, variables, content protection, and formatting for clarity.

#### Importing

We can now import the module with the Import-Module cmdlet and then verify that it has been properly loaded with the Get-Module cmdlet. If you want to access the Comment-based help, use the Get-Help cmdlet with the parameter Get-Recon.

Use the following command to import the module and verify that it has properly loaded:

>Import-Module 'C:\\Users\\Mtanaka\\Documents\\WindowsPowerShell\\Modules\\quick-recon.psm1'
>get-module
>get-help get-recon

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Scripting and Automation](https://academy.hackthebox.com/module/167/section/1630 'HTB academy PowerShell scripting and automation guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)