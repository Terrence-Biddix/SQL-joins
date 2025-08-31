# SQL-joins

## Objective

The objective of this lab was to practice using SQL joins to combine data from multiple relational database tables. In a simulated security incident, SQL queries were used to connect employees, machines, and login attempts data to support an investigation.

### Skills Learned

Constructing and executing INNER JOIN, LEFT JOIN, and RIGHT JOIN queries

Understanding relationships between tables in a relational database

Identifying common columns used for joins

Extracting meaningful insights from joined datasets to support security investigations

### Tools Used

SQL (Structured Query Language)

Relational Database Management System (RDBMS)

### Steps
##### Task 1: Match employees to their machines

To determine which employees were using which machines, an INNER JOIN was used between the machines and employees tables on the common column device_id.

SELECT * 
FROM machines 
INNER JOIN employees ON machines.device_id = employees.device_id;


Result: The query returned 185 rows, mapping employees to their assigned machines.

*Ref 1: INNER JOIN between machines and employees* 
<img width="912" height="769" alt="SQL 1" src="https://github.com/user-attachments/assets/9e36c5f6-9bc1-405c-8101-203c130c3fb2" />
<img width="327" height="117" alt="SQL 2" src="https://github.com/user-attachments/assets/a9f042e4-4eed-4778-94dc-a671d5a473de" />


##### Task 2: Return more data with LEFT and RIGHT Joins

LEFT JOIN: Retrieved all machines and their associated employees (if assigned).

SELECT * 
FROM machines 
LEFT JOIN employees ON machines.device_id = employees.device_id;


Result: Some records showed NULL in the username field, indicating machines without assigned employees.

*Ref 2: LEFT JOIN output – machines without users highlighted*
<img width="930" height="699" alt="SQL 3" src="https://github.com/user-attachments/assets/3e5c319a-5fc7-44b4-8464-84253c087526" />
<img width="920" height="225" alt="SQL 4" src="https://github.com/user-attachments/assets/4589806e-7cb2-42f9-ab6c-42dfaee00dc5" />







RIGHT JOIN: Retrieved all employees and their assigned machines (if any).

SELECT * 
FROM machines 
RIGHT JOIN employees ON machines.device_id = employees.device_id;


Result: The last record showed username areyes, confirming employees without machines were also captured.

*Ref 3: RIGHT JOIN output – employees without machines highlighted*
<img width="922" height="779" alt="SQL 5" src="https://github.com/user-attachments/assets/0ae1bf96-49fe-46c0-8876-8f71ed86700f" />
<img width="929" height="184" alt="SQL 6" src="https://github.com/user-attachments/assets/9a736b33-ffc9-40bc-8e16-67b6fe9c6b13" />


##### Task 3: Retrieve login attempt data

To continue the incident investigation, an INNER JOIN was performed between employees and log_in_attempts using the common column username.

SELECT * 
FROM employees 
INNER JOIN log_in_attempts ON employees.username = log_in_attempts.username;


Result: The query returned 200 rows, showing all login attempts tied to employees.

*Ref 4: INNER JOIN between employees and login attempts*
<img width="930" height="789" alt="SQL 7" src="https://github.com/user-attachments/assets/dc20df30-2ec8-4c60-adde-744f9dcfcc8a" />
<img width="926" height="356" alt="SQL 8" src="https://github.com/user-attachments/assets/eb255d9b-371a-459c-900c-e07711e5541a" />



## Conclusion

This lab provided hands-on experience with SQL joins to connect and analyze related tables in a database. By applying INNER JOIN, LEFT JOIN, and RIGHT JOIN, it was possible to:

- Identify which employees were using which machines

- Detect machines without assigned users

- Detect users without assigned machines

- Gather login attempt data for all employees

This demonstrates the critical role of SQL joins in security analysis, enabling analysts to connect fragmented datasets into meaningful insights for investigations.


