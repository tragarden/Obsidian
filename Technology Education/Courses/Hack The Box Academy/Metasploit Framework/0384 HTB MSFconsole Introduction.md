# Introduction to MSFconsole

#MSFconsole is the command that we enter to start the Metasploit Framework application. This application is installed on Parrot OS and Kali Linux by default. When we start the application through the command-line ( #CLI) we can supply options and parameters like many other #Linux scripts.

For instance, if we submit the command 'msfconsole -q' - the application will open without displaying the logo banner.

If we want more information about the functionality of the application and syntax, type 'help'.

#### Update and Upgrade

It is important to ensure that we have fully updated all modules related to this application and downloaded any newly implemented ones. 

We can make sure our msfconsole application is up to date and fully installed with the following command:

>sudo apt update && sudo apt install metasploit-framework

Note that the old way to update this application - msfupdate - is less efficient and obsolete compared to the above command.

### Engagement Structure

There is a logical process for using the application as follows:

- #Enumeration
- Preparation
- Exploitation
- Privilege Escalation
- Post-Exploitation

Each of these categories are nuanced and contain subcategories that are beyond the scope of this page. It is important to learn all of these categories over time and understand their functions within the application. Here is a hierarchical tree that outlines these multifaceted groups:

![image](https://academy.hackthebox.com/storage/modules/39/S04_SS03.png)

