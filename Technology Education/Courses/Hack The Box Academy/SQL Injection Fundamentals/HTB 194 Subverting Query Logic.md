# Query Logic Exploitation

The original queries that we will submit need to be modified via injection using the OR operator. The example for this module will be bypass the authentication measures used by the web application.

When credentials are recieved by the example application, the AND operator is used to select records that match the submitted credentials. If MySQL returns true, PHP code will evaluate the condition to be TRUE for the login credentials, thus validating the login. In this case the application will return FALSE for incorrect credentials.

### Testing

Certain payloads can be submitted into a login form is vulnerable to injections. The following payloads can be used to test this:

- An apostrophe ( ' ) with the URL Encoding %27
- A quotation mark ( " ) with URL Encoding %22
- A hashtag ( # ) with URL Encoding %23
- A semi-colon ( ; ) with URL Encoding %3B
- A closing parenthesis ( ) ) with URL Encoding %29

#### OR Injection

The OR operator can be used to ensure that the login query always returns as TRUE no matter what credentials are entered. If we consider operation precedence, we know that the AND operator is evaluated before the OR operator. However, if there is an OR operator after the AND operator, it will check for the validity of the AND operator AS WELL AS whatever is on the other side of the OR operator. This can be used to negate the AND operator by including the OR operator followed by a condition that will evaluate to TRUE.

Consider the following injection text:

>admin' or '1'='1

This is the snippet that will be injected into the following statement:

>SELECT \* FROM logins WHERE username='' AND password='something';

The injection will be placed within the single quotes following username to produce the following malicious code:

>SELECT \* FROM logins WHERE username='admin' or '1'='1' AND password='something';

