# HyperText Transfer Protocol

#HyperText is any text that is linked to a web address where the user can click the text to access the address.

HyperText Transfer Protocol ( #HTTP ) facilitates communication between a client and a server. Clients make requests that are sent over the internet to a server, which will hopefully respond with the requested data. HTTP is a protocol at the application-level. The application level is an abstracted level that facilitates all the protocols and interfaces needed to communicate. The #port used by HTTP is port 80 by default,, although this can be changed.

Fully Qualified Domain Names ( #FQDN) is the full name for a host which is composed of both the hostname and domain name. A Uniform Resource Locator ( #URL) with the FQDN is submitted to access a desired website or resource. 

Uniform Resource Locator ( #URL) is the interface used to access website resources. It is composed of 7 key parts:

1. #Scheme identifies which protocol the client is using and is punctuated with ://.
2. User Info is optional and supplies credentials in the form of username and password separated by a colon.
3. #Host indicates the location of a resource which is either a hostname or and IP address.
4. A #Port number is included, usually port 80 unless default configuration has changed.
5. #Path points to the desired resource files or folders.
6. Query String begins with a question mark (?) and contains parameters separated by ampersands (&) and a Boolean value.
7. Fragments indicate sections within the resource that the client side browser interprets.

### Flow of HTTP

When we submit a FQDN or other information to our URL bar, it passes on to a Domain Name Service ( #DNS) server that converts the url submission into IP addresses that direct the client to the intended resource. Previously queries sites are stored locally on the client.

After receiving a reply from a DNS server, a #GET request is sent to the HTTP port 80 to receive the root path ( / ). The server then reads the index.html files sent over and responds with a status code that indicates if the HTTP request was successfully answered, or if an error occured.

### cURL

Client URL ( #cURL) is a command line tool that allows you to run scripts and automation for web requests over HTTP.  cURL will return data from the site it is paired with, which may be raw HTML data that is not rendered in the browser. The ( -O ) flag can be used to download this text data when cURL returns it. 

# HTTP Secure

HyperText Transfer Protocol Secure ( #HTTPS) is the secured version of HTTP, encrypting all transmitted data instead of the plaintext transfers that HTTP does. If you try to force an HTTPS based site to use HTTP on port 80, the server will yield the error code "301 Moved Permanently" and move communications to port 443.

In the case of HTTPS, the client will deliver a "client hello" package and the server will respond with a "server hello" and a subsequent key exchange