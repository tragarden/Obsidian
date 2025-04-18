# Database Management Systems

A Database Management System (DBMS) is used to create, define, and host a database. Relational databases, NoSQL, Graph types, and Key-Value systems are common.

Methods for interacting with a DBMS include command-line interfaces, graphical user interfaces, and Application Programming Interfaces (API). DBMS are often used within the industries of banking, finance, and education.

#### Features

There are some essential features of a good DBMS, as described below:

- Concurrency - multiple users may interacted with the DBMS simultaneously without data loss or corruption.
- Consistency - data is consistent and valid throughout the entire database.
- Security - security controls like user authentications and permissions prevent unauthorized access.
- Reliability - an easy system for backing up and restoring the database.
- SQL - a language with intuitive syntax to perform operations within the database.

#### Architecture

Most databases use a two-tier database.

- Tier I handles the client-side applications and activities like login or comment posting. Once this data is submitted on the front end, it is passed on to Tier II via API calls or other methods.
- Tier II is known as middleware that interprets events and stores them in a format required by the DBMS. An application layer uses libraries and drivers to receive queries like insertion, retrieval , deletion, or updating. The DBMS will return either the requested data or relevant error codes for inoperable queries.
- 
### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to Databases](https://academy.hackthebox.com/module/33/section/178 "Intro to Databases")