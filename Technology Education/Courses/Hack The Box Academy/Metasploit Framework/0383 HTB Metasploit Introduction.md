# Metasploit Introduction

#Metasploit is a set of penetration testing tools for enumerating networks, assessing vulnerabilities, executing code for exploitation, all while evading defense systems. Metasploit is based on the #Ruby language and has many features that make testing easier. Metasploit Framework is the free and open-source ( #FOSS) iteration of the Metasploit platform.

### Metasploit Pro

Metasploit Pro is the paid commercial version of the platform and comes with features that Metasploit Framework does not provide. 

The tools available with the pro version include:

- Task Chains
- Social Engineering
- Vulnerability Validations
- GUI
- Quick Start Wizard
- Integration with Nexpose
- Unique Command Line Interface ( #CLI)

### Metasploit Framework Console

The Metasploit Framework Console ( #MSF) or #msfconsole allows you to access nearly every aspect of MSF. This console turns your computer into a capable machine for attacking and includes tools like scanners, toolkits for social engineering, and payload generators. It can maintain multiple concurrent jobs and can be used to exploit a range of vulnerabilities. It is designed to be a user friendly and intuitive way of managing exploitations.

#### Architecture

In the Pwnbox supplied by HTB Academy, the Metasploit Framework is located within the /usr/share/metasploit-framework directory by default on Parrot OS.

##### Data, Documentation, and Lib

The Data, Documentation, and Lib files are the base set of data for the Framework. The Data and Lib files allow the msfconsole interface to function, and the Documentation folder contains technical information related to the application.

##### Modules

The Modules folder contains all of the tools and modules provided by msfconsole. This is located at /usr/share/metasploit-framework/modules and contains the following folders:

- auxiliary
- encoders
- evasion
- exploits
- nops
- payloads
- post

##### Plugins

Plugins serve as an extension of the base msfconsole application and can help a user add functionality that addresses aspects beyond the base functions of the application. This allows users to customize and create new tools for their specific set of needs while keeping the original application lightweight. These plugins are often used to enable automation of the application. Plugins are located within the /usr/share/metasploit-framework/plugins/ directory. 

##### Scripts

Scripts are located within /usr/share/metasploit-framework/scripts/ directory and contains #Meterpreter. 

##### Tools

Tools are utilities for the command-line ( #CLI) that can be called from msfconsole and are stored within the /usr/share/metasploit-framework/tools/ directory.

