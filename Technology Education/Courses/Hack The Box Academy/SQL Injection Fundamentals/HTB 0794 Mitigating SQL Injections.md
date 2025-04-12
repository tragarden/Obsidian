# Mitigating Injections

This course has demonstrated how to perform SQL injections, but it is more important to know how to defend against them and patch away vulnerabilities when they are identified.

### Sanitization

When code has not been sanitized, any submissions to the input field are sent via POST requests and passed directly to the query. This is how attackers are able to perform injections and gain access to web applications. 

Sanitizing the input renders injection inoperable. There are various libraries used to perform sanitization of user input by including functions like mysqqli_real_escape_string(). This function escapes special chracters like the apostrophe ( ' ) and quotes ( " ) so they cannot be used to exploit internal code. The pg_escape_string() function does the same thing for PostgreSQL iterations.

### Validation

Validation refers to examining user input to determine if the content submitted is what meets the expectations for input on the server. An example of this means that if the field takes user input for email information, then the server will validate that the format of the submitted email includes '\@email.com'. 

Validation employs the use of regular expressions to achieve this. You simply determine a known format for the information being submitted, and then use regex to indicate what the submitted information should look like. This is facilitated by the use of the preg_match() function, which checks user input to make sure it matches the regex pattern.

In the case of our module, \[A-Za-z\s]+ is used to indicate the form of port information.

### Privileges 

It is important to ensure that users querying the database have the minimum permissions required to perform their work. In the case of web applications, superusers and admin privileges should NEVER be used.

### Firewalls

A Web Application Firewall (WAF) is used to detect malicious input and subsequently refuse any HTTP requests that contain this type of data. This technique will prevent injection attempts even in the case of flawed logic on the back-end. There are many open-source and proprietary firewalls, like ModSecurity and Cloudflare respectively. They come with default configurations that offer a strong start to preventing common types of web based attacks. In most cases, requests containing the string INFORMATION_SCHEMA are rejected since this is almost always a vector for attack.

### Parameterized Queries

Parameterized Queries use placeholders for input data so that it can be escaped before being passed to drivers. This prevents the data from being passed directly into the SQL queries on the back-end. When the data is passed, placeholders are used before they are filled with PHP functions. Within our module, the placeholders are question marks (?) where the username and password information is typically output. The username and password submission data is bound to mysqli_stmt_bind_param() function that escapes any quotes or special characters before values are placed into the query.

### End

It should be noted that even with preventative measures in place, it is still possible to perform SQL injection by exploiting the logic of the application.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Mitigating Injection](https://academy.hackthebox.com/module/33/section/794 "HTB Mitigating Injections")