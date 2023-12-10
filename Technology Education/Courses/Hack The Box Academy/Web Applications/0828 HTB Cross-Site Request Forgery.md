# CSRF

Cross-Site Scripting Forgery ( #CSRF) use XSS to perform queries and API calls to access the information for an authenticated user. This is commonly done with a JavaScript payload that executes immediately to change the user's password when they submit it, granting control of the account to the attacker.

Sanitation is when special characters are filtered out and removed from user input.

Validation is when formatting is applied to user input, and the format of the submission must match the accepted formats for submission.

A Web Application Firewall  ( #WAF) can be used in addition to sanitation and validation to prevent XSS style attacks. The WAF is not foolproof however and can still be bypassed.

You browser may have features built-in that prevent JavaScript from executing automatically once a page is loaded. There are also HTTP headers and flags that prevent XSS from being executed.