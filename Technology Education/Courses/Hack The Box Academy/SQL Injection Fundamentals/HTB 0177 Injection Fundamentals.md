# Introduction

Database structures are used to store and retrieve information for web applications via the backend operations, where the database interacts with the application in real time.

An SQL Injection (SQLi) is when this database structure is exploited using the SQL language to interfere or modify the backend operations. This is the most common type of injection, although HTTP, command, and code injections are possible as well.

The SQL code is injected to manipulate the logic of the web app by modifying the original query to execute something totally different. Union queries and stacked queries are common ways of achieving this. Once the input has been submitted, the output is retrieved on the web app's front end.

These attacks are utilized to gain sensitive data like login credentials or credit card information. Sometimes login can be bypassed without submitting credentials at all and attackers may even gain access to administrator accounts. Advanced attacks can even write new files to the database and create backdoors for the attacker for easier future access.

These attacks can be mitigated or prevented through strong coding practices and strong security. Input sanitization, validation, and appropriate user privileges and access control are methods for mitigation.


### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to SQL Injection](https://academy.hackthebox.com/module/33/section/177 "Intro to SQL Injection")