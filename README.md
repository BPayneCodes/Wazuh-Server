# Wazuh Server

## Introduction
This home lab will incorporate Wazuh as the EDR inspecting packets that are deployed on agents

<img width="1040" height="336" alt="image" src="https://github.com/user-attachments/assets/1ae6cc24-d7a8-48f6-ad39-50e27418857b" />



### Objective

The Wazuh EDR Project aimed to be a central hub for different machines being managed by a single entity. Wazuh will continuously collect and analyze data from endpoints, including system logs, file changes, and network activity. This comprehensive monitoring provides real-time visibility into the security posture of each endpoint. This is to simulate managing different machines while being under a single API configuration on the host machine.

### Skills Learned

- Security event correlation
- Endpoint Detection and Response (EDR)
- Intrusion detection and monitoring
- Vulnerability detection and assessment
- File integrity monitoring (FIM)
- Security compliance monitoring
- Malware detection techniques
- MITRE ATT&CK framework mapping
- Linux system administration
- Rule creation and tuning
- Real-time monitoring and alert management

### Tools Used

- Wazuh EDR Installed on host machine that will be the monitor for seperate deployed agent machines
- Kali Linux (Attacking machine)
- Ubuntu (Wazuh Server)
- Windows (Victim machine)

## Getting Started

First thing that would've saved me a ton of time is verifying your VM's have been installed with dependencies and headers prior to agent deployment

<img width="355" height="41" alt="image" src="https://github.com/user-attachments/assets/cee62d01-f481-4cbf-9a7c-dda0a6aab3a5" /> <br> <br>
<img width="257" height="21" alt="image" src="https://github.com/user-attachments/assets/6ecd212f-c703-4355-9c57-498c9c41322f" />
<br>
<p>The Wazuh agent <i>CANNOT</i> be deployed if these dependencies haven't been installed on any one machine</p>

### Installing Wazuh on Host

The next step would be to install Wazuh on the machine that will play as the monitor that will inspect the different agents that will be deployed on the network. 

<br><img width="868" height="67" alt="image" src="https://github.com/user-attachments/assets/6d1078e4-5341-4cc1-aa6e-a46b03c2d9f4" /><br><br>
If the correct dependencies has been installed, a username and password will be provided to login to the Wazuh host server.


### Deploying Agents

This is a pretty simple part that Wazuh provides step-by-step instrustions to deploy an agent. On your machines that are going to be monitored, input the following commands to install the Wazuh management system.
<br><br><img width="915" height="140" alt="image" src="https://github.com/user-attachments/assets/46ff8024-b764-4dae-9c38-1ab936bf848d" />
<br><br>
Once the packages have finished installing you need to start the agent and management system to pair with your host machine 
<br><br><img width="1060" height="120" alt="image" src="https://github.com/user-attachments/assets/f5abb30c-44e2-403d-acd2-4c112eedce1b" />



### Accessing Wazuh Dashboard

Open firefox and input the IP of the host machine with the command (ip a). Next, you will be prompted to enter the username and password that was just provided to you in the terminal

<img width="1851" height="942" alt="EDR_dashboard" src="https://github.com/user-attachments/assets/c992f753-84e2-47a0-87a4-3aa54e79285a" />


### Create Nmap Rule
You can generate a nmap rule from chatgpt to give out a template(You need to make sure to map the if_sid code to match local wazuh rule creation number)

<img width="1793" height="817" alt="nmap_rule" src="https://github.com/user-attachments/assets/17035d71-4a8f-4f54-b807-27fefd3018a3" />

## Start the Attack
1. Use the command nmap -A 10.0.2.15 (Victim agent)
2. Sysmon picks up/configures a log to send to Wazuh


<img width="853" height="120" alt="image" src="https://github.com/user-attachments/assets/7687f154-d9c4-47f0-8ed6-85e70a620d27" />






