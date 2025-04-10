# SQL Injections

SQL Injections are when a web application receives user input that is submitted as code instead of a string. This occurs if proper sanitization methods are not enforced within the data entry points of the application. Special characters are used to bypass the boundaries of user input so that the code is executed.

If we want perform an easy test to determine if a submission form is vulnerable to SQL injection, we can simply enter a single apostrophe ( ' ) into the submission field. If it returns an error, this may mean that the page is vulnerable to SQL injections.

### Types

How and where output is retrieved is how SQL Injections are identified or named.

- In-Band - when output is printed directly to the front end of the application.
	- Union Based - specifies the location of the column or field the output is printed to.
	- Error Based - PHP and SQL errors appear on the front end intentionally.
- Blind - a more complicated method that uses default logic to output character by character.
	- Boolean Based - conditional statements are used to determine if there is output.
	- Time-Based - conditional statements delay page responses using the Sleep() function.
- Out-of-Band - there is no direct way to observe output so it is directed to a remote location.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to SQL Injections](https://academy.hackthebox.com/module/33/section/193 "Intro to SQL Injections")