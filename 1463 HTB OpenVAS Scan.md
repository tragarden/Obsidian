# OpenVAS Scan

We will be interacting with the #OpenVAS Security Assistant from Greenbone. This tool has many features, we are concerned with the Scans tab where we can create new tasks and configure them.

Note that these scans can take as long as two hours to complete: the module has provided the scan results so we do not have to perform them ourselves.

We will access the following targets:

- #Windows: 172.16.16.100
- #Linux: 172.16.16.160

### Configuration

Navigate to the Configurations tab, then to the sub-tab Targets. In the top left of the interface, there is a "New File"-like icon that will allow you to add a new target or host list. Within this menu you can further configure ports, authentication credentials, and host identification. For default settings for Alive Test, NVT Ping Host and NVT Family are the default selections.

#### Authenticated Scans

Authenticated scans use admin credentials to further scan the network. Our credentials for these exercises are:

###### Windows

>u: administrator
>p: Academy_VA_adm1!

###### Linux

>u: student_adm
>p: HTB_\@cademy_student! 

After applying these credentials you will see the list of targets populated with the new targets. 