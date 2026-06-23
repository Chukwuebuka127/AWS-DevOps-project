#  Project 01 - Two-Tier Application Deployment on AWS

##  Project Overview
Deployed a production-style 2-tier web application on Amazon Web Services (AWS).
The architecture separates the application layer from the database layer,
following industry best practices for security and scalability.

## 🌐 Live Application
http://<your-ec2-public-ip>:8080/api/tutorials

## 🏗️ Architecture
Internet → EC2 (Node.js REST API) → RDS (MySQL Database)

## 🛠️ Tools & Services Used
| Tool | Purpose |
|------|---------|
| AWS EC2 | Hosts the Node.js application |
| AWS RDS (MySQL) | Managed relational database |
| AWS VPC | Isolated private network |
| Security Groups | Firewall rules for EC2 and RDS |
| Internet Gateway | Connects VPC to the internet |
| Route Tables | Controls network traffic routing |
| Git & GitHub | Version control |
| Ubuntu 22.04 | Server operating system |
| Node.js & Express | Backend REST API framework |

##  What I Did
- Created a custom VPC with public and private subnets
- Launched an EC2 instance in the public subnet
- Deployed a Node.js REST API on the EC2 instance
- Provisioned a MySQL RDS instance in the private subnet
- Connected the application to the database securely
- Configured security groups to restrict database access to EC2 only

##  Problems Encountered & Solutions

**Problem 1: RDS subnet group failed**
The DB subnet group required subnets in at least 2 availability zones.
*Solution:* Created an additional subnet in a second availability zone.

**Problem 2: VPC DNS settings**
RDS creation failed due to DNS resolution being disabled on the VPC.
*Solution:* Enabled DNS resolution and DNS hostnames in VPC settings.

**Problem 3: GitHub authentication failed**
Git push was rejected because GitHub no longer accepts passwords.
*Solution:* Generated a Personal Access Token with repo permissions.

##  What I Learned
- How to design and implement AWS networking from scratch
- The importance of separating public and private subnets for security
- How to securely connect application and database tiers
- Linux server administration and Node.js deployment
- Git version control and GitHub repository management

