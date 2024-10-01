# Importance of Python Libraries

Two popular libraries that will be covered are the requests and the BeautifulSoup libraries.

### requests

The requests library is an #HTTP library for Python that allows you to sent HTTP/1.1 requests, add query strings to URLs, or form-encode POST data.

The following command will install the requests library:

>python3 -m pip install requests

This library has a Session class that maintains context during web activity. If you wanted to track a range of cookies, you could use a Session object to do so.

Creating an object from the Session class would look like:

>sess = requests.Session()

The requests module can be used to make HTTP requests as follows:

>import requests
>
>
>resp = requests.get('\http://httpbin.org/ip')
>print(resp.content.decode())

Output:

>'origin': 'x.x.x.x'

This is how you would perform a GET request to obtain a public IP.

We used the .decode() module to convert the resp.content variable from a byte-string into UTF-8 characters. Other encodings besides UTF-8 can be indicated by including them as an argument of the .decode() module, UTF-8 is the default argument.

The resp object will contain useful information such as the status code of the HTTP GET request as well as cookies.

### BeautifulSoup

The BeautifulSoup library, alternatively known as beautifulsoup4 allows for ease of use with the #HTML language. Raw HTML data can be difficult to read through and the BS library turns this output into Python objects that are easier to work with and analyze. 

Install BeautifulSoup with the following command:

>python3 -m pip install beautifulsoup4

When HTML is returned in Python output, it is often an ugly mess:

![[Sloppy HTML.png]]

Save this output to a variable named html_doc:

>from bs4 import BeautifulSoup
>
>html_doc = """ html code here """
>soup = BeautifulSoup(html_doc, 'html.parser')
>print(soup.prettify())

This will output the reformatted HTML code in the following way:

![[Pretty HTML.png]]