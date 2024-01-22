# PowerShell Registry

### Windows Registry

The #Windows #Registry is a hierarchical tree of keys and values that allow the Operating System ( #OS) and software to run via subtrees. This is one of the more complicated aspects of Windows and can be difficult to understand, but is of vital importance when performing penetration tests or otherwise managing system security. 

While the data within the registry can be found elsewhere in our operating system, the registry consolidates all of this information in a single place that is difficult to protect and allows for a lot of modifications. Attackers will be able to wreak havoc in the registry unlike no other single space in our operating system.

#### Keys

Registry Keys are containers that represent components of the computer by holding values and other keys. Key nomenclature uses alphanumeric characters that are not case-sensitive. A single key may hold many other keys in it's hierarchical structure. 

##### Root Keys

Root keys are also known as root registry keys - they are public and private key combinations that contain other keys for the host computer. These root keys are primarily stored within the path C:\\Windows\\System32\\Config\\, yet there are other registry hives within the file system. 

[List of Root Keys](https://learn.microsoft.com/en-us/windows/win32/sysinfo/registry-hives 'microsofts list of root keys')

#### Values

Values are data in object form that are associated with a specific key. Values are composed of a name, type, and identifying data. Root keys contain nested Installer keys, which contain values. There are 11 value types.

[List of Values](https://docs.microsoft.com/en-us/windows/win32/sysinfo/registry-value-types 'Microsofts list of values')

#### Registry Hives

There are five Registry Hives on Windows by default:

| Name                | Acronym | Description |
| ------------------- | ------- | ----------- |
| HKEY_LOCAL_MACHINE  | HKLM    | Contains data about physical components, hardware, drivers, memory, OS data, and bus types.            |
| HKEY_CURRENT_CONFIG | HKCC        | Shows the differences between default and current hardware configurations.            |
| HKEY_CLASSES_ROOT   | HKCR        | Data on file types, user interface, extensions, and backward compatibility settings.            |
| HKEY_CURRENT_USER   | HKCU        | Contains software and OS data for users, preferences, and Roaming Profile configurations.            |
| HKEY_USERS          | HKU        | Contains Default user profile and settings for current user.            |
More [Predefined Keys](https://learn.microsoft.com/en-us/windows/win32/sysinfo/predefined-keys 'list of predefined keys from Microsoft') from #Microsoft for other OS versions.

### Accessing Registry

#### reg.exe

The executable reg.exe is a #DOS based method for accessing and managing the registry. This  should be available on systems without modern iterations of PowerShell.

#### Get-Item

The Get-Item and Get-ItemProperty cmdlets allow us to read the keys and values within the Registry.

We can use the Get-Item and Select-Object cmdlets to see the services and applications running on the target host with the following command:

>get-item -path Registry::HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Run | Select-Object -ExpandProperty Property

#### Recursive Search

We can use the cmdlets Get-ChildItem and the -recurse parameter to identify keys and values within a hive with the following command:

>Get-ChildItem -Path HTLM::\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion -recurse

#### Get-ItemProperty

The output from the previous command is quite expansive and difficult to read. 

We can use the Get-ItemProperty cmdlet to reduce output content to be more readable with the following command:

>Get-ItemProperty -path Registry::HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Run

This output will return the name of services and their associated value needed to run them. The Registry key is used to start the services upon logon. This information is quite useful in the realm of penetration testing.

#### reg.exe

We can use the reg.exe command to query registry keys to output their values with the following command:

>reg query HKEY_LOCAL_MACHINE\\SOFTWARE\\7-Zip

This will return two values: Path and Path64 with the value type Reg-SZ indicating that it is in Unicode or ASCII. 

### reg query

Let's break down the following command to see how the reg.exe command is used:

>REG QUERY HKCU /F "Password" /t REG_SZ /S /K

- reg query calls the reg.exe function.
- HKCU sets the path to HKey_Current_User
- /f "Password" sets the pattern to search for
- /t REG_SZ sets the value type we are searching for
- /s searches every key and value recursively
- /k limits the search to only key names

### Creating and Modifying Keys and Values

#### New Registry Key

We can create a new Registry Key with with the following command:

>New-Item -Path HKCU:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce\\ -Name TestKey

#### New Registry Item Property

Use the following command to create a value named 'access' and assigning it to payload.exe:

New-ItemProperty -Path HKCU:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce\\TestKey -Name "access" -PropertyType String -Value "C:\\Users\\htb-student\\Downloads\\payload.exe"

Alternatively you could use the following command to employ reg.exe:

>reg add "HKEY_CURRENT_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce\\TestKey" /v access /t REG_SZ /d "C:\\Users\\htb-student\\Downloads\\payloads.exe"

Either of these commands would effectively place a payload for execution on the target host.

#### Delete Reg Properties

Use the following commands to remove and verify the removal of the property we created:

>Remove-ItemProperty -Path HKCU:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce\\TestKey -Name "access"
>Get-ItemProperty -Path HKCU:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce\\TestKey

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Registry](https://academy.hackthebox.com/module/167/section/1623 'HTB academy PowerShell registry guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)