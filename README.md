# Simulate-a-basic-network-attack-and-defense-

## Objective

In this project, we aim to simulate a network attack and learn how to defend against such threats. Utilizing the virtual machines previously configured in my <a href="https://github.com/VegaL101/Setting-up-a-basic-home-lab">"setting up a basic home lab"</a> project, In this scenario:

The Ubuntu VM will act as the defending system, tasked with protecting against potential threats.<br>
The Kali Linux VM will serve as the attacker, simulate a network attack to test and evaluate our defensive measures.<br>
This project will not only help us understand the vulnerabilities within our network but also improve our ability to deploy effective countermeasures.



### Skills Learned

- Learned how to use tools to identify weaknesses in a network.
- Gain hands-on experience in configuring and managing security measures such as firewalls.
- Learn how to monitor network traffic for signs of suspicious or malicious activity.
- Practice ethical hacking techniques to exploit vulnerabilities in a controlled environment.  
  


## Steps


Step 1:
Install necessary tools for this projects.

In this step, we will install the necessary tools for our project. First, we install Wireshark on our Ubuntu VM. Wireshark is a widely-used open-source network protocol analyzer that enables you to capture and examine network traffic. It provides in-depth details about network packets and protocols, making it an essential tool for network troubleshooting, analysis, and security.<br>
To install Wireshark, open a terminal on your Ubuntu VM and enter the following command: sudo apt install wireshark<br>
as shown below.<br>
once installed, you can use wireshark to to monitor and analyze traffic.

![ubuntu wireshark](https://github.com/user-attachments/assets/224dfe18-d01b-4d46-b1c0-cd66132300e9)

##
  
Next, we will be installing 'Wireshark', 'Nmap', and 'Metasploit-framework' for our Kali Linux VM.<br> Nmap is a network scanning tool for discovering hosts and services on a network.<br> Metasploit-framework is a framework for developing and executing exploits against systems with vulnerabilities. widely used for penetration testing.<br> to install these tools we'll be entering the command: sudo apt install -y nmap wireshark metasploit-framework <br>
as shown below.
  
![kali wireshark and tools addition](https://github.com/user-attachments/assets/0f8ed183-d66f-429a-803d-4fb94054862d)

  ##
  Step 2:
  Simulate the attack.
  
 To simulate our attack, we first need to obtain the IP address of our Ubuntu machine. Open a terminal and type the command: 'ip a'. <br>Then look for the line that starts with 'inet' near the bottom.This line will display your ip address. In this example shown below our ip address is 'inet 10.0.2.15'. Your ip address should look similar, make sure to take a not of it as we will be using this ip address for our simulation.
  
 ![ubuntu ip](https://github.com/user-attachments/assets/590c5758-8f99-416f-9df2-895743023ec8)

##
  
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








