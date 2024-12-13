##3-Tier Architecture Website with EFS
This project demonstrates the implementation of a 3-tier architecture for a website, utilizing AWS CloudFormation for infrastructure automation and EFS for scalable storage.

##Architecture Overview:
The architecture is divided into three layers:

##Network Layer
This layer creates a robust networking infrastructure to support a scalable and secure multi-tier application architecture. It includes the following components:

- *VPC (Virtual Private Cloud): Defines the network environment for the application.
- *Public and Private Subnets: Organizes resources in different network segments for security and scalability.
- *Internet Gateway: Allows communication between instances in the VPC and the internet.
- *NAT Gateway: Enables instances in the private subnets to access the internet securely.
- *Route Tables: Manages the traffic routing within the VPC.
- *Security Groups: Provides stateful firewall protection for instances and resources.
- *This network infrastructure ensures a solid foundation for hosting applications with secure, scalable, and high-availability capabilities.

##The Application Layer for a multi-tier architecture, incorporating several key components to ensure high availability, scalability, and security. The main features of this layer include:

- *Auto Scaling Group (ASG): Automatically adjusts the number of EC2 instances based on traffic demand to maintain optimal performance and resource efficiency.
- *Application Load Balancer (ALB): Distributes incoming traffic across multiple EC2 instances to ensure fault tolerance and high availability of the application.
- *Route 53 DNS Integration: The template creates a Route 53 record set to associate the ALB with the domain shashabou.com. This ensures that user requests to your domain are routed seamlessly to the ALB, which handles traffic distribution to the EC2 instances.
- *EC2 Instances: Compute resources running the application, dynamically scaled by the Auto Scaling group to handle varying traffic loads.
- *Amazon EFS (Elastic File System): Provides scalable, shared file storage across EC2 instances, allowing them to share data seamlessly across availability zones.
- *HTTPS Communication: Secures user communication with the application via SSL/TLS encryption, ensuring data privacy and integrity. The ALB is configured to use an SSL/TLS certificate from AWS Certificate Manager (ACM) for HTTPS traffic.
- *CloudWatch Monitoring & SNS Alerts: Provides real-time monitoring for application health and performance. Automated alerts are sent to the operator’s email on scaling events, high CPU utilization, or other critical operational issues.

##Database Layer
 This AWS CloudFormation template defines the database layer for the multi-tier architecture, utilizing Amazon RDS to provide a fully managed relational database service. The main features of this layer include:

- *Amazon RDS Instance: Deploys a MySQL database instance (or other supported engines like PostgreSQL, MariaDB, Oracle, or Aurora) with customizable configurations such as instance type, storage size, and backup retention.
- *Database Subnet Group: Ensures that the RDS instance is deployed in private subnets within a Virtual Private Cloud (VPC), with fault-tolerant and isolated networking.
- *Scalable and Secure: The database can be scaled according to performance needs with a range of instance types (e.g., db.t3.micro, db.t3.small, db.t3.medium). Security is maintained with the use of VPC Security Groups and Multi-AZ deployment options for high availability.
- *Automated Backups: Configures automated backup retention periods for disaster recovery and data protection.
- *Public Accessibility: The database can be configured to be publicly accessible or kept private, depending on your security requirements.
- *Multi-AZ Support: Configures the database instance to span across multiple availability zones, ensuring high availability and disaster recovery in case of a failure.
- *This template ensures that your database layer integrates seamlessly with the networking and application layers, providing a fully managed and scalable database solution.

##Current Progress:
 The network, application, and database layers have been completed. Currently, work is underway to mount EFS and configure Apache and WordPress using Ansible. This setup ensures high availability, scalability, and efficient storage, while the project aims to automate the deployment and scaling of resources based on traffic demands.

##To Do:
- *Mount Amazon EFS to EC2 instances
- *Configure Apache and WordPress using Ansible
- *Test the entire stack for high availability and scalability

##Configure Apache web server
Install and configure WordPress on EC2 instances using Ansible automation
