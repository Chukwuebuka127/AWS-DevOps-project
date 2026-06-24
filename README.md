#  Project 02 - Dockerized Application Deployment

##  Project Overview
Containerized the Node.js application from Project 01 using Docker to create a portable, consistent, and environment-independent deployment. This eliminates "it works on my machine" issues and provides a standardized runtime environment.

## 🌐 Live Application
http://3.123.36.221:8080/api/tutorials

## 🏗️ Architecture
Developer → Dockerfile → Docker Image → Docker Container → Node.js App (Port 8080) → MySQL Database (RDS)
## What is Docker?
Docker is a containerization platform that packages an application together with its dependencies into a lightweight container, ensuring the application runs consistently across different environments.

## Files Added
| File | Purpose |
|------|---------|
| `Dockerfile` | Defines the instructions used to build the application image |

## Deployment Workflow
1. Write Dockerfile
2. Build Docker Image
3. Run Docker Container
4. Application Available on Port 8080

## 🛠️ Commands Used
| Command | Purpose |
|---------|---------|
| `docker build -t nodejs-mysql-app .` | Build the application image |
| `docker run -d -p 8080:8080 --name my-app nodejs-mysql-app` | Start the container |
| `docker ps` | View running containers |
| `docker logs my-app` | Inspect container logs |
| `docker rm -f my-app` | Stop and remove the container |
| `docker images` | List locally available images |

## ⚠️ Problems Encountered & Solutions

**Problem 1: MySQL 8 Authentication Error**
The application failed to connect to MySQL because MySQL 8 uses caching_sha2_password by default.

**Solution:** Changed the user authentication method to mysql_native_password using:
```sql
ALTER USER 'username'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
Problem 2: Configuration Changes Not Reflected
Docker continued using a previously cached image after application changes.
Solution: Forced a clean rebuild using:
docker build --no-cache -t nodejs-mysql-app .

 What I Learned
How to write a Dockerfile from scratch
Difference between containers and virtual machines
Docker image build process and container lifecycle management
How to connect a containerized application to an external database
Container inspection and troubleshooting using Docker commands
Importance of immutable and portable application environments

 Future Improvements
Use Docker Compose to manage multi-container applications
Push images to Docker Hub for centralized image storage
Integrate Docker builds into a CI/CD pipeline
Deploy containers using Kubernetes for orchestration and scalability

Project Summary
This project demonstrates practical experience with containerization using Docker. By packaging the application into a container, the deployment process becomes portable, repeatable, and independent of the underlying host environment — a key principle in modern DevOps practices.
