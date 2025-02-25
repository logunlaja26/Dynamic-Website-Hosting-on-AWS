# Dynamic Website Hosting on AWS

## Project Overview
This project demonstrates the deployment of a dynamic website on AWS using multiple services and best practices to ensure high availability, security, and scalability. The project is structured using Infrastructure as Code (IaC) principles, with all deployment scripts and a reference diagram available in the associated [GitHub repository](<your-repo-link-here>).

## Architecture & Resources Used

1. **Virtual Private Cloud (VPC):** Configured a VPC with both public and private subnets spanning two Availability Zones (AZs) to provide a secure and scalable network infrastructure.
2. **Internet Gateway (IGW):** Deployed an Internet Gateway to enable connectivity between the VPC instances and the wider internet.
3. **Security Groups:** Established security groups to serve as network firewall mechanisms, defining inbound and outbound traffic rules.
4. **Multi-AZ Deployment:** Leveraged two Availability Zones to improve system reliability and fault tolerance.
5. **Public Subnets:** Utilized for infrastructure components such as the NAT Gateway and Application Load Balancer (ALB).
6. **EC2 Instance Connect Endpoint:** Implemented for secure connections to assets within both public and private subnets.
7. **Private Subnets:** Hosted web servers (EC2 instances) within private subnets to enhance security.
8. **NAT Gateway:** Allowed instances in private Application and Data subnets to access the internet while keeping them isolated from direct internet exposure.
9. **EC2 Instances:** Hosted the website on EC2 instances, ensuring reliable performance and scalability.
10. **Application Load Balancer (ALB):** Used to distribute incoming web traffic evenly to an Auto Scaling Group of EC2 instances across multiple AZs.
11. **Auto Scaling Group (ASG):** Automatically managed EC2 instances, ensuring website availability, scalability, fault tolerance, and elasticity.
12. **AWS Certificate Manager (ACM):** Secured application communications with SSL/TLS certificates.
13. **Simple Notification Service (SNS):** Configured to send alerts and notifications regarding activities within the Auto Scaling Group.
14. **Route 53:** Registered a domain name and set up DNS records for the website.
15. **Amazon S3:** Used to store application code and deployment scripts for improved accessibility and security.

## Deployment Steps
1. **Clone the Repository:**
   ```sh
   git clone <your-repo-link-here>
   cd <project-directory>
   ```
2. **Setup AWS CLI & Terraform:**
   - Ensure AWS CLI is installed and configured with the necessary permissions.
   - Install Terraform and initialize the project.
   ```sh
   terraform init
   ```
3. **Deploy Infrastructure:**
   ```sh
   terraform apply -auto-approve
   ```
4. **Verify Resources:**
   - Check VPC, subnets, security groups, and EC2 instances via the AWS Management Console.
   - Confirm domain resolution using Route 53.
   - Verify ALB health checks and Auto Scaling Group behavior.
5. **Access the Website:**
   - Retrieve the ALB DNS name and access the website in a browser.
   ```sh
   aws elbv2 describe-load-balancers --query 'LoadBalancers[*].DNSName'
   ```
6. **Monitor and Manage:**
   - Check SNS notifications for Auto Scaling Group updates.
   - Adjust scaling policies as needed.
   - Secure SSH access using EC2 Instance Connect.

## Conclusion
This project effectively showcases the deployment of a scalable and secure dynamic website on AWS. By leveraging a combination of AWS services, best practices, and automation, it ensures high availability, security, and ease of management.

For more details, refer to the [GitHub repository](<your-repo-link-here>) and the architecture diagram included.

