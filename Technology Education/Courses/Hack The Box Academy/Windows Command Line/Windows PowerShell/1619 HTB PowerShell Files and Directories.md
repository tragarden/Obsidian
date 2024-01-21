# Files and Directories in PowerShell

There are many cmdlets for the management of files and directories in #PowerShell. 

#### Cmdlets

| Cmdlet | Aliases | Description |
| ---- | ---- | ---- |
| Get-Item | gi | Retrieves and object |
| Get-ChildItem | ls / dir / gci | Lists directory contents |
| New-Item | md / mkdir / ni | Creates new objects |
| Set-Item | si | Modifies object properties |
| Copy-Item | copy / ci / cp | Duplictes an object |
| Rename-Item | ren / rni | Renames an object |
| Remove-Item | rm / del / rmdir | Deletes an object |
| Get-Content | cat / type | Displays the contents of a file |
| Add-Content | ac | Appends content to a file |
| Set-Content | sc | Overwrites file contents |
| Clear-Content | clc | Clears a file without deleting it |
| Compare-Object | diff / compare | Compare an object and it's content with another object |
### Creating File and Folder Structures

In this module we will go through the process of creating a folder structure for the user Mori Tanaka. This will be imported into Tanaka's computer when they become an official employee. We will use the following series of commands and processes to accomplish this.

##### Determining Location

To figure out where we are beginning within the existing file structure, use the following command:

>Get-Location

Move to the Documents folder:

>cd Documents

##### Create the Parent Directory

Create a new Directory named 'SOPs':

>new-item -name "SOPs" -type directory

##### Create Nested Folders

Now the main directory has been created. Move on to the sub-folders nested within:

>cd SOPs
>mkdir "Physical Sec"
>mkdir "Cyber Sec"
>mkdir "Training"
>Get-ChildItem

The last line should show the new nested folders within the directory SOPs.

##### Create Markdown Files

Next we will create #Markdown files with a given header in each of the nested folders.

The header is as follows:

>Title: Insert Document Title Here
>Date: x/x/202x
>Author: MTanaka
>Version: 0.1 (Draft)

We will use the following series of command to create the markdown files:

>new-item "Readme.md" -ItemType File
>cd '.\\Physical Sec\\'
>ls
>new-item "Physical-Sec-draft.md" -ItemType File
>cd ..
>cd '.\\Cyber Sec\\'
>new-item "Cyber-Sec-draft.md" -ItemType File
>cd ..
>cd '.\\Training\\'
>ls
>new-item "Employee-Training-draft.md" ItemType File
>cd ..
>tree /F

The last line should show a completed and accurately nested folder structure with the files.

##### Add Header to Files

Now we will add the header content to each of these files with:

>Add-Content .\\Readme.md "Title: Insert Document Title Here
>>>Date: x/x/202x
>>>Author: MTanaka
>>>Version: 0.1 (Draft)"

>cat .\\Readme.md

Repeat this for each of the Markdown files we created. This is a tedious process but is good practice until we automate this with scripts in a later module.

##### Renaming Files

MTanaka wants to rename the "Cyber-Sec-Draft.md" file to "Infosec-SOP-draft.md".

Change directories until you are in the 'Cyber Sec' folder and rename the file with the following commands:

>ls
>Rename-Item .\\Cyber-Sec-draft.md -NewName Infosec-SOP-draft.md
>ls

##### Changing File Format

MTanaka wants all of the .txt files on his Desktop to be changed to .md files. Use the following commands after ensuring you are in the Desktop directory:

>ls
>get-childitem -Path \*.txt | rename-item -NewName {$\_.name -replace ".txt",".md"}
>ls

##### Setting Permissions

Permissions within the New Technology File System ( #NTFS) can be assigned to a parent directory so that all child items inherit the same set of permissions. 

Permission types include:

- Full Control - allows the user to modify a file in any way they want. 
- Modify - allows a user to read, write, and delete a file.
- List Folder Contents - allows a user to view and list folders, and execute files within.
- Read and Execute - allows a user to view file contents and run executables.
- Write -  allows a user to add content to files and create new folders and files.
- Read - allows a user to view and list folders. Can also view file contents.
- Traverse Folder - allows a user to access files and subfolders - but not the parent directory.
### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Files and Directories](https://academy.hackthebox.com/module/167/section/1619 'HTB academy PowerShell files and directories guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)
- [Markdown Syntax](Markdown%20Syntax.md)
- [The 6 Most Important Keys to Typing in Markdown](The%206%20Most%20Important%20Keys%20to%20Typing%20in%20Markdown.md)