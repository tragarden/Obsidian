# Information Gathering

 Information Gathering is the most important stage of penetration testing and is repeated as often as we are able to exploit, laterally move, or escalate privileges. Every time we reach a new stage of our test, we will perform information gathering again.

#### Open-Source Intelligence

Open-Source Intelligence ( #OSINT) is the process of discovering information about an organization through publicly available resources. This means investigating sites and published documents from the organization and employees. Sometimes you can find problematic repositories on GitHub. Another less common example is looking for employee posts on Stack Overflow to determine if they have posted any compromising information. There are many ways of uncovering public information and each organization will have a different set of resources to investigate.

#### Infrastructure Enumeration

Infrastructure Enumeration refers to identifying the full list of hosts, clients, servers, web applications, and network devices on the target network. This is often accomplished using #DNS to find all #IP addresses for a given network and then identifying the devices accordingly. This will help us create a map of the devices and their relationships throughout the network.

During this phase we will also identify any security features like #firewalls so that we can perform an external penetration test and then infiltrate the network undetected. This is known as Evasive Testing, where the attacker enters the network and becomes increasingly "noisier" until they are discovered by the security features. This gives the tester an idea of how these security methods can be improved.

#### Service Enumeration

During the Service Enumeration stage we will identify any services active on the hosts and servers, as well as their current versions and purpose for use. This will help us understand if the applications are regularly updated or neglected. Sometimes administrators will refrain from updating services because they fear they will stop working upon update.

#### Host Enumeration

During the Host Enumeration stage we will identify any hosts active on the network, as well as their operating systems, versions, services used, and service versions. Occasionally we can find hosts that are poorly configured because the device does not directly connect to the internet and the Administrator  doesn't think it can be accessed by outsiders.

After initial exploitation and identifying of hosts, we will further investigate the hosts to determine additional services, ports, files, scripts, applications, and other information that is now available to us. This is a part of the Post-Exploitation phase of our tests.

#### Pillaging

Pillaging occurs after we have successfully exploited a host and gained access to user accounts and new levels of privilege. This can reveal accounts names, employee names, client data, financial histories, and many other pieces of sensitive information.