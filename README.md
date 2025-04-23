
👥 Group Details
Group No: 2024GR12CS462

Members:

Mani M Kulkarni (202211047)

Md Ganim (202211048)

Vibhansh Goel (20221097)

📋 Project Overview


This project automates the deployment of a 5G core using Docker containers and Ansible. It also covers post-deployment verification (e.g., ping tests, WebUI checks) and the implementation of IPSec for secure communication.

🛠️ Step-by-Step Setup Guide


1. Install Dependencies
Ensure your system has the required dependencies installed.

<pre>'sudo apt update'</pre>

<pre>'sudo apt install -y docker.io docker-compose python3 python3-pip ansible git'</pre>


2. Start Docker

<pre>'sudo systemctl start docker'</pre>

3.Clone the Deployment Repository

<pre>'git clone --recursive https://github.com/Free5GC/Free5GC.git
cd Free5GC
 '</pre>

4.Indentify your network interface

Determine the name of your network interface that connects to the internet. This is required for the 
playbook execution.

<pre>'ip a'</pre>

 5.Run the Ansible Playbook

 <pre>'ansible-playbook -K deploy_network.yml -e "internet_network_interface=[network_interface_name]"'</pre>


 6.Verify Deployment
 Checking containers: 
 <pre>'docker ps'</pre>

 
 Ping test:
 <pre>'docker exec -it ue bash
ping google.com'</pre>

 
check webui by opening browser and going to 
<pre>'http://localhost:3000 '</pre>


7.implementing ipsec security with deployment

<pre>'sudo .venv/bin/python ipsec_enc.py '</pre>

and it can be verfied be running :
<pre>'sudo tcpdump -i any esp '</pre>


