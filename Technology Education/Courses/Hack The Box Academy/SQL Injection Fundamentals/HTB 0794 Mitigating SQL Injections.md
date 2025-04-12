# Mitigating Injections

This course has demonstrated how to perform SQL injections, but it is more important to know how to defend against them and patch away vulnerabilities when they are identified.

### Sanitization

When code has not been sanitized, any submissions to the input field are sent via POST requests and passed directly to the query. This is how attackers are able to perform injections and gain access to web applications. 

Sanitizing the input renders injection inoperable. There are various libraries used to perform sanitization of user input by including functions like mysqqli_real_escape_string(). This function escapes special ch