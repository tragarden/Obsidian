# Modules and CMDlets

### cmdlets

A #cmdlet is a single command capable of manipulating PowerShell objects. Cmdlets are named using a verb-noun format so that users can intuitively know what each cmdlet is used for. This also simplifies searching the help manual because you can simply enter a verb such as "get" or "set" and view the whole list of nouns these verbs will apply to. The main difference between cmdlets and PowerShell functions is that cmdlets are NOT written in PowerShell language - they are written in C# and then compiled.

### Modules

A #PowerShell module is coded in PowerShell language and is composed of several components:

- cmdlets
- script files
- functions
- assemblies
- resources
- manifests
- help files

### PowerSploit

PowerShellMafia created the PowerSploit project that is used as a toolkit for pentesters. We will use the PowerView.ps1

PowerSploit.psd1 is a PowerShell Data ( #psd) file, and in this case it is a Module manifest file. These types of file contain several components:

- References to the module 
- Version numbers
- #GUID 
- Author name
- Copyright information
- Information about PowerShell compatibility
- Included modules
- Included cmdlets
- Metadata

PowerSploit.psm1 is a PowerShell script module ( #psm) file that contains the PowerShell code. 

#### Get-ChildItem

We can use the following command to read the contents of this file:

>Get-ChildItem $PSScriptRoot | ? { $\_.PSIsContainer -and !('Tests', 'docs' -contains $\_.Name) } | % { Import-Module $\_.FullName -DisableNameChecking }

#### Get-Module

If we run the Get-Module cmdlet we will be able to view a list of all the modules that are loaded into  PowerShell.

##### List-Available

We can use the -List-Available modifier with Get-Module to show additional modules that are installed but not currently loaded.

#### Import-Module

The Import-Module cmdlet will import a chosen module into our current PowerShell session. 

Issue the following command to learn more about the Import-Module cmdlet:

>Get-Help Import-Module

When we import a module, we often get various new cmdlets that come with the module package. If we want to acquire the Get-NetLocalGroup cmdlet, we need to download the PowerSploit module.

Import the PowerSploit module and run the Get-NetLocalgroup cmdlet with the following commands:

>Import-Module .\\PowerSploit.psd1
>Get-NetLocalGroup

#### PSModulePath

We can permanently add modules to PowerShell by modifying the #PSModulePath. We can do so with the following command:

>$env:PSModulePath

### Execution Policy

The #Microsoft Execution Policy is a tool for IT administrators to prevent themselves from executing a potentially damaging script. Many of our imported modules will have cmdlets that the execution policy does not allow by default - thusly we must modify the policy to enable them.

#### Policy State

We can check the state of our Execution Policy with the following command:

> Get-ExecutionPolicy

If this returns output saying "Restricted" we will then need to modify the policy.

#### Setting Policy 

We can use the Set-ExecutionPolicy cmdlet to remove the restrictive policy. 

We will need to set the policy to undefined with the following command:

>Set-ExecutionPolicy undefined

Now we should be able to execute modules and cmdlets that were previously restricted by the policy. It is important to revert these changes when we are done, especially if we are working professionally as a pentester on a client's machine. If we do not do this, their defensive measures may detect this as a breach of security.

A simple way to guarentee that we have reverted changes is to run the policy changes as a Process, which will only last until we close out PowerShell session.

#### Execution Policy Scope

We can set the scope of the Set-ExecutionPolicy to only persist for the duration of the PowerShell session with the -scope and Process modifiers. 

We can enact this scope with the following commands:

>Set-ExecutionPolicy -scope Process
>Get-ExecutionPolicy -list

This should toggle the scope of the policy to only include our current session. We should then be presented with the list of policy rules for our current session.

### Calling cmdlets

#### Get-Command

If we want to retrieve the list of imports such as aliases, cmdlets, and functions - we will use the Get-Command cmdlet with the -Module modifier.

Use the following command to see the list of imports that came with PowerSploit:

>Get-Command -Module PowerSploit

This should output a full list of the objects that were imported with PowerSploit. We can then simple pick and choose which of these imports we want to use and run them.

### PowerShell Gallery

[PowerShell Gallery](https://www.powershellgallery.com/ 'Powershell Gallery repository for modules) is a repository for scripts, modules, cmdlets, aliases, and much more created by #Microsoft. This is worth exploring as there are many tools across a range of complexity.

#### PowerShellGet

#PowerShellGet is a built-in module for PowerShell that helps us browse and import modules from the PowerShell Gallery. 

#### AdminToolbox

The AdminToolbox module is a collection of modules that manage many System Administrator tasks like Active Directory, Microsoft applications, virtualization, and much more.

#### Find-Module

The Find-Module cmdlet can be used to find the AdminToolbox:

>Find-Module -Name AdminToolbox

#### Install-Module

After using Find-Module to view the desired modules, we can then install them with the Install-Module cmdlet. 

Use the following command to employ the Find-Module and Install-Module cmdlets to install the AdminToolbox:

>find-module -Name AdminToolbox | Install-Module

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Modules and Cmdlets](https://academy.hackthebox.com/module/167/section/1636 'HTB academy PowerShell modules and cmdlets guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)