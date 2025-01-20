
## Overview:
This runbook outlines the steps to provision and configure a secure, scalable cloud infrastructure for application deployment.

## Infra-architecture
![image](https://github.com/user-attachments/assets/be0e14d9-aee4-4c3f-871e-0c2c11c6371c)

## Follow the link to initiate the infra
[https://github.com/harishmahalingam03/One-Infra-doc]

## Cloud Platform Details:
Cloud Provider: **AWS (Amazon Web Services)**
### Region-Specific Configuration:
- **Production:** All resources are provisioned and deployed within the Mumbai region (ap-south-1) for production, ensuring data residency and compliance with region-specific requirements.
- **Development:** The us-east-1 region is used for the development environment, chosen for its lower latency in North American operations.
- **UAT:** The us-east-2 (Ohio) region is used for UAT testing to ensure that testing environments are isolated and separated from production.


## Scope
This runbook outlines the process for setting up and managing cloud infrastructure using AWS services for three environments: Development (Dev), Staging (Stage), and Production (Prod). The following AWS services are included in the setup:

1.	**Elastic Compute Cloud (EC2)**:\
    Provision and manage scalable virtual machines for application deployment in all environments.
2.	**Elastic Load Balancing (ELB)**:\
    Set up and manage load balancers to distribute incoming traffic across EC2 instances, ensuring high availability and fault tolerance.
3.	**Virtual Private Cloud (VPC)**:\
    Design and configure isolated networking environments, subnets, and routing tables for secure communication between resources in each environment.
4.	**CloudWatch:**\
    Monitor infrastructure performance, set up custom metrics, logs, and alarms for operational visibility and proactive issue resolution.
5.	**Route 53:**\
    Manage domain name system (DNS) services for routing traffic to the appropriate resources in each environment.
6.	**Secrets Manager:**\
    Safely store and retrieve sensitive data such as API keys, passwords, and connection strings for applications and services.
7.	**Simple Storage Service (S3):**\
    Provision and configure scalable object storage for backup, data storage, and static content delivery.
8.	**Data Transfer:**\
    Utilize tools and services for moving data between AWS regions, on-premise infrastructure, and within environments.
9.	**CloudFront:**\
    Implement content delivery network (CDN) services to optimize the delivery of static and dynamic content to end users globally.
10.	**CloudTrail:**\
    Enable detailed logging of API activity to monitor and audit AWS resources for security and compliance purposes.
11.	**Key Management Service (KMS):**\
    Manage encryption keys for securing data at rest and in transit, ensuring compliance with security standards.
12.	**Simple Notification Service (SNS):**\
  	Set up messaging and notification systems for sending alerts, updates, and automated responses across environments.
13.	**AWS Chatbot:**\
  	Use AWS Chatbot for notifications and real-time alerts in Slack or Amazon Chime, allowing teams to stay informed on system health and issues through messaging channels.
14.	**AWS CodePipeline:**
  	Automate the continuous integration and continuous delivery (CI/CD) process to ensure rapid and reliable application deployment across Dev, Stage, and Prod 
    environments.
15.	**AWS CodeDeploy**:
    Automate application deployment to various compute resources (EC2, Lambda) to streamline the release process, ensuring quick and consistent deployments with 
   minimal downtime.
