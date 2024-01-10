# IDS Evasion HARD LAB

I began this lab with the script dns-brute since that was successful during the last lab.

##### dns-brute script on port 21 to enumerate services

>sudo nmap 10.129.2.47 21 --script dns-brute

The first thing I noticed - before I even ran ANY scans, the IDS was being alerted to an intruder. Not sure if this lab is bugged. When I ran the command, many alerts were generated and fewer results were presented than when used in the Medium lab.

I then reviewed my notes from the IDS and Firewall Evasion module and tried a command for examining the firewall:

>sudo nmap 10.129.2.47 -n -Pn -p 445 -O

This revealed port 445/tcp as a filtered port for microsoft-ds

Then I ran another command from the evasion module:

>sudo nmap 10.129.2.47 -n -Pn -p 445 -O -S 10.10.2.200 -e tun0

This did not seem to be a viable means of scanning.

>setup_target: failed to determine route to 10.129.2.47

Feeling pretty unsure of what to do, I tried the proxy command from the evasion module:

>sudo nmap 10.129.2.47 -p 50000 -sS -Pn -n --disable-arp-ping --packet-trace

Which yielded the following result:

PORT      STATE    SERVICE
50000/tcp filtered ibm-db2

Then I tried the following from the evasion module:

>sudo nmap 10.129.2.47 -p 50000 -sS -Pn -n --disable-arp-ping --packet-trace --source-port 53

This produced results that were identical to the last scan.

Now I will try to use these ports to perform a netcat scan:

>ncat -nv --source-port 53 10.129.2.47 50000

Which was blocked via the following statement:

>libnsock mksock_bind_addr(): Bind to 0.0.0.0:53 failed (IOD #1): Permission denied (13)

### New scan methods

I got frustrated with lack of results with the previous scans and decided to use a very aggressive scan against the host target:

>sudo nmap 10.129.2.47 -A -T5

Yielding the following results:

>869 closed tcp ports (conn-refused), 129 filtered tcp ports (no-response)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 71c189907ffd4f60e054f385e6356c2b (RSA)
|   256 e18e531842af2adec0121e2e54064f70 (ECDSA)
|_  256 1accacd4945cd61d71e739de14273c3c (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Apache2 Ubuntu Default Page: It works
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Ironically avoiding evasion technique gave more results than any other scan. I was detected by the IDS however.

### New Approach

After reading threads related to this module and various other resources, I was guided to the information I recovered earlier in my scans:

>PORT      STATE    SERVICE
50000/tcp filtered ibm-db2

I then tried running the command:

>sudo nc -nv 10.1299.2.47 50000

which revealed that I don't have permission to access this port.

after reviewing the module for IDS evasion, I decided that the DNS server information I retrieved in the medium lab might be a key.

>| dns-nsid: 
|_  bind.version: HTB{GoTtgUnyze9Psw4vGjcuMpHRp}

I then tried to run the banner script on port 50000 with the service ibm-db2

>nmap 10.129.2.47 -p 50000 -T2 --script banner

This didn't reveal new information. I modified my command as follows:

>nmap 10.129.2.47 -Pn -n -p -sV 50000 -T2 --script banner

Which yielded the same results.

Then I tried to perform a netcat scan against this port using the --source-port option after reviewing the material.

>sudo ncat -nv --source-port 53 10.129.2.47 50000

This command allowed me to connect to the service and get the flag!!!!!!!!!!!

>Ncat: Version 7.93 ( /https://nmap.org/ncat )
Ncat: Connected to 10.129.2.47:50000.
220 HTB{kjnsdf2n982n1827eh76238s98di1w6}

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Firewall and IDS Evasions Lab Hard](https://academy.hackthebox.com/module/19/section/119 'HTB academy Firewall and IDS Evasions Lab Hard')
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)