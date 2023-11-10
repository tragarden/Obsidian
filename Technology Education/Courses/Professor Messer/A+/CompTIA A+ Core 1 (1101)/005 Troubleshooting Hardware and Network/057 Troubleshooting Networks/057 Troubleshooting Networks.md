# Troubleshooting Networks 5.7

### Diagnosis

#### Physical Issues

*No Network Connectivity* is the **most common issue** addressed when troubleshooting networks.

First you should **check the physical connections** of the devices in question. If you **discern that there is a connection via indicator lights** or link lights on the #modem or #router.

*Port Flapping* is usually **related to physical issues** with your system, this can be verified by **checking the cables** or replacing them.  The symptom is that your network will go up and down repeatedly.  If the cables are secure, you will need to determine if it is an **issue with your switch or your device**.  If this issue is resolved when you move to a new #switch #port, it is likely a sign of **bad hardware or cabling**.

#### Loopback and Ping

Next, we can ping the #loopback address (**127.0.0.1**) to **see if there is an available connection and to ensure the protocol stack is working**.  If you get a #ping returned via the loopback, then you know that communication within your device is working.

If the *loopback ping* is successful, we can **ping the local #IP address** next to see if the access point is active.  This can be used to **check the local configuration, adapter, and supply a link signal** that confirms we are connected to the network.

If the local IP is available, we can now **ping the default gateway** to check connectivity to the local #network.

Lastly, we can **ping #Google’s server** at **8.8.8.8** or alternatively **9.9.9.9** to see if we are able to connect to the internet beyond the router.

#### Interference

*If only some of the submitted pings are returned*, this indicates intermittent connectivity of the wireless network.  This could be due to **interference from other devices** using the same frequency.

*Signal strength* may be a factor – **check the antennas** within your network and try to assess signal strength throughout the premises.

Sometimes the device is set to the *wrong channel*, sometimes this **configures automatically and needs to be manually overridden**.  You can also **configure some alternative channels** to determine which settings allow for the best performance of the network.

##### Latency 

#Bounce and #latency can be **remedied by simply moving**.  You may be experiencing **interference from the pathing of the signal** as it bounces from the source to your receiving device.  Carefully **consider the location of your access point** and think about whether that is a factor in poor reception.

#Latency is the **delay between a server request and the response**.  Latency is like friction, inescapable and evident on all networks.  **Using package capture to analyze your latency can give you details on the request** and the return within microseconds of accuracy, allowing you to see every step of the way.

You can **analyze interference using third party utilities** or sometimes your own #OS. ***Common interferences include fluorescent lights, microwave ovens, cordless house phones, or sources of high-power***. 

When interference is evaluated, we use *Signal to Noise Ratios* ( #SNR) and a *Performance Monitor* to determine the amount of  #noise or #interference within our system hardware.  Noise is undesirable but expected on all networks.

### IP Addressing

#Windows will put alerts in the system tray like **‘Limited or No Connectivity’** when you are experiencing network issues.  **Check your local IP** address, if your IP wasn’t configured by your #DHCP, you may have an *Automatic Private IP Address* ( #APIPA) which **will only have local connectivity**.  This device with an APIPA would only be able to communicate with other devices on the local network.

*If you have obtained an IP from the DHCP* server, **perform ping tests on the local gateway and a remote IP** address.

### Jitter

#Jitter is the time between frames of packets coming through, and this gap in information is what causes choppy streams of #audio and video. 

*Jitter* could be explained as the **garbled and distorted ‘underwater’ or ‘robot’ sounds and visuals** that we sometimes get during a call or #video chat.  This is because you are transmitting data in real time and **data is sensitive to delay**.  The data should arrive constantly and in regular intervals, but this is interrupted causing gaps in the information.  In these cases, a #packet is not received, yet there is no attempt to retransmit the packet – similar to how you cannot rewind a phone call.

#VoIP requires a *high speed and low latency network*, so **if the internet is slowed you will have poor VoIP quality.** Check your internet connection via **speed test**, which can be used to identify slow links in the network.  If speeds are adequate, **check the #hardware of the network** – an old #router and other technologies can cause issues with the quality of signal.  If all of these things check out, **use packet capturing technology to analyze your network performance**.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/troubleshooting-networks-comptia-a-220-1101-5-7/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [016 Windows IP Address Configuration](016%20Windows%20IP%20Address%20Configuration.md)
- [051 How to Troubleshoot](051%20How%20to%20Troubleshoot.md)
- [052 Troubleshooting Common Hardware Problems](052%20Troubleshooting%20Common%20Hardware%20Problems.md)
- [121 Introduction to IP](121%20Introduction%20to%20IP.md)
- [225 Assigning IP Addresses](225%20Assigning%20IP%20Addresses.md)

#study #professormesser #comptia #Aplus #accesspoint #defaultgateway #network #portflapping