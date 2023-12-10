# Web Apps

Web applications are different from a standard website. They use client-server architecture providing a front-end and back-end that allow for real-time control over design. Google Docs and G-mail are examples of common web apps.

Static sites are websites that cannot be changed in real-time and only represent a set of data that doesn't change and isn't interactable. This is also known as Web 1.0.

Web apps are considered advents of Web 2.0 and offer real-time modifications and an interactive user experience. These are modular in nature and adaptable to nearly any size display or run on any platform.

You can think of web apps as a native OS application that you don't have to download or install. The server hosting it runs the application and presents it through the browser, allowing a user on any OS anywhere to use it.

While there are obvious benefits to using web apps, they do have some disadvantages when compared to their native OS counterparts. Native OS apps are often faster, more powerful, and offer integrations otherwise unavailable. Native OS apps offer more control and configuration to a user.

Attacks on Web Applications are increasingly common and often rewarding to the attacker as once infiltrated, they offer boundless access to resources and confidential data. These are a major vector for attack because due to their nature of design, they offer a very large attack surface that is available to anyone with a browser and internet connection. Penetration testers must have a firm understanding of how Web Apps work because this is an increasingly desired role in cyber-security as the volume of attacks increases.

When a penetration tester is analyzing the web app for vulnerabilities, they often begin with the front-end; specifically #HTML. #CSS, and #JavaScript - known as the Front End Trinity. These languages are often vulnerable to attacks such as Sensitive Data Exposure and Cross-Site Scripting ( #XSS).

Common methods of attack against a web app include:

- #SQL Injection, where Active Directory usernames are compromised and a password spraying attack is used against the email portal.
- File Inclusion refers to examining source code to discover hidden directories or site navigations that enable remote code execution.
- Unrestricted File Upload is when there are no limits on filetype within an uploading interface such as profile picture. The attacker will upload non-image based code.
- Insecure Direct Object Referencing ( #IDOR) is when the FQDN is modified to gain access to an area of the site that is otherwise restricted. An example would be if our URL ends with "/page6/" and we manually enter "/page7/" to gain access.
- Broken Access Control is an exploitation of the account creation page where an attacker is able to create an account with elevated privileges by modifying parameters.




[OWASP Web Security](https://github.com/OWASP/wstg/tree/master/document/4-Web_Application_Security_Testing "OWASP guide to web security.")
