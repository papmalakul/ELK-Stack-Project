# ELK-Stack-Project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/papmalakul/ELK-Stack-Project/blob/main/Diagrams/Pap%20Malakul%20Elk%20Stack%20Project.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/papmalakul/ELK-Stack-Project/blob/main/Ansible/filebeat-playbook.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting access to the network.
Load balancers protect availability of your service you are running. Also the advantage of having a jump box is that it allows admins to first connect to a secure computer before performing administrative tasks on untrusted environments.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system metrics.
Using Filebeat allows you to monitor the log files or locations that you specify. Using Metricbeat allows to monitor your servers by collecting system metrics and services running on the server.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| web-1    | Server   | 10.0.0.5   | Linux            |
| web-2    | Server   | 10.0.0.6   | Linux            |
| web-3    | Server   | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Load Balancer machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
(configured to my personal IP)

Machines within the network can only be accessed by the admins.
The machine allowed to access the ELK VM is the ansible container within the Jump-Box, and its IP was set to a dynamic public IP.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 10.0.0.5 10.0.0.6    |
|          |                     | 10.0.0.7             |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

The main advantage of automating configuration with Ansible would be that it allows you to save an abundant amount of time by running a playbook to configure all your IT needs.
The playbook implements the following tasks:
- install docker.io with apt
- install python3-pip
- install docker module with pip
- increase virtual memory
- download and launch a docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/papmalakul/ELK-Stack-Project/blob/main/Diagrams/running%20docker%20ps%20in%20ELK%20VM.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
web-1 10.0.0.5
web-2 10.0.0.6
web-3 10.0.0.7

We have installed the following Beats on these machines:
Filebeat
Metricbeat

These Beats allow us to collect the following information from each machine:
Using Filebeat allows you to monitor the log files or locations that you specify. Using Metricbeat allows to monitor your servers by collecting system metrics and services running on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-playbook.yml file to your /etc/ansible/.
- Update the /etc/ansible/hosts file to include the private IP's of the webservers:
[webservers]
xx.xx.xx.xx:xxx (add in: ansible_python_interpreter=/usr/bin/python3)

- Run the playbook, and navigate to individual web servers to check that the installation worked as expected.
- To check f the ELK server is running navigate to https://[jumpbox public ip]/app/kibana

For extra help with some simple Linux commands here are some other commands I used to get it running:
https://github.com/papmalakul/ELK-Stack-Project/blob/main/Linux/Linux%20Commands.md
