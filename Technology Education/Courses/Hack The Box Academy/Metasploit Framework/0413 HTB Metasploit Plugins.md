# Metasploit Plugins

Plugins are third party software that has been approved for integration by the creators of Metasploit. Some of these are paid for, but almost all plugins will have a community version that is free for use. These will expand the functionality of msfconsole and even Metasploit Pro. Plugins are commonly use to save time by automatically documenting our actions while using msfconsole and providing convenient #GUI for managing hosts, services, vulnerabilities, exploits, and payloads. The plugin integrates via the #API allowing them to manipulate the framework so you can automate tasks and add new commands to the #CLI. 

### Using Plugins

Plugins are stored within the /usr/share/metasploit-framework/plugins directory by default. 

To see what plugins are installed or if you have correctly installed them, use the following command:

>ls /usr/share/metasploit-framework/plugins

You should be able to use any plugin name from this output as a command within msfconsole to execute it and use it.

#### Loading Nessus

Running the #Nessus plugin is a simple as typing the following command:

>load nessus

If you get an error saying the plugin failed to load, make sure you have downloaded the current version correctly. Reading the help manual for each plugin is required, as all of them have their own unique set of commands.

### Installing New Plugins

To install a new plugin, go to the official page for the plugin and download the #Ruby .rb file to the /usr/share/metasploit-framework/plugins directory.

Use the following commands to install [DarkOperator's Metasploit-Plugins](https://github.com/darkoperator/Metasploit-Plugins.git 'git repo for Dark Operators metasploit plugins package')to the plugins directory:

>git clone \https://github.com/darkoperator/Metasploit-Plugins
>ls Metasploit-Plugins

We can now copy a single plugin from this repo into our active plugins directory:

>sudo cp ./Metasploit-Plugins/pentest.rb /usr/share/metasploit-framework/plugins/pentest.rb

You can now execute msfconsole and use the load command to see if the plugin was installed successfully.

### Mixins

Metasploit  is written in the #Ruby #object-oriented language which makes the application user friendly. Mixins are a class that act as methods that other classes are able to use without acting as a parent class. They are not parent classes because they operate with inclusion instead of inheritance. This makes them flexible, providing extra features for a class or one specific feature for many classes. In #Ruby, mixins are considered modules and are implemented using the include command with the name of the module as a parameter.

