# IDS Evasion EASY LAB

I used the following command to enumerate the open ports on the target host:

>sudo nmap 10.129.2.80  -T2 -Pn -n

Performing this scan alerted the IDS / Firewall 52 times out of the maximum allowed limit of 100.

After determining that port 22/tcp SSH was open, I decided to use netcat to reveal more information with the following command:

>nc -nv 10.129.2.80 22

This revealed that the target host was using Ubuntu as it's OS.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Firewall and IDS Evasions Lab Easy](https://academy.hackthebox.com/module/19/section/117 'HTB academy IDS and firewall evasion lab easy')
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)