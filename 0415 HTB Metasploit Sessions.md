# Metasploit Sessions

MSFconsole can utilize multiple modules concomitantly through the use of sessions. Multiple sessions can run at the same time, allowing you to toggle between them while each session allows the active module to persist in operation in the background. We can even link these background modules to our current working module. These modules will persist in the sessions until they encounter an error and the connection closes.

### Using Sessions

As long as a connection is maintained with the target host, sessions can continue running in the background. To place a session into the background environment, press Ctrl + Z or type the command 'background' while using Meterpreter. You will be prompted to confirm this decision and returned to the msf6> interface to begin running a new module.

#### Listing Active Sessions

Type the 'sessions' command to see the list of actively running sessions:

>sessions

This will provide and indexed list of the active sessions, you can select one with the -i switch and the index number:

>sessions -i 1

This will allow us to run multiple modules on a single instance of a reverse shell. 

Once we have established connection through a module, it can be backgrounded. We can then choose a new module to run by selecting a new session number for the module. This new module may have added functionality from the backgrounded sessions, which will be included in the output of the 'show options' command menu. These modules will often be associated with the 'post' category in reference to Post-Exploitation. These are typically credential gatherers, local exploit suggesters, and internal network scanners.

### Jobs

If we need to access a port that is currently being accessed by a backgrounded module in a session, we will be unable to do so unless that session is terminated. The 'jobs' command looks at the currently running modules in the background and terminate anything that is getting in the way of our newly initiated module. Tasks can be converted into jobs and run in the background even in the case that they are terminated.

Use the -h switch to view more information related to the jobs command:

>jobs -h

