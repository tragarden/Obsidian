# Detection and Analysis Part 2

Once we begin our investigation we will **use a cyclical process with three distinct steps to discover the means by which an incident has occurred**. 

### Investigation Steps

We will take the data from our initial investigation and put it through a three step process to **determine the origin of the attack**. These steps are:

- Creation and usage of the *Indicators of Compromise* ( #IOC)
- Identification of leads and affected systems
- Data collection and further analysis

#### Creation and Usage of IOCs

*Indicators of Compromise* ( #IOC) are **artifacts leftover from the incident**. These may be #IP addresses, #hash values, or files used to perpetrate exploits on our systems. It is important to **document and occasionally use these IOCs in our determination processes** to discover what happened during our incident. These can be documented and implemented with applications such as #OpenIOC, #Yara,  and #Mandiant IOC editor.

In order to discover these artifacts of the incident, we can use IOC searching tools to find them. *Windows Management Instrumentation* ( #WMI) and #PowerShell can be used  to discover IOCs on our systems. It is important to note that ***Windows applications often cache user credentials, which may create new vectors for attack***. You must ***have awareness of which Windows tools cache user credentials*** when performing this part of the incident response. #WinRM and #PSExec are examples of Windows tools that cache user credentials. 

#### Identifying Leads

The scanning tools we used in the previous step will likely determine that other aspects of our network are susceptible to attack in the same way our targeted system was. You must identify which of these pose *actual* threats as **many of them will be cases of false-positives by the detection tools**.

#### Data Collection from Impacted Systems

Now that we have discovered IOCs and any new leads, we will want to **capture the state of the system for our research**. This means **creating an image of the system while it's in the state that the incident occurred under**. It is worth noting that many ***artifacts / IOCs are stored within the RAM of the affected devices, so turning them off will effectively destroy any evidence*** of the attack. Once Live analysis has been performed we can document our finding and validate any leads that are truly threats.


### Related:

- [HTB Academy Home Page](https://academy.hackthebox.com/ 'HTB Academy home page')
- [HTB Academy D&A Part 2 Module](https://academy.hackthebox.com/module/148/section/1368 'HTB D&A part 2 module')