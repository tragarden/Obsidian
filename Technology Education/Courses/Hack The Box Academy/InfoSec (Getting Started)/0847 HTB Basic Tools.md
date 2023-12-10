# Basic Tools

### SSH

Secure Shell ( #SSH ) is a #network #protocol used to remotely and securely access machines within a network allowing the client to access resources on different hosts. It uses #port forwarding and proxying across port 22. It can use password authentication or public-key authentication depending on how it is configured. It can additionally be used to map local ports on a remote machine to the local host.

The following command initiates an SSH connection:

> ssh trag@69.69.69.69

You will then be prompted to submit the appropriate password before connection is established.

### Netcat

#Netcat ( #ncat / #nc) is a network utility that offers a variety of functions related to TCP/UDP ports. It can be used to listen to ports and interact with relevant services as well as connect via SSH. It operates on port 22 along with SSH.

To connect to TCP port 22 with netcat, use the following command:

> netcat 69.69.69.69 22

This command will return what is known as a #banner, which is depicted below:

> SSH-2.0-OpenSSH_8.4p1 Debian-3

This process is known as Banner Grabbing, which identifies any services running on a port.

We can download netcat even if using #Windows, #PowerCat is an alternative version designed for use with #PowerShell. 

#Socat is another alternative that offers functionality beyond the offerings of netcat.

### Tmux

Terminal Multiplexers ( #tmux / #Screen ) enables multiple windows to run within one iteration of the terminal.

To install tmux:

> sudo apt install tmux -y

Once tmux is installed type the following or press Ctrl + B then press C to open a new window.

> tmux

Shift + % is used to split the windows vertically.

Shift + " is used to split the windows horizontally.

Arrow keys are used to toggle between existing windows respective of their horizontal or vertical divisions. 

### Vim

#Vim is a text editor used for editing .txt files on #Linux #OS. This is often used as a code editor as it offers full control of the application without use of a mouse and is commonly used to manage remote machines.

The following command would open a new (or existing) file with Vim:

> vim /etc/hosts

When the file is opened we will be in Normal mode by default, which is used to read the file but not modify it.

To modify a file, we press the ' i ' key to enter Insert mode - indicated by the presence of "-- INSERT --" at the bottom of the file in question.

The Esc key will exit insert mode and revert to Normal mode.

Notable key presses:

- ' i ' enables Insert mode.
- ' Esc ' disables Insert mode.
- ' : ' enables command mode.
- ' x ' is used to cut a character.
- ' dw ' is used to cut a word.
- ' dd ' is used to cut a line.
- ' yw ' is used to copy a word.
- ' yy ' is used to copy a line.
- ' p ' is used to paste.

Command key presses:

- ' :1 ' goes to the first line.
- ' :w ' writes the file to save.
- ' :q ' quits the application.
- ' q! ' is used to quit without saving.
- ' :wq ' is used to write / save and quit.

These commands can be modified with numerical input. For example, the input ' 4yw ' would copy 4 words instead of one.

If we press colon ' : ' we are able to enter command mode, which enables us to enter commands which will appear at the bottom of the open Vim window.

[Vim Cheat Sheet](https://vimsheet.com/ 'Useful list of Vim commands')