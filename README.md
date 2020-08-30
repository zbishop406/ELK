# ELK
Penn Cyber ELK Stack Project

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the `elk_config.yml` file may be used to install only certain pieces of it, such as Filebeat.

  - https://github.com/zbishop406/ELK/blob/master/elk_config.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient and responsive, in addition to restricting DoS attacks to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs, files and system metrics.

The configuration details of each machine may be found below.

| Name    | Function             | IP Address | Operating System |
|---------|----------------------|------------|------------------|
| JumpBox | Gateway              | 10.0.0.4   | Ubuntu 18.04.4   |
| Web1    | Web Server           | 10.0.0.7   | Ubuntu 18.04.4   |
| Web2    | Web Server           | 10.0.0.8   | Ubuntu 18.04.4   |
| Web3    | Web Server           | 10.0.0.9   | Ubuntu 18.04.4   |
| ELK     | Gateway to ELK Stack | 10.1.0.4   | Ubuntu 18.04.4   |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows IT administrators to automate the majority of the install, update, and edit tasks related to the ELK machine setup and maintenance.

The playbook implements the following tasks:
- Increase Virtual Memory
- Install Docker
- Install pip3
- Install Docker Python Module
- Download and launch docker ELK container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps.png` with the name of your screenshot image file.  


![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines: 10.0.0.7, 10.0.0.8, 10.0.0.9.

We have installed the following Beats on these machines: Filebeat & Metricbeat.

These Beats allow us to collect the following information from each machine:
- Filebeat collects and displays data related to logs and files. For example, Filebeat will display syslog and SQL queries.  Metricbeat collects and displays data related to the systems and services. For example, Metricbeat will display CPU and disk usage.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the /etc/ansible/files/filebeat-config.yml file to /etc/filebeat/filebeat.yml.
- Update the /etc/filebeat/filebeat.yml file to include...the IP address of the ELK VM (40.113.204.95).
- Run the playbook using the ansible-playbook filebeat.yml command, and navigate to http://40.113.204.95:5601/app/kibana to check that the installation worked as expected.
