# Dawit_Repo
Here is my repository for my cybersecurity works
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Elk Project(Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YML file may be used to install only certain pieces of it, such as Filebeat.

  - _Filebeat playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly balanced, in addition to restricting heavy load and attack to the network.
- _TODO: What aspect of security do load balancers protect? Load Balancing plays an important security role as computing moves evermore to the cloud. The off-loading function of a load balancer defends an organization against distributed denial-of-service (DDoS) attacks.
What is the advantage of a jump box?It is used as a gateway for traffic coming from HTTP and provide connection to Web servers.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the other servers and system networks.
- _TODO: What does Filebeat watch for? It is installed as an agent on your servers, Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.- 
_TODO: What does Metricbeat record? It helps you monitor your servers by collecting metrics from the system and services running on the server, such as: Apache. HAProxy.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.4   | Linux            |
| Web1     |          | 10.1.0.5   |                  |
| Web2     |          | 10.1.0.6   |                  |
| Web3     |          | 10.1.0.7   |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _47.35.129.50

Machines within the network can only be accessed by Jump box
- _TODO: Which machine did you allow to access your ELK VM? Jump box What was its IP address?10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |      No             |    47.35.129.50
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _ What is the main advantage of automating configuration with Ansible? It can do things quickly and will be free from human error

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Gathering facts
- Download filebeat deb
- Install filebeat deb
- Drop in filebeat.yml
- enable and configure  system module
- Setup filebeat
- Start filebeat services
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
  10.1.0.4
  10.1.0.5
  10.1.0.6
  10.1.0.7
  10.2.0.4

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ filebeat-7.4.0-amd64.deb

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Filebeat configuration file to  your WebVM's.
- Update the configuration file to include user name, password, and the host ip
- Run the playbook, and navigate toFilebeat installation page on the ELK server GUI to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? filebeat Playbook.yml, at /etc/ansible
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_Filebeat.configuration.yml
- _Which URL do you navigate to in order to check that the ELK server is running? http://[10.2.0.4:5601/app/kibana

