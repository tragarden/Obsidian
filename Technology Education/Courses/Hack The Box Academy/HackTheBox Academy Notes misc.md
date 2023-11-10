# Misc HTB Academy Notes 

These notes were taken off of my linux machine to consolidate with my main file list.

HACK THE BOX ACADEMY

LEARNING PROCESS (incomplete from the past)

A problem is an emotional state. Without emotion, it is merely a situation.
Focus and attention are not the same. Focus is the direction our thinking is looking towards, and attention
is the momentum behind this direction. Focusing is the deliberate alignment to a specific goal. If you
were looking for your keys, but also checking your watch to see how late you are, is an example where
your focus is divided and not optimized for completing the task.
‘Yet’ is a great solution to an ‘I can’t mentality. When you find yourself saying ‘I can’t do that’ – the
whole situation changes when you say ‘I can’t do that YET’. This is stimulating to our personal beliefs
that we CAN actually do something.
Talent is a highly developed skill that we can utilized with a high level of efficiency.
Skill is the ability to solve or manage something well.
Passion is an emotional commitment to something of our choice.
Most people only feel verbally attacked by someone we attribute a high value to. They are much more
offended If someone they love calls them stupid than if a stranger on the street were to do so. I AM THE
OPPOSITE THOUGH AND FEEL EQUALLY UPSET AT THE STRANGER.
Asking the right question is much more useful than seeking the right answer. Asking complete and
focused questions brings us closer to an answer than just seeking a solution.
1. How long will I need to spend doing cybersecurity related studies in order to quit my job and
make money from home.
2. How long do I want to continue working with plants as my primary income?
3. Why do I resist physical activity?
A question is a sentence worded to elicit information.
Apply the Remote-Oriented-Questioning Model (ROQ) to the questions you asked.
Frustration is a reaction to powerlessness or disappointment. Training away the emotional responses to
frustration is difficult but possible.

LINUX FUNDAMENTALS (incomplete from the past)

whoami Displays current username.
id Returns users identity
hostname Sets or prints the name of current host system.
uname Prints basic information about the operating system name and system hardware.
pwd Returns working directory name.
ifconfig The ifconfig utility is used to assign or to view an address to a network interface and/or

configure network interface parameters.

ip Ip is a utility to show or manipulate routing, network devices, interfaces and tunnels.

netstat Shows network status.
ss Another utility to investigate sockets.
ps Shows process status.
who Displays who is logged in.
env Prints environment or sets and executes command.
lsblk Lists block devices.
lsusb Lists USB devices
lsof Lists opened files.
lspci

Ls -la WILL LIST HIDDEN FILES THAT ARE PREPENDED BY DOTS ( . )

DAEMONS are background services that run to manage startup processes without requiring user
interaction. They are indicated by affixing a d to the end of the service, such as sshd or systemd.
Systemd is an init process and has the process ID (PID) of 1. This daemon monitors the start and end to
other services. All of these processes have a PID that can be viewed under /proc/. Alternatively to
systemd, we can use update-rc.d to manage SysV init script links.

WEB SERVICES
Web Servers are a vital function of web services. IIS, Nginx, and Apache are common webservers.
Apache can encrypt communication between the browser and web server, act as a proxy server, and
manipulate HTTP header data. Using Apache, you can create dynamic and interactive web pages using a
variety of scripting languages, including PHP, Perl, Ruby, Python, JavaScript, Lua, and .NET among
others.
CURL facilitates the transfer of files over HTTP, HTTPS, FTP, SFTP, FTPS, or SCP. It is commonly used
to test a remote system.
WGET is an alternative tool to cURL.

BACKUP AND RESTORATION
Common tools for backing up datat include Rsync, Deja Dup, and Duplicity.
Rsync is open-source and is useful when backing up files remotely, especially if they are large. Rsync can
also be used in conjunction with Cron Tabs to schedule backups. You can also encrypt your data as it is
being transferred.
Duplicity can be used to handle front end backup, while using Rsync for recording the backend.
Deja Dup is a user friendly backup service that is user friendly, also working jointly with Rsync.
Unix specific backup tools include GnuPG, eCryptfs, and LUKS.

An important feature of linux is Swapping. A space is partitioned off for any files that may be swapped in
the future. When the available drive space has run out on our system, then linux starts to move inactive
data to the swap space freeing up physical memory for active processes. Partitions for swap can be
created during install of the OS or after. It is recommended to make this partition encrypted, since you
aren’t totally sure what data will end up here. Swap space can also be used for hibernating your machine,
where the swap partition remembers the active state of your computer at the time it was hibernated.

CONTAINERS are used to isolate development from the host environment. Using containers is a light-
weight tool that allows devs to create, deploy, and manage applications efficiently. They can be used to

run multiple applications simultaneously and securely. Docker and AWS are examples of these tools.
Docker is an open source tool. Its containers are designed to be immutable, meaning that any changes
you make while accessing the container are not saved. This allows for a sandbox environment where you
can try different versions of your app and implement experimental features that might crash or destroy
your original work.
Linux Containers (LXC) is an alternative to Docker, however it can be used in conjunction with docker
for a fully-fledged containerization. There are differences in the approach, image building, portability,
security, and ease-of-use between the two applications. In LXC, you create a new root file-system on
your machine and install the required packages and configurations. Because this data is tied to your own
file-system, this limits the portability of the containers and makes them more difficult to configure and
manage.
Containers are useful for simulating a network so you can actively pentest on the network without
damaging anything. For example, say you wanted to test whether you can uninstall the system files to run
SSH. If you did this – you would immediately disconnect from the machine you are testing when you
uninstall SSH. In the container environment, you could do this without the threat of actually deleting
SSH off of your real machine.
Lxc.cgroup.cpu.shares parameter is used to allocate CPU time to the container. The default time is 1024,
meaning the container has full use of the CPU, which is a useful way to manage resources like CPU and
RAM. If we set the time allocation to 512, this would allow access to half of the CPU.
Lxc.cgroup.memory.limit_in_bytes parameter is used to allocate the amount of physical memory a
container can use.
PAUSED FOR NOW

WEB REQUESTS
A web request is what your browser sends to a server – it is a list of what information we want to receive
from the server. After the server interprets this information, it processes a response with the relevant
information and sends this request back to the client.
General headers are contextual and include things like date, time, and connection information. The
connection header will tell you whether the client-server connection should be terminated (close) or
maintained (keep-alive).
Entity Headers are included in both requests and responses. They describe the content that is included in
the request or response. These headers are typically found in the POST and PUT requests.
Request headers are sent by the client. They do not involve the content of the submitted message. It
relays information such as Host, User-Agent (client), Referer (location of the link you clicked), Accept

(lists what media types can be submitted), Cookie, and Authorization (identifies clients), in addition to
many more.
Response headers do not relate to their content, and usually give context to the response. Server contains
information about the HTTP server that processed the request. Set-Cookie header defines the cookies that
identify the client/user. WWW-Authenticate tells the client what type of authentication will be used to
access the server.
Security headers specify rules and policies that your browser must follow while you are accessing the
site. This includes information about the security policy, Strict-Transport-Security that enforces the use of
HTTPS over HTTP, and a Referrer Policy that defines whether to include Referrer information in a server
response. The referrer policy and STS can be useful to prevent sniffing of web traffic.

HTTP METHODS AND CODES
GET requests a resources from the server.
POST sends binary data to the server, which is included at the end of the header-list.
HEAD returns the headers that would be returned after a submitted GET request.
PUT creates a new resource, and this can be exploited via uploading resources with malicious intent.
DELETE removes a resource from the server, and can be exploited to perform Denial of Service attacks
by deleting important files from the server.
OPTIONS returns server info.
PATCH applies modifications to the specific resource.
PLUS many more methods.
Response codes, such as 200 OK or 302 Found, are returned in the server response to the client. These
are indicated by a 3 digit indicator number.
1xx only indicates information.
2xx is returned if a request succeeds.
3xx is returned when the client is redirected by the server.
4xx indicates client requests information that is not actually on the server.
5xx is returned when there are server problems.
GET
GET can be exploited by modifying the URL, and can even be used to log credentials in multiple ways.
Using DevTools, we can examine our requests and using the copy command, we can actually get curl
commands copied straight from DevTools to be used in our terminal. I used curl to request information
from the API search to find a flag within the database.
POST
POST requests are preferred over GET for a few reasons. With POST, there is no logging as POST
requests typically contain a lot of data and recording all submissions would not be efficient. These
requests also do not require as much encoding as a GET request. Because GET is sent via URL, this
information must be encoded for the server to process the request. POST requests can be sent within the
body of the submission and do not need to be encoded. Lastly, URLs must be less than 2,000 characters,
so with POST, we can include more than 2,000 characters in the body of the submission.