# Complete Provisioning with Ansible Project

## Overview
This project is a continuation of the "Ansible for Eight Years" project, extending the automation to complete provisioning of the V profile application stack on a cloud platform. The aim is to automate the lift and shift process, where a set of EC2 instances is provisioned, and the V profile stack, including services like MySQL, Memcache, RabbitMQ, Tomcat, and Engine X, is automatically set up using Ansible. This project combines the expertise gained from two previous projects, emphasizing the need for automation in managing complex infrastructures efficiently.

## Problem Statement
Operations teams, also known as sys admin or systems engineer teams, face challenges in manually setting up and managing infrastructure. The need for agility, coupled with frequent requests for provisioning and changes, makes manual processes time-consuming, error-prone, and difficult to track. Managing different services, networks, security, and ensuring high availability in a complex stack adds to the complexity. Automation is essential to eliminate human errors, centralize changes, and make the infrastructure provisioning process more agile and repeatable.

## Solution
The project proposes the use of Ansible for configuration management to automate the entire infrastructure setup. By adopting automation, teams can achieve centralized, repeatable, and reusable infrastructure provisioning. Infrastructure as code (IaC) principles are leveraged, allowing version control and easier management of changes. The business value of automation is highlighted, emphasizing revenue growth, reduced operations costs, and increased innovation.

## Business Value of Automation
- **Revenue Growth:** Over 70% of IT companies report a 10% or more increase in revenue through automation.
- **Operations Cost Reduction:** 84% of organizations claim a significant reduction in operations costs.
- **Innovation:** 81% of IT organizations become more innovative when tasks are handed over to automation tools.

## Project Execution
The project involves a threefold execution:

### 1. VPC Setup
- **Objective:** Set up a Virtual Private Cloud (VPC) using Ansible playbooks from the previous project.
- **Components:** VPC, subnets, security groups, Internet gateway, private subnets with NAT Gateway, and Bastion host.
- **Execution:** Pull code from the repository, execute the VPC playbook to establish the foundation for the infrastructure.

### 2. EC2 Instances and Load Balancer Setup
- **Objective:** Provision EC2 instances, an application load balancer, security groups, and key pairs for the V profile stack.
- **Components:** Public and private subnets, application load balancer, EC2 instances for V profile services (Tomcat, RabbitMQ, MySQL, etc.), security groups, and Bastion host.
- **Execution:** Write playbooks, execute them to create EC2 instances, load balancer, and associated components.

### 3. V Profile Stack Provisioning
- **Objective:** Use Ansible playbooks to provision services on EC2 instances, including MySQL, Memcache, RabbitMQ, Tomcat, and Engine X.
- **Execution:** Leverage the inventory file created during the second execution to connect to EC2 instances. Execute playbooks to set up the complete V profile stack.

## Architectural Design
### 1. VPC Setup
![VPC Setup](path/to/vpc_setup_diagram.png)
- **Description:** The VPC setup involves the creation of a VPC with subnets distributed across multiple zones. Public and private subnets are established, with an Internet gateway for public subnets and a NAT Gateway for private subnets. A Bastion host is set up inside a security group.

### 2. EC2 Instances and Load Balancer Setup
![EC2 Setup](path/to/ec2_setup_diagram.png)
- **Description:** This setup includes the creation of EC2 instances in private subnets, an application load balancer in the public subnet, security groups, and key pairs. Instances are distributed across two private zones, and a Bastion host is available for secure access.

### 3. V Profile Stack Provisioning
![V Profile Stack Provisioning](path/to/vprofile_stack_diagram.png)
- **Description:** The provisioning of the V profile stack involves setting up MySQL, Memcache, RabbitMQ, Tomcat, and Engine X services on the EC2 instances. A load balancer is created to distribute traffic to healthy instances.

## Getting Started
Follow these steps to execute the project:

1. Launch an EC2 instance to serve as the Ansible control machine.
2. Install Ansible and Boto3 on the Ansible control machine.
3. Set up an Ansible role for VPC setup (reuse from the previous project if available).
4. Execute the VPC setup playbook.
5. Write playbooks for EC2 instances and load balancer setup.
6. Execute playbooks for EC2 setup.
7. Choose between launching the controller in the V profile VPC or using a Bastion host.
8. If using a Bastion host, configure the necessary connections.
9. Execute playbooks to provision the V profile stack.

## Conclusion
This project demonstrates the power of Ansible in automating the provisioning and configuration of a complete infrastructure. By embracing automation, teams can achieve greater agility, reduce operational costs, and focus on innovative solutions. The project's threefold execution provides a systematic and automated approach to infrastructure setup, making it reusable and scalable across projects.
