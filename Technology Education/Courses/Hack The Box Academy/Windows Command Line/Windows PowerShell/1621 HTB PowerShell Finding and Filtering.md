# Finding and Filtering Content

### PowerShell Output and Objects

While Command Prompt ( #CMD) uses text strings to assign values, everything in #PowerShell ( #PS) is an #object. 

#### Objects

An #Object is an instance of a class in the context of PowerShell. If we consider a host device as an object, the object would be composed of hardware, software, design, users, etc. 

A #Class is the #schema or unique set of properties that define an object. In the context of a host device, the class would be the blueprint that you follow to assemble the computer and install all the software and users. 

A #Property is a piece of data or an attribute of an object that is used to define the class of the object. In terms of our host device, this would be an individual hardware part or single application - each with it's own unique intention and design.

A #Method is the function of a given object. In a host device, this would be the functions it performs such as processing data, depicting an image, browsing the internet, opening applications, etc.

### Filtering and Finding

For our understanding we will focus on an individual user  as our object. The class would be the default or inherited values assigned to the user object when it is created. The properties would be the permissions of the user, nomenclature, and attributes associated with this user account. The methods would be the ability to execute files, access directories and resources, and submit data.

##### Getting Object Properties and Methods

If we want to get the Properties and Methods of a User Object, use the following command:

>Get-LocalUser administrator | get-member

##### Property Output

We can use the Select-Object cmdlet to see how PowerShell will output the properties:

>Get-LocalUser administrator | Select-Object -Property \*

This will output a list of the properties associated with the given user. 

##### Filtering Properties

We can further filter our results down to more granular bits of information.

We will look for a user's last set password with the following command:

>Get-LocalUser \* | Select-Object -Property Name,PasswordLastSet

##### Sorting and Grouping

We can use sort and group functions to make the property data more readable. In this case we will use the Sort-Object and Group-Objects cmdlets to find all users, sort them by their name, and group them based on whether they are currently enabled or not.

We can use the following command to do so:

>Get-LocalUser \* | Sort-Object -Property Name | Group-Object -property Enabled

#### Other Objects

The User object is a nice place to start because it produces limited properties that are easily readable. In the case of services, this information can be quite overwhelming as there are many services, each with many properties.

Use the Get-Service cmdlet in the following command as an example:

>Get-Service | Select-Object -Property \*

This produced an overwhelming amount of output. Filter and sort it with the following command:

>get-service | select-object -property DisplayName,Name,Status | Sort-Object DisplayName | fl

This still produces a lot of output. We can further pare this output down and ignore the objects we aren't searching for if we know the name of the service we want.

##### Where-Object

We can use the Where-Object cmdlet with the -like parameter to search for specific object names.

In this case we will look for the #Windows #Defender service by using Where-Object alias where:

>Get-Service | where DisplayName -like '\*Defender*'

This will output any service related to the term defender, and in this case should yield four results. Enumerating these services is of vital importance when determining the active services on a host device.

#### Comparison Parameters

| Parameter | Description                                                             |
| --------- | ----------------------------------------------------------------------- |
| -like     | allows for use of wildcards to search all objects for a specified term. |
| -contains | gets any object with a matching property value                          |
| -equal    | specifies a case-sensitive match for a given value                      |
| -match    | matches a regular expression ( #regex ) to a value                      |
| -not      | matches a blank property and also matches $False                                                                        |
Use these parameters in addition to the comparison operators you are already familiar with (greater than, less than, etc.) to further filter and pare down search results.

#### Applying Parameters

We can further examine how parameters apply to searching by returning to our Windows Defender example from above. When applied, we will be able to see if services are running and the limitations of what we are able to do with them.

Use the following command to output a list of Windows Defender related services and out permissions:

>get-service | where DisplayName -like '\*Defender*' | select-object -property \*

### PowerShell Pipeline

We can use the pipe ( | ) to concatenate or link commands. When we use the pipe, think of the pipe as a divider that segments our commands into a sequential order. The command on the far left will need to execute before the command to the right of the pipe can be executed. This means we can generate output and then use that output in a second command - all within a single command. Subdividing the output like this is useful and saves time and space.

Command output that is piped will process like this:

>Command1 | Command 2 | Command 3

Where Command1 will execute, then Command 2 can begin executing using that output, and so on.

Sometimes you will see piped command formatted in the following way:

>Command1 |
>>Command2 |
>>>Command3

An example command using actual cmdlets is as follows:

>Get-Process | Where-Object CPU | Where-Object Path | Get-Item |

#### Counting Unique Instances

We can use the -unique parameter and the Measure-Object cmdlet to enumerate a total number for the unique process instances in the following example:

>get-process | sort | unique | measure-object

This output will return the total amount of unique processes running on the target host. 

#### Pipeline Chain Operators

***Only versions of PowerShell newer than 5.1 can use Chain Operators. PowerShell 7 recommended.***

Chain Operators like && and || allow us to execute piped commands conditionally. 

- && tells PowerShell to execute the next piped command if the previous command successfully executes. This is an AND condition.
- || tells PowerShell to execute the next piped command if the previous command does NOT successfully execute. This is  an OR condition.

##### AND Pipeline

We can use the following command to check for a file and ping the #DNS server IF the file exists:

>get-content '.\\test.txt' && ping 8.8.8.8

##### OR Pipeline

We can run the following command to stop pinging until failure is detected:

>get-content '.\\test.txt' || ping 8.8.8.8

### Finding Data in Content

In PowerShell, the Select-String cmdlet is used to find a string within file contents or command outputs. This is similar to #grep or findstr.exe in Command Prompt ( #CMD). This cmdlet is particularly helpful when paired with #regex and the Where-Object cmdlet. The output for this command will return the line containing the string, line number, and the name of the file.

#### Finding in a Directory

There are often many filetypes and subfolders within a directory and with the Get-ChildItem cmdlet we can search these various types more efficiently.

Here is an example using the Get-ChildItem cmdlet:

>get-childitem -path C:\\Users\\MTanaka\\ -file -recurse

#### Paring Output Down

The previous command returned an overwhelming amount of output in the example case.

We can use the where cmdlet and conditional terms to pare down our output to return only names:

>get-childitem -path C:\\Users\\MTanaka\\ -file -recurse -ErrorAction SilentlyContinue | where {($\_.Name -like "\*.txt")}

This output will only return files with the .txt extension thanks to the $\_.Name attribute.

##### Using OR

We can now use the -or operator to expand out search to other file types that meet our conditions:

>get-childitem -path C:\\Users\\MTanaka\\ -file -recurse -ErrorAction SilentlyContinue | where {($\_.Name -like "\*.txt" -or $\_.Name -like "\*.py" -or $\_.Name -like "\*.ps1" -or $\_.Name -like "\*.md" -or $\_.Name -like "\*.csv")}

This output returns many more filetypes. We can now try using the Select-String cmdlet to search the returned files' content for a specific string.

### Select-String

Now that we know how to select the file extensions we want to search for, we can use the Select-String cmdlet to find our desired string within these files. 

If you want to search for case-sensitive strings, you can use the -CaseSensitive modifier. 

If you want the command to ignore errors, use the -ErrorAction parameter with the SilentlyContinue modifier.

We can use the following command to search for the strings 'Password', 'credential', and 'key':

>Get-ChildItem -Path C:\\Users\\MTanaka\\ -Filter "\*.txt" -Recurse -File | sls 'Password', 'credential', 'key'

We can combine this method from our previous file search:

>get-childitem -path C:\\Users\\MTanaka\\ -file -recurse -ErrorAction SilentlyContinue | where {($\_.Name -like "\*.txt" -or $\_.Name -like "\*.py" -or $\_.Name -like "\*.ps1" -or $\_.Name -like "\*.md" -or $\_.Name -like "\*.csv")} | sls 'Password', 'credential', 'key'

### Directories Worth Checking

- \\AppData\\ is a great place to check for configuration files and temp files.
- C:\\Users\\User\\ often has hidden folders containing VPN and SSH keys as well as passwords.
- C:\\Users\\Username\\AppData\\Roaming\\Microsoft\\Windows\\PowerShell\\PSReadLine\\ConsoleHost\_History.txt contains console data that can often be revealing.
- Get-Content (Get-PSReadlineOption).HistorySavePath
- Get-Clipboard can reveal recent copy and paste entries.
- Scheduled Tasks ( #schtasks) can reveal useful information as well.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Finding and Filtering](https://academy.hackthebox.com/module/167/section/1621 'HTB academy PowerShell finding and filtering guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)