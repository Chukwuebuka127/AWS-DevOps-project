
#  Project 01 - Two-Tier Application Deployment on AWS

##  Project Overview
Designed and deployed a production-style two-tier web application on Amazon Web Services (AWS).

The architecture separates the application layer from the database layer, following industry best practices for security, scalability, and fault isolation commonly used in modern cloud systems.

---

## 🌐 Live Application
**API Endpoint:**
http://3.123.36.221:8080/api/tutorials

> Note: The application runs on an EC2 instance in a public subnet and securely connects to an AWS RDS MySQL database in a private subnet within a VPC.

---

## 🏗️ Architecture

Internet
   ↓
EC2 Instance (Node.js + Express API)
   ↓
AWS RDS (MySQL Database - Private Subnet)

### Architecture Breakdown:
- Application Layer: Handles HTTP requests and business logic
- Database Layer: Stores persistent data securely in a private subnet
- Network Design: Secure internal communication within a VPC

---

## 🛠️ Tools & AWS Services Used

| Tool / Service | Purpose |
|----------------|--------|
| AWS EC2 | Hosts Node.js application |
| AWS RDS (MySQL) | Managed relational database |
| AWS VPC | Provides isolated network environment |
| Subnets (Public & Private) | Network segmentation for security |
| Security Groups | Acts as virtual firewalls |
| Internet Gateway | Enables internet access for public subnet |
| Route Tables | Controls traffic routing |
| Node.js & Express | Backend REST API |
| Ubuntu 22.04 | Server OS |
| Git & GitHub | Version control |

---

##  What I Did

- Designed and implemented a custom AWS VPC for secure network isolation
- Created public and private subnets to separate application and database layers
- Deployed a Node.js + Express REST API on an EC2 instance in the public subnet
- Provisioned a MySQL database using AWS RDS in the private subnet
- Configured security groups to allow database access only from the application server
- Established secure internal communication between EC2 and RDS using private IP networking

---

## ⚠️ Problems Encountered & Solutions

### Problem 1: RDS Subnet Group Failure
RDS creation failed because the subnet group required subnets across at least two Availability Zones.  
**Solution:** Created an additional subnet in another Availability Zone.

---

### Problem 2: VPC DNS Configuration Issue
RDS deployment failed due to disabled DNS resolution in the VPC.  
**Solution:** Enabled DNS resolution and DNS hostnames in VPC settings.

---

### Problem 3: GitHub Authentication Error
Git push was rejected due to password authentication being deprecated.  
**Solution:** Generated a Personal Access Token (PAT) with repository permissions.

---

##  What I Learned

- How to design secure cloud architectures using AWS VPC and subnetting
- How to separate application and database tiers for better security
- How EC2 and RDS communicate within a private network
- Real-world AWS networking concepts (IGW, routing, security groups)
- Linux server setup and backend API deployment
- Debugging infrastructure issues in a cloud environment
- Git workflow and version control in real projects

---

##  Future Improvements

- Containerize the application using Docker
- Implement CI/CD pipeline using GitHub Actions
- Automate infrastructure provisioning using Terraform
- Add monitoring and logging using AWS CloudWatch or Prometheus
- Improve scalability using Auto Scaling Groups and Load Balancer

---

##  Project Summary
This project demonstrates a foundational understanding of cloud infrastructure, backend deployment, and secure network design using AWS. It simulates a real-world production environment with separated application and database layers.
