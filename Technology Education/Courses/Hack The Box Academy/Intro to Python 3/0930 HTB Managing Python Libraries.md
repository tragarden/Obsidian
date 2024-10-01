# Managing Python Libraries

#pip is a way that external packages can be installed to Python. Pip stands for 'pip installs packages', which is an ironic use of the acronym in a recursive way. Pip is a module that is used to install, uninstall, and upgrade packages within Python. 

You will likely only install Python packages when you search for 'how to do something' related to Python and the package is recommended for that task. 

Flags and arguments associated with pip include:

- install
- --upgrade
- uninstall
- freeze - prints a list of currently installed packages and dependencies.

Syntax for package installation is demonstrated in the following code:

>python3 -m pip install \[package]

To install the flask package used to run Python-based web servers:

>python3 -m pip install flask

To upgrade flask:

>python3 -m pip install --upgrade flask

To uninstall flask:

>pip uninstall flask

To see what is currently installed:

>python3 -m pip freeze

Sharing your freeze list is useful when you are sharing code so that the other user knows which packages to install.

#### Requirements

pip maintains packages by referencing a requirements file by the name of requirements.txt, which contains all the required packages needed for a given script to run.

You can copy freeze output and save it as a requirements.txt file to download the correct packages and dependencies needed for a given script. 

Saving your freeze output to this file and then installing it:

>python3 -m pip install -r requirements.txt

The freeze output uses the == comparison operator to denote the exact version of a package used. If you wanted to allow for modified version that deviate from these exact versions, the following comparison operators can do this:

- <= or >= can be used to include other versions.
- < or > can be used to exclude other versions.

If you know that certain versions of packages are vulnerable to exploitation, or if newer versions are known to break the code written, you can prevent them from being installed with the comparison operators. 