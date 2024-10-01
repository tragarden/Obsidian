# Managing Python Libraries

Libraries are stored in different directories and have different file paths in Windows and Linux.

Windows:
>C:\\Program Files\\Python38\\Lib\\site-packages

Linux:
>/usr/lib/python3/dis-packages

A package is a folder that contains an \_\_init\_\_.py file inside, and likely has other python files and nested folder structures within.

If you have a written script that acts as an API, you can package this with an \_\_init\_\_.py file and place the package inside the site-packages directory.

We can change the directory that python searches by default by modifying the PYTHONPATH environment variable.

For example, we could set the PYTHONPATH environment variable to /tmp/ with the following command:

>PYTHONPATH=/tmp/ python3

This would allow all packages within /tmp/ to be imported into our projects or IDLE.

If we change the default environment variable, we can direct packages we install via pip to the correct directory with a command like the following:

>python3 -m pip install --target /var/www/packages/ requests

### Virtual Environments

We can isolate a project in a virtual environment, otherwise known as a venv.  This will have it's own copy of the python binary and files for configuring the shell in the new environment.

To create a virtual environment called 'academy', use the following command:

>python3 -m venv academy

To install packages to this newly created virtual environment, use the following command:

>source academy/bin/activate
>pip install requests

You will notice that when you change the source, the terminal address path will change to indicate that you are operating within the virtual environment.

In the case of penetration testing, it is advised to use virtual environments to separate work projects from the main environment. 

