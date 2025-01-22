
## Overview:
This runbook outlines the steps to provision and configure a secure, scalable cloud infrastructure for application deployment.

## Infra-architecture:
![Aura-Architecture](https://github.com/user-attachments/assets/56fad0f3-29da-4fc5-870e-344658f3759b)


## Cloud Platform Details:

**Cloud Provider:** AWS (Amazon Web Services)
### Region-Specific Configuration:

- **Development:** The us-east-1 region is used for the development environment, chosen for its lower latency in North American operations.
- **Stage:** The us-east-2 (Ohio) region is used for UAT testing to ensure that testing environments are isolated and separated from production.
- **Production:** All resources are provisioned and deployed within the Mumbai region (ap-south-1) for production, ensuring data residency and compliance with region-specific requirements.

## Scope:
This runbook outlines the process for setting up and managing cloud infrastructure using AWS services for three environments: Development (Dev), Staging (Stage), and Production (Prod). The following AWS services are included in the setup:

- **Elastic Compute Cloud (EC2)**:\
    Provision and manage scalable virtual machines for application deployment in all environments.
- **Elastic Load Balancing (ELB)**:\
    Set up and manage load balancers to distribute incoming traffic across EC2 instances, ensuring high availability and fault tolerance.
- **Virtual Private Cloud (VPC)**:\
    Design and configure isolated networking environments, subnets, and routing tables for secure communication between resources in each environment.
- **CloudWatch:**\
    Monitor infrastructure performance, set up custom metrics, logs, and alarms for operational visibility and proactive issue resolution.
- **Route 53:**\
    Manage domain name system (DNS) services for routing traffic to the appropriate resources in each environment.
- **Secrets Manager:**\
    Safely store and retrieve sensitive data such as API keys, passwords, and connection strings for applications and services.
- **Simple Storage Service (S3):**\
    Provision and configure scalable object storage for backup, data storage, and static content delivery.
- **Data Transfer:**\
    Utilize tools and services for moving data between AWS regions, on-premise infrastructure, and within environments.
- **CloudFront:**\
    Implement content delivery network (CDN) services to optimize the delivery of static and dynamic content to end users globally.
- **CloudTrail:**\
    Enable detailed logging of API activity to monitor and audit AWS resources for security and compliance purposes.
- **Key Management Service (KMS):**\
    Manage encryption keys for securing data at rest and in transit, ensuring compliance with security standards.
- **Simple Notification Service (SNS):**\
  	Set up messaging and notification systems for sending alerts, updates, and automated responses across environments.
- **AWS Chatbot:**\
  	Use AWS Chatbot for notifications and real-time alerts in Slack or Amazon Chime, allowing teams to stay informed on system health and issues through messaging channels.
- **AWS CodePipeline:**\
  	Automate the continuous integration and continuous delivery (CI/CD) process to ensure rapid and reliable application deployment across Dev, Stage, and Prod 
    environments.
- **AWS CodeDeploy**:\
    Automate application deployment to various compute resources (EC2, Lambda) to streamline the release process, ensuring quick and consistent deployments with 
   minimal downtime.

 ## Provisioning and Configuration:
 [https://github.com/atomedgesoft/aura-cloud]

 ## Security and Compliance:

| Team            | Role/Responsibilities                                         | Interaction with Infrastructure                                         |
|-----------------|---------------------------------------------------------------|------------------------------------------------------------------------|
| DevOps Team     | Responsible for provisioning, configuring, and managing cloud infra. | Direct access to all cloud resources and infrastructure management.     |
| Frontend Team   | Runs the build pipeline for frontend applications. Access ECR repositories and S3 buckets. | Builds the docker image using code pipeline and pushes to ECR. Access some files to S3. |
| Backend Team    | Runs the build pipeline for backend services. Access to ECR repositories and S3 buckets. | Builds the docker image using code pipeline and pushes to ECR. Access some files to S3. |
| Testing Team    | Tests the docker image generated in ECR for all frontend backend and DB .              | Access to ECR. Some cases they will also need access to code pipeline to build the docker image. |

## Manual Setup (Cloudflare and Route 53 configuration settings):

 
### 1. aesoft.ai DNS setting with AWS cloudfront in cloudflare

![image](https://github.com/user-attachments/assets/8bf1a660-e050-4db8-b827-f97ef7b63e5a)

### 2. Subdomain DNS settings to map with AWS loadbalancer

![image](https://github.com/user-attachments/assets/e2046c05-d36d-43e3-873a-bca455ebd123)

### 3. Creating SSL certificates in ACM AWS CNAME Name and CNAME Value

![image](https://github.com/user-attachments/assets/0cb2a2d8-8ff1-4098-bd45-187cced6c572)

### 4. Update  from ACM to below cloudflare corresponding setup.

![image](https://github.com/user-attachments/assets/0bc0dd36-dbee-4459-a715-60820127a8e1)

# Build and Deployment Procedures

Below link provides the information about the build pipeline for all (Frontend/Backend/DB) services.

[https://github.com/atomedgesoft/builder/edit/main/Aura-Middleware-Build-Pipeline(Terraform)/README.md]

[https://github.com/atomedgesoft/builder/blob/main/Aura-HRMS-Build-Pipeline(Terraform)/README.md]

[https://github.com/atomedgesoft/builder/blob/main/Aura-Database-Build-Pipeline(Terraform)/README.md]

Below link provides information about the deploy pipeline and its region where it is located.

[https://github.com/atomedgesoft/aura-multi-stage-pipeline/tree/main]








