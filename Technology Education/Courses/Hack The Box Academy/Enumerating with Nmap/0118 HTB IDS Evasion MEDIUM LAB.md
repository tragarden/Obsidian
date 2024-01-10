# IDS Evasion MEDUIM LAB

Based on results from the Easy lab I used the following command to examine port 53 on the target host:

##### Service Version Scan on 'DNS port' 53 with low aggressiveness

>sudo nmap 10.129.2.48 -p 53 -T1 -sV --max-retries 5

This revealed that port 53/tcp is filtered, likely by a firewall. This is a domain service.

##### ACK scan no ping

I then used :

> sudo nmap 10.129.2.48 -p 53 -T1 -sA -Pn --max-retries 5

Which provided less results than my first scan

##### ACK scan no ping no DNS resolution

I then modified this scan:

>sudo nmap 10.129.2.48 -p 53 -T1 -sA -Pn -n

##### ACK scan on 4 ports no ping no dns resolution no arp ping 

I then tried the following command for ACK scan:

>sudo nmap 10.129.2.48 -p 21 22 25 53 -sA -Pn -n --disable-arp-ping --packet-trace

##### netcat on port 21 and 53

I then ran a netcat scan of port 21 and 53:

>nc -nv 10.129.2.48 21

>nc -nv 10.129.2.48 53

with the following results for port 53:

220 ProFTPD 1.3.5a Server (Debian) \[::ffff:10.129.2.48]

##### Decoy scan with 5 fake IPs

I then used the following scan with a decoy:

>sudo nmap 10.129.2.48 -p 21 22 25 53 80 443 -sS -Pn -n --disable-arp-ping --packet-trace -D RND:5

so far all results point to port 21/tcp, the filtered port.

I closed out the terminal and googled the question from the module.

I immediately saw a solution using scripts. As soon as I saw that I went to the list of scripts from nmap and searched for scripts related to DNS

### Next Session

##### Service discovery script with service version discovery

I then tried to run the following script broadcast-dns-service-discovery:

>sudo nmap 10.129.76.44 -p 21 -Pn -n -T1 --disable-arp-ping --script broadcast-dns-service-discovery -sV -v

This revealed port 21 as 'open' for the first time.

##### dns-cache-snoop script

then I ran the script dns-cache-snoop:

>sudo nmap 10.129.76.44 -p 21 -Pn -n -T1 --disable-arp-ping --script dns-cache-snoop

no new data revealed

##### dns-service-discovery script

Then I ran the script dns-service-discovery:

>sudo nmap 10.129.76.44 -p 21 -Pn -n -T1 --disable-arp-ping --script dns-service-discovery

no new results

##### dns-nsid script

Then I ran the script dns-nsid:

>sudo nmap 10.129.76.44 -p 21 -Pn -n -T1 --disable-arp-ping --script dns-nsid

also nothing lol.

Then I used 

>sudo nmap 10.129.76.44 -p 21 -Pn --disable-arp-ping --script dns-nsid

no new results

### Less Flags

I ran the script dns-brute on the FTP port 21 with less flags. Maybe -n and -Pn were causing issues.

>sudo nmap 10.129.76.44 21 --script dns-brute

yielding the following results

PORT    STATE    SERVICE
21/tcp  open     ftp
22/tcp  open     ssh
53/tcp  open     domain
80/tcp  open     http
110/tcp open     pop3
139/tcp open     netbios-ssn
143/tcp open     imap
445/tcp filtered microsoft-ds

based on these results I am thinking that the flags were definitely impeding my scans.

##### dns-brute script

then I ran the same command on port 53:

>sudo nmap 10.129.76.44 53 --script dns-brute

This produced the same results as the last scan, but with an added result:

>Host script results:
|_dns-brute: Can't guess domain of "10.129.76.44"; use dns-brute.domain script argument.

##### dns-nsid script with less flags on port 53

Then I tried to run the script dns-nsid on the port with less flags than last time.

>sudo nmap 10.129.76.44 53 --script dns-nsid

This scan took much longer than any other scan I ran against the target. About 5 minutes, although it didn't register too many alerts against the firewall with respect to the length of the scan.

At 99.99% complete the scan stopped working and the recorded alert count continuously increased.

Although this triggered the IDS flagging me as detected, I was able to get the flag for the exercise!!!

> dns-nsid: 
_  bind.version: HTB{GoTtgUnyze9Psw4vGjcuMpHRp} 

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Firewall and IDS Evasions Lab Medium](https://academy.hackthebox.com/module/19/section/118 'HTB academy Firewall and IDS Evasions Lab Medium')
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)