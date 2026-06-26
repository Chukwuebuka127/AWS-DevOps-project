#  Project 04 - Load Balancer & Auto Scaling on AWS

![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![Architecture](https://img.shields.io/badge/Architecture-Highly%20Available-blue)
![Scaling](https://img.shields.io/badge/Auto--Scaling-Enabled-green)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

##  Overview

This project demonstrates a **highly available and scalable AWS cloud architecture** using:

- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- EC2 instances
- RDS MySQL database

It ensures:
- Zero downtime deployment
- Automatic scaling based on traffic
- Self-healing infrastructure (replaces failed instances automatically)

---

## 🌐 Live Application

 http://my-portfolio-alb-xxxxxxxx.eu-central-1.elb.amazonaws.com/api/tutorials



## 🏗️ Architecture
Internet
↓
Application Load Balancer (Port 80)
↓
Target Group (Port 8080)
↓
Auto Scaling Group
↓           ↓
EC2 Instance 1  EC2 Instance 2
↓           ↓
RDS MySQL Database


## AWS Services Used

| Service | Purpose |
|--------|--------|
| Application Load Balancer | Distributes traffic across EC2 instances |
| Target Group | Performs health checks & routing |
| Auto Scaling Group | Automatically scales EC2 instances |
| Launch Template | Defines EC2 configuration |
| EC2 | Runs application containers |
| RDS (MySQL) | Managed database service |

---

##  How It Works

### 🔹 Application Load Balancer (ALB)
- Entry point for all incoming traffic
- Routes requests to healthy EC2 instances only
- Performs health checks every 30 seconds
- Automatically removes unhealthy instances



### Auto Scaling Group (ASG)
- Maintains desired number of EC2 instances
- Scales out when CPU usage > 50%
- Scales in when demand decreases
- Replaces failed instances automatically



### Launch Template Automation
Each new EC2 instance automatically:
- Installs Docker
- Pulls application code from GitHub
- Builds Docker image
- Starts application container

 Fully automated provisioning (no manual setup)



##  Scaling Configuration

| Setting | Value |
|--------|--------|
| Minimum Instances | 1 |
| Desired Instances | 1 |
| Maximum Instances | 3 |
| Scale-Out Trigger | CPU > 50% |
| Scale-In Behavior | Automatic reduction |

---

## ⚠️ Issues & Solutions

### ❌ ALB requires multiple Availability Zones
**Problem:** Load Balancer setup failed with a single subnet.  
**Solution:** Added a second public subnet in another Availability Zone (`eu-central-1b`).

---

### ❌ Application unreachable via ALB
**Problem:** No access through Load Balancer URL.  
**Solution:** Updated security group to allow inbound HTTP traffic on port 80.

---

##  Key Learnings

- AWS Application Load Balancer traffic distribution
- Importance of health checks in production systems
- Horizontal scaling with Auto Scaling Groups
- Infrastructure automation using Launch Templates
- Building fault-tolerant cloud architectures
- Difference between vertical vs horizontal scaling

---

##  Future Improvements

- Enable HTTPS with AWS Certificate Manager (SSL/TLS)
- Add CloudWatch alarms for monitoring scaling events
- Implement sticky sessions for session-based applications
- Separate security groups for ALB and EC2 instances
- Add centralized logging (CloudWatch / ELK Stack)

---

##  Project Summary

This project transforms a single-server application into a **fault-tolerant, highly available cloud system**.

- The **Load Balancer ensures reliability**
- The **Auto Scaling Group ensures elasticity**
- The **Launch Template ensures automation**

Together, they form a production-grade AWS architecture that adapts automatically to traffic changes and server failures.



## 👨‍💻 Author

**Emmanuel**  
DevOps / Cloud Engineer
