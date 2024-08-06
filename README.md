# Simulate-a-basic-network-attack-and-defense-

## Objective

The objective is to simulate a network attack and learn how to defend against it. We will be using the virtual machines we set up in a earlier project wich will be linked <a href >here</a> Ubuntu as the defending vM and Kali Linux as the attacker VM

### Skills Learned

- learned how to apply filters to SQL queries.
- gained the ability join tables to get specific information from databases.
  


## Steps


Step 1:
Retrieve after hours failed login attempts.

There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![sql portfolio](https://github.com/VegaL101/computer-updates-lab/assets/166334918/d683dae1-99bd-4431-80a3-2c3ea7c36e38)

The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts.



Step 2:
Retrieve login attempts on specific dates.

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.
The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

![sql portfolio 2](https://github.com/VegaL101/computer-updates-lab/assets/166334918/c76ecf2d-ceac-4d44-8bc8-9e81c966b341)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.



Step 3:
Retrieve login attempts outside of Mexico.

Login attempts outside of Mexico also need to be looked up due to suspicious activity.

![sql portfolio 3](https://github.com/VegaL101/computer-updates-lab/assets/166334918/0249c5d3-1ebc-4e9b-86e7-e762e82732a1)

FIrst i selected all data from the log_in_attempts table. Then, I used a WHERE  with NOT to retrieve login attempts everywhere but Mexico . I used LIKE with MEX% to find anything that starts with “Mex”  since both MEX and MEXICO can appear on the dataset. 



Step 4:
Retrieve employees in Marketing.

Certain employees in the marketing department located in the east building need their systems to be updated. To do this I need to create a new query. 

![sql portfolio4](https://github.com/VegaL101/computer-updates-lab/assets/166334918/980714e7-7e94-4ac1-b61a-d12cca4a71bb)

This query returns all employees in the Marketing department in the East building. I select all data from the employees table. Then, I used a WHERE with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% since there is more than one office in the east building. I then received the data needed to find out who has yet to update their systems.



Step 5:
Retrieve employees in Finance or Sales.

systems in the Finance and Sales departments also need to be updated. The query returns employees in the Finance and Sales departments.

![portfolio5](https://github.com/VegaL101/computer-updates-lab/assets/166334918/03c97169-b1ee-4339-8444-faa31d408c97)

Again I start by selecting all data from the employees table. Then, I used a WHERE  with OR to filter for employees who are in sales and finance. With this query I can find employees in either department.
Retrieve all employees not in IT
A security update needs to be done on all employees except those in the IT department.



Step 6:
Retrieve all employees not in IT

A security update needs to be done on all employees except those in the IT department.

![sql 6](https://github.com/VegaL101/computer-updates-lab/assets/166334918/512b9716-6f59-431f-b031-8179db973824)


Similar to the query from earlier i return all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE  with NOT to filter for employees not in this department.


Summary:

I created multiple queries to help find information regarding login attempts and employee systemsI. Any data related to login attempts was to investigate suspicious activity and any data involving employee machines was to update any systems that can prove a security risk.








