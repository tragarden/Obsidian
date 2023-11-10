# On-Path Attacks

#On-path Attacks are formerly known as *man-in-the-middle attacks.*  These methods **redirect your internet traffic, capture or modify the data, and send it back into the data-stream** without your knowledge that anything has happened.

#ARP Poisoning is used to **attack the #subnet of a local #IP as the ARP has no #security and is easily exploited.** Since ARP operates on your local network, it **does not follow security protocols and will willingly connect to any ARP associations that make logical sense.**  The client requests the #router IP via #broadcast transmission, the router responds and says, ‘Here I am, and this is my #MAC address”.  This **MAC address is added to the client’s ARP cache for a limited amount of time** – then this entire process begins again.  

**An On-Path attacker will respond to the ARP broadcast** request from the client **and PRETEND to be the #router,** claiming to have the same IP but **responding faster than the router responds.**  The attacker then claims that their MAC address is the REAL address, and it will be added to the client’s cache in place of the router.  The attacker has successfully intercepted the signal and is moderating communications between the two devices.

#On-Path #Browser attacks occur by trojan horse or other malware proxy and are formerly known as *man-in-the-browser* attacks.  Even encrypted traffic is easy to #proxy and capture without the victim having any awareness.  This style of attack will **let someone watch your browser submissions** and collect your bank credentials when you log into your account.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/on-path-attacks-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [023 Malware](023%20Malware.md)
- [023 Anti-Malware Tools](023%20Anti-Malware%20Tools.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [033 Removing Malware](033%20Removing%20Malware.md)

#study #professormesser #comptia #Aplus #trojanhorse #malware