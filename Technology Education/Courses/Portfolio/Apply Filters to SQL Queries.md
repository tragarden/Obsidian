### Overview

This document will demonstrate experience using SQL to query databases via operators and keywords. This is based on a completed lab where queries and filtering were used to access a database and retrieve data. 

### Scenario

You are a security professional investigating security issues within an organization that involve login attempts to employee machines. You will examine the data related to employees and log_in_attempts tables using SQL filters.

### Project

The lab focused on two database tables: log_in_attempts and employees. The tables had the following column format:

log_in_attempts:

| event_id | username | login_date | login_time | country | ip_address | success |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |

employees:

| employee_id | device_id | username | department | office |
| ---- | ---- | ---- | ---- | ---- |

#### Task 1

Retrieve all failed login attempts that occurred after hours:

I knew that I would be filtering ALL data from log_in_attempts where the log_in_time was after 18:00 with a failed status indicated by the Boolean value '0'. To accomplish this I knew I would need to use the 'greater than' operator and the 'equals' operator:

>SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = 0;

#### Task 2

Retrieve all login attempts on 2022-05-08 OR 2022-05-09:

I knew that this would be querying data from log_in_attempts for either of the dates described, which indicated the use of the OR operator: 

>SELECT * FROM log_in_attempts WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';

#### Task 3

Retrieve all login attempts that occurred outside of the country Mexico:

I knew that this would be querying data from log_in_attempts for any country that is NOT Mexico. Additionally, Mexico is represented by the term 'MEX' or 'MEXICO' which means I would need to use a wildcard to represent this term:

>SELECT * FROM log_in_attempts WHERE NOT country LIKE 'MEX%';

#### Task 4

Retrieve employees in 'Marketing' that are also in an Eastern office location:

I knew that this would be querying the employees table, filtering for both the 'Marketing' department and 'East' offices which would require the AND operator. Since there are various offices located in the east building, I knew a wildcard would be used in conjunction with the LIKE operator:

>SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'East%';

#### Task 5

Retrieve employees from both the 'Finance' and 'Sales' departments:

I knew that this would be querying the employees table and using the OR  operator to indicate both the 'Finance' and 'Sales' departments:

>SELECT * FROM employees WHERE department = 'Finance' OR department = 'Sales';

#### Task 6

Retrieve all employees that are NOT in the IT department:

I knew that this would be querying the employees table for all employees that are NOT in the 'Information Technology' department via the NOT operator:

>SELECT * FROM employees WHERE NOT department = 'Information Technology';

### Summary

This exercise showed experience of using the AND, NOT, OR, LIKE, greater than, and equals to operators to perform queries while filtering two tables for data. It demonstrated common security queries for log in data such as filtering for failed log in attempts after hours, login attempts during specific dates and time periods, and log in data that is outside of a specific region. Additionally this showed how to filter employee data to get information about employees in specific departments, and employees that work in specific buildings.