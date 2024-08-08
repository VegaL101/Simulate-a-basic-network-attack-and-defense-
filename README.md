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
  
For this step we are utilizing both our Ubuntu and Kali Linux vm so make sure to have them both on during this step.<br>
To simulate our attack, we first need to obtain the IP address of our Ubuntu machine. Open a terminal and type the command: 'ip a'. <br>Then look for the line that starts with 'inet' near the bottom.This line will display your ip address. In the image shown below our ip address is 'inet 10.0.2.15'. Your ip address should look similar, make sure to take note of it as we will be using this ip address for our simulation.
  
 ![ubuntu ip](https://github.com/user-attachments/assets/590c5758-8f99-416f-9df2-895743023ec8)

 ##
  
  Next, we'll open up wireshark on Ubuntu by entering the command: 'sudo wireshark' in the terminal, once opened you should be presented with the screen below.<br>
  Click on "capture" and then "start" on the bottom right.
  
  ![ubuntu wireshark menu](https://github.com/user-attachments/assets/488576cb-b7ab-4087-9221-4f3f8cab2a7b)

  ##

 Now Wireshark is capturing network traffic. Anything captured by wireshark will be presented below. 

![ubuntu wireshark 3](https://github.com/user-attachments/assets/f1642461-cf36-45f5-b03e-834ae3a12122)

  ##

  Next, we go on our Kali Linux machine open a terminal and enter the command: 'nmap -A (ip address)'.<br> in your case you'll use the ip address from your UBuntu VM because thats your target.<br> Although in this example we'll be using 'namp -A 10.0.2.15' as shown below and press enter.

  ![nmap](https://github.com/user-attachments/assets/a2852354-fb33-41ad-9fdc-5e1687e30df0)

  If performed correctly, you should see a message saying "Host is up," indicating that your network scan successfully reached the target VM. The nmap -A command is an aggressive scan that sends  TCP packets to collect detailed information about the target system. By using nmap -A, you can gather 
  details about the target VM, including its operating system, running services, and open ports.

  ##

  Now we go back to Wireshark running on your Ubuntu VM YOU should see a bunch of tcp packets (red and grey) that wireshark has captured that you can examine. It should look similar to down below.
  
  ![tcp packets](https://github.com/user-attachments/assets/8e0cac63-5911-4f4d-9b30-3d875550841c)

  After a while the tcp packets will begin to go away as activity resumes back to normal.

  ![tcp packets going back to normal](https://github.com/user-attachments/assets/c75c1a8b-65d5-4180-9808-a9fdc7e66ca9)

  ##

  Step 3:
  Defend

  Now in this step we'll be going over how to defend against this kind of aggressive scan.<brr> On your Ubuntu VM we will be installing a UFW which stands for uncomplicated firewall that we will enable and configure.
  <br> The command needed is: 'sudo apt install ufw' to install the firewall.
  
  Next we can enable it by typing the command: 'sudo ufw enable'.<br> You should also enter the command: 'sudo ufw enable ssh' this adds a rule to the UFW 
  configuration to allow incoming traffic on the default SSH port (port 22). It ensures that SSH connections can reach your server.

  ![ufw install ubuntu](https://github.com/user-attachments/assets/f1e7941c-5aa7-4608-a367-b33b40c4d494)

  We will also enter the command: 'sudo ufw enable ssh' this enables configuration to allow incoming traffic on the default SSH port (port 22). It ensures that SSH connections can reach your server.
  <br> This will also provide security as it provides secure, encrypted communication between a client and a server.

![sudo allow ssh ubuntu](https://github.com/user-attachments/assets/d7df4231-71c2-4adf-b2f1-4158e53af6e4)

UFW (Uncomplicated Firewall) offers flexible options and can be configured as you like.

##

Now to test if an aggressive network scan from our Kali Linux VM will successfully reach the Ubuntu VM after configuring the firewall,  we will again use the 'nmap -A' command.<br>
If the firewall is configured properly, you should encounter the message 'Host seems down. If it is really up, but blocking our ping probes, try -pn' This indicates that the firewall has successfully defended the system. <br> It should look like the example below.

![nmap fail](https://github.com/user-attachments/assets/1e5987ae-ba01-4d9c-a3ce-569a6d1bafeb)

##




