# Cross-Site Scripting 2.4

### Types of XSS

*Cross-Site Scripting* ( #XSS) is called so because this method of attack **started with security flaws of browsers where information from one site is shared** with another.  This is an exploit that **takes advantage of a flaw in code, **so having strong knowledge about the codling language you use is vital for defending against these vulnerabilities.

#### Reflected XSS

#Reflected ( #non-persistent) XSS happens when **sites allow scripts to run within user input spaces** like the search bar.  Sometimes the **attacker will send a link via #email that runs a script and exploits the #vulnerability, yielding credentials, session IDs, or #cookies** that the attacker can use to gather more data.  Another method is to **embed a #script into the #URL of the victim’s browser.**

An attacker can use a session ID ( #SSID) or cookies to recreate the same data presentation that another user obtained by using their credentials.  They are effectively able to **use your session ID to view your account from their browser.**

#### Stored XSS

#Stored ( #persistent) XSS  **uses a malicious payload to broadly attack no specific target.**  It is called persistent because **anyone that sees the script will run it.**  A common example of this is to post a **comment to a social media page that contains malicious code** causing everyone that sees the comment to run the #script.

#Subaru vehicles were **hacked in June 2017 when security researcher Aaron Guzman recognized that his Subaru had a #web-based front end.** He was able to hack into this system and realized that a single token was allocated for the life of the device, allowing anyone with a Subaru #token to log into your vehicle and control it. All it really required was for a Subaru owner to click a malicious link via #email.

Developers will need to validate user input to counter these types of attacks.  This will prevent any user from adding scripts to input fields. **Update your software and browsers with regularity.**  You could **disable** #JavaScript, although this will not thoroughly protect you and can crash sites you’re visiting.  **Avoid links within emails,** this is the most common way these attacks are executed.

#### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/cross-site-scripting-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [023 Malware](023%20Malware.md)
- [023 Anti-Malware Tools](023%20Anti-Malware%20Tools.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [033 Removing Malware](033%20Removing%20Malware.md)

#study #professormesser #comptia #Aplus #SSID