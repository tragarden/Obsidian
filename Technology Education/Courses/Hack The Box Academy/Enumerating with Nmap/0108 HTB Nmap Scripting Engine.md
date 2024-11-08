# Nmap Scripting Engine

#Nmap *Scripting Engine* ( #NSE) makes it possible to execute scripts in the #Lua language. There are 17 different categories these scripts are sorted into:

1. auth - authentication credentials
2. broadcast - host discovery via broadcasting
3. brute - brute-force credentials
5. default - default scripts under the -sC flag
7. discovery - available services and description
8. dos - examines denial of service vulnerabilities
9. exploit - exploits known vulnerabilities on a given port
10. external - external services used
11. fuzzer - a time-consuming script that identifies vulnerabilities by sending different fields
13. intrusive - intrusive scripts that may have adverse affects
14. malware - identifies malware on the target
15. safe - defensive scripts that pose no harm
16. version - service detection
17. vuln - identifies vulnerabilities

### Scripting Commands and Flags

##### Default

>sudo nmap \<target> -sC

##### Specific Scripts

>sudo nmap \<target> --script \<script category>

##### Defined Scripts

>sudo nmap \<target> --script \<script-name>,\<script-name>,...

##### Specified Scripts

We can use the following command to run banner and #smtp scripts on port 25:

>sudo nmap 10.10.2.28 -p 25 --script banner,smtp-commands

##### Aggressive Scanning

We can use the -A flag to perform an aggressive scan. This option will invoke several other options such as: 
- Service Detection -sV
- #OS Detection -O
- Traceroute --traceroute 
- Default scripts -sC

#### Vuln

We can use the *vuln* option to detect vulnerabilities on port 80 with nmap:

>sudo nmap 10.10.2.28 -p 80 -sV --script vuln

This should return output with version information and any related known vulnerabilities.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Nmap Scripting Engine](https://academy.hackthebox.com/module/19/section/108 'HTB academy  nmap scripting engine')
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [048 Scripting Use Cases](048%20Scripting%20Use%20Cases.md)
- [048 Scripting Languages](048%20Scripting%20Languages.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)