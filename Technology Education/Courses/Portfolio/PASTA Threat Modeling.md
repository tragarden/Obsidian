### Overview

I will demonstrate the PASTA framework as applied to threat modeling to determine if a new shopping application is ready for launch. This will be performed to identify vulnerabilities and assess risk before this application is available to threat actors.

### Scenario

I work for a retailer that accommodates sneaker heads and collectors of shoes that is about to launch a mobile app for buying and selling expensive and rare shoes. I will generate a threat model using the seven stages of the PASTA framework to identify necessary security requirements.

### Project

##### Stage 1: Identify

This is a sneaker oriented app for transacting sales of shoes that offers excellent user experience. PCI-DSS regulatory data must be secured to remain compliant and maintain trust with customers. This app will have a messaging and rating system between users. The whole process of creating accounts, browsing products, communicating with and rating other users, and paying with a variety of methods must be easy and memorable. This will require heavy back-end processing.

##### Stage 2: Define Scope

The Application Programming Interface (API) should be prioritized and third party technology should be considered. This is because there are MANY facets of this application that interact with each other and a goal of the business is to create a seamless user experience from beginning to end. 

PKI should follow because this will secure the sensitive data within the application and ensure that we remain compliant with PCI-DSS regulations. 

Securing SQL with sanitization techniques and Prepared Statements will ensure that our vast database is secure and free from injection attacks seeking sensitive client data. 

SHA256 hashing will further protect data on the site.

##### Stage 3: Decompose Application

The basic format for transactions is the user will search products and these searches will query our database. The database will then return listing to the web interface that the user will interact with. These methods should be secured with SQL sanitization and prepared statements, which hsould be paired with SHA256 hashing of data.

##### Stage 4: Threat Analysis

Possible threats include SQL injection attacks and credential theft. 

Since our database is providing resources and data to all aspects of our application, it is most susceptible to these attacks due to the interactive nature of our app. 

Credential theft is possible due to the many user accounts needed for buying, selling, and browsing the site. 

##### Stage 5: Vulnerability Analysis

If there are flaws with our input fields for reviews, logins, comments, or messages, this could be exploited via SQL injection attacks. Flaws in our sanitization methods or prepared statement methods could result in compromise of our database.

If we do not have secure password policies, brute force methods could be used to access user credentials which would reduce trust in our application.

##### Stage 6: Risk Analysis

Suggested Security Controls for mitigating threats would include:

- Password Policies that prevent credentials from being cracked and exfiltrated.
- SQL sanitization and prepared statements for input fields to prevent SQL injection attacks.
- Multi-factor authentication in combination with OAuth style credential submission.
- Application wide encryption like SHA256 and PKI to ensure PCI-DSS data is safe keeping the company within regulatory compliance.