# Nmap Performance

When using a *Network scanner* like #Nmap we will experience **varying levels of performance** depending on the target host we are attacking, the #network we a communicating over, and the #hardware of our own machine.

#Nmap commands can be **modified with options that control the different aspects of the scan**. We can **manage the speed** at which the test is completed, the **frequency of requests**, #packet #timeout ranges, **retry attempts**, and how many packets can be simultaneously sent.

### Modifications

#### Timeouts

When nmap is scanning a target there is a designated amount of time it will wait for a response before determining that the resource is unavailable. This is known as a #timeout period and the **nmap tool refers to this as** the *Round-Trip-Time* ( #RTT). 

For an example of the default #RTT settings, run the following command and observe the time it takes to complete the scan:

>sudo nmap 10.10.2.0/24 -F

We can set different timeout limits with the option *--min-RTT-timeout* and the following command:

>sudo nmap 10.10.2.0/24 -F --initial-rtt-timeout 50ms --max-rtt-timeout 100ms

You will notice that the ***second scan produced less results*** than the first scan but it completed the scan ***4 times as fast***. Some hosts will need more than 50-100ms to issue a response.

#### Retries

If Nmap does not detect a response from a host during the #timeout period described above, it will **retry the connection attempt for a set amount of times**. The **default value is 10 retries**, but we can modify this with the *--max-retries* option.

Perform the following scan to observe how the default settings behave:

>sudo nmap 10.10.2.0/24 -F | grep "/tcp" | wc -l

After performing that scan, perform the following scan with modified retries:

>sudo nmap 10.10.2.0/24 -F --max-retries 0 | grep "/tcp" | wc -l

Once again you will notice that the ***second scan completed notably faster while missing a few results***.

#### Rates

In certain circumstances we will know the #bandwidth limits of our target network. If we know this, **we can then adjust the amount of packets that are simultaneously sent over the #network** with the *--min-rate option*. This can speed up our test significantly. 

Perform the following scan to observe the behavior of the default settings:

>sudo nmap 10.10.2.0/24 -F -oN tnet.default

Perform the following scan with modified rate limits and observe the difference:

>sudo nmap 10.10.2.0/24 -F -oN tnet.minrate300 --min-rate 300

We can then **use the cat command with the file we created to view the open ports** of each of these scans:

>cat tnet.default | grep "/tcp" | wc -l

>cat tnet.minrate300 | grep "/tcp" | wc -l

#### Timing

We can **modify the aggressiveness** of our scanning with the -T flag and our choice from six scan models. ***When we increase how aggressive a scan is we increase the load on the target network which could reveal our presence*** to *Intrusion Detection Systems* ( #IDS) and *Intrusion Prevention Systems* ( #IPS). 

We can assign how aggressive our timing is with the following flags. **By default nmap uses -T3**:

- -T0 / -T paranoid
- -T1 / -T sneaky
- -T2 / -T polite
- -T3 / -T normal
- -T4 / -T aggressive
- -T5 / -T insane

Run the following scan to observe the default behavior and record it:

>sudo nmap 10.10.2.0/24 -F -oN tnet.default

Run the following scan on 'insane' settings so we can compare the scans:

>sudo nmap 10.10.2.0/24 -F -oN tnet.T5 -T5

Now you can **cat the files** and review the differences between the scans:

>cat tnet.default | grep "/tcp" | wc -l

>cat tnet.T5 | grep "/tcp" | wc -l

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Nmap Performance](https://academy.hackthebox.com/module/19/section/105 'HTB academy performance and nmap')
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)
- [221 Common Network Ports](221%20Common%20Network%20Ports.md)
- [Network Security Guide](Network%20Security%20Guide.md)