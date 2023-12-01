# HTTP Headers

### General

A General #Header is used to describe the message instead of the content within. General headers are associated with both requests and responses. Common information in these headers include date and time, as well as when to close the connection.

### Entity

#Entity Headers describe the content of a message and are included in both response and request headers. Entity headers include the content-type, media-type, content-length, encoding-type, and boundaries that determine where header fields begin and end. 

### Request

A Request header is included within any HTTP request the client sends out. This header is used to transact the HTTP transmission and does not relate to the content within. These headers will identify the #host, the User-Agent, referrer, authorization method, cookies policies, and Accept information. 

- The Accept portion described the types of media the client can interpret.
- The authorization method will define what happens with tokens. 
- The referrer tells us where the request came from.
- The User-Agent is the client who made the request.

### Response

A Response header is the counterpart to Request headers and does not relate to the content within. This header may include items like age, server, location, Set-Cookie policies, and Authenticating the WWW data. 

### Security

Security Headers define policies and rules that the browser must follow in order to gain and maintain access to the designated resource. There are three important parts of these types of headers:

- Content-Security-Policy defines rules about injecting resources into the data stream. This was implemented to defend against Cross-Site Scripting ( #XSS) attacks.

- Strict-Transport-Security enforces the HTTPS policies and does not allow for HTTP transmissions.

- Referrer-Policy determines whether a server returns data about who the referral source is.

