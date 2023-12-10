# HTTP Requests and Responses

An #HTTP request is sent by a client and an HTTP response is sent by a server. 

The very top line of any HTTP request contains three fields: Method, Path, and Version.
- Method specifies the HTTP method being employed.
- Path indicates the route to get to the accessed resources. Sometimes the path will include a query string preceded by a question mark (?).
- Version tells you what version of HTTP is being used.

When the server responds, the top line of the response includes two important fields.
- Version, which tells you what version of HTTP is being used.
- HTTP response codes, which tell you the status of the request. 

The response headers includes more information than this which we are not covering in this module.

The body of the response will contain #HTML or #JSON code that can render the page requested.

#### DevTools

In your #browser is likely a set of applications known as #DevTools that are used by web developers and penetration testers to examine web requests.

# GET Requests

#GET requests are the default method that a #browser will use to obtain resources from a server. These requests can be examined in the #Network tab of your browser's DevTools.

# POST Requests

#POST requests are used in place of GET requests when the client is requesting a large amount of data. POST is better attuned for large file transfer because it requires less encoding and supports larger URL name. 

