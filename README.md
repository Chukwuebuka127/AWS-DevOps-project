 Project 03 – Automated CI/CD Pipeline with GitHub Actions

 Overview

This project demonstrates how to automate application deployments using GitHub Actions, Docker, and AWS EC2.

The goal was to eliminate manual deployments by creating a CI/CD pipeline that automatically deploys the latest application version whenever code is pushed to the main branch.

This project simulates a real-world DevOps workflow where code changes are continuously integrated and deployed with minimal human intervention.

🏗️ Architecture

Developer
    │
    │ git push
    ▼
GitHub Repository
    │
    ▼
GitHub Actions Workflow
    │
    ▼
Ubuntu Runner
    │
    ▼
SSH into AWS EC2
    │
    ▼
Pull Latest Source Code
    │
    ▼
Build Docker Image
    │
    ▼
Stop Existing Container
    │
    ▼
Start New Container
    │
    ▼
Updated Application Running

---

🌐 Live Demo

Application Endpoint

http://3.123.36.221:8080/api/tutorials

---

📁 Project Structure

.github/
└── workflows/
    └── deploy.yml

docker-compose.yml
Dockerfile
README.md

 How the Pipeline Works

1. A developer pushes code to the main branch.
2. GitHub automatically triggers the workflow.
3. GitHub provisions a temporary Ubuntu runner.
4. The runner securely retrieves SSH credentials from GitHub Secrets.
5. The runner connects to the EC2 server using SSH.
6. The latest source code is pulled from GitHub.
7. Docker rebuilds the application image.
8. The existing container is stopped.
9. A new container is started.
10. The latest version of the application becomes available automatically.

🔐 GitHub Secrets

Sensitive credentials are stored securely using GitHub Secrets.

Secret| Description
"EC2_HOST"| EC2 Public IP Address
"EC2_USERNAME"| Linux SSH User
"EC2_PRIVATE_KEY"| Private SSH Key

No credentials are stored inside the repository.

🛠️ Technologies Used

- GitHub Actions
- Docker
- AWS EC2
- Ubuntu Linux
- Git
- SSH
- appleboy/ssh-action

 CI/CD Workflow

Code Change
      │
      ▼
git push
      │
      ▼
GitHub Actions Triggered
      │
      ▼
SSH into EC2
      │
      ▼
git pull
      │
      ▼
docker build
      │
      ▼
docker stop
      │
      ▼
docker run
      │
      ▼
Deployment Complete ✅


⚠️ Challenges Encountered

1. GitHub Workflow Permission Error

Problem

The workflow failed because the authentication token did not have permission to update workflow files.

Solution

Generated a new GitHub Personal Access Token (PAT) with the workflow permission enabled.

2. SSH Connection Timeout

Problem

GitHub Actions could not establish an SSH connection with the EC2 instance.

Solution

Updated the AWS Security Group to allow inbound SSH traffic on port 22.


 Key Learnings

Through this project I learned how to:

- Build a CI/CD pipeline using GitHub Actions.
- Automate deployments to an AWS EC2 instance.
- Secure sensitive credentials with GitHub Secrets.
- Connect securely to remote Linux servers using SSH.
- Deploy Dockerized applications automatically.
- Troubleshoot GitHub Actions workflow failures.
- Debug SSH connectivity issues.
- Eliminate manual deployment steps.



 Future Improvements

- Add automated unit tests before deployment.
- Deploy only if all tests pass.
- Push Docker images to Docker Hub or GitHub Container Registry.
- Send deployment notifications to Slack.
- Restrict SSH access instead of allowing connections from anywhere.
- Implement Infrastructure as Code using Terraform.
- Add rollback support if deployment fails.


💡 Skills Demonstrated

- CI/CD Pipelines
- GitHub Actions
- Docker
- Linux Administration
- AWS EC2
- SSH
- Git
- Secrets Management
- Deployment Automation
- Troubleshooting


Project Summary

This project demonstrates the implementation of a fully automated deployment pipeline using GitHub Actions and AWS.

Instead of manually connecting to the server after every code change, deployments are triggered automatically whenever changes are pushed to the main branch. The workflow securely connects to the EC2 instance, updates the application, rebuilds the Docker image, and restarts the container.

This project showcases practical DevOps skills including automation, Linux administration, Docker, AWS, CI/CD, and secure credential management, reflecting a workflow commonly used in modern software delivery.
