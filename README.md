🚀 Project 05 - Infrastructure as Code (IaC) with Terraform

 Overview

This project recreates an AWS infrastructure entirely using Terraform, demonstrating the principles of Infrastructure as Code (IaC).

Instead of provisioning resources manually through the AWS Management Console, the complete infrastructure is defined in code, making deployments repeatable, version-controlled, and automated.

With a single command, Terraform provisions the complete environment, and it can be destroyed just as easily when no longer needed.

---

⚡ Deployment

Create the infrastructure:

terraform apply

Destroy the infrastructure:

terraform destroy

---

🏗️ Architecture

terraform apply
        │
        ▼
VPC (10.0.0.0/16)
        │
        ▼
Public Subnet (10.0.1.0/24)
        │
        ▼
Internet Gateway
        │
        ▼
Route Table
        │
        ▼
Security Group
(SSH :22, App :8080)
        │
        ▼
EC2 Instance (Ubuntu t3.micro)

---

📂 Project Structure

File| Purpose
"main.tf"| Defines all AWS infrastructure resources

---

☁️ AWS Resources Provisioned

Resource| Purpose
VPC| Creates an isolated virtual network
Public Subnet| Hosts public-facing resources
Internet Gateway| Enables internet connectivity
Route Table| Defines network routing
Route Table Association| Connects subnet to the route table
Security Group| Controls inbound and outbound traffic
EC2 Instance| Hosts the application server

---

🛠️ Terraform Commands

Command| Description
"terraform init"| Initializes Terraform and downloads required providers
"terraform plan"| Previews infrastructure changes before deployment
"terraform apply"| Creates the infrastructure
"terraform destroy"| Removes all managed infrastructure

---

⚠️ Challenges & Solutions

❌ Invalid AMI

Issue

The selected AMI was incompatible with the chosen EC2 instance type.

Solution

Used the AWS CLI to locate a compatible Ubuntu AMI for the "eu-central-1" region.

---

❌ Instance Type Compatibility

Issue

"t2.micro" was unavailable for the AWS account configuration.

Solution

Queried supported instance types using:

aws ec2 describe-instance-types

and migrated to the t3.micro instance type.

---

❌ Terraform Syntax Error

Issue

Terraform failed because of an unclosed configuration block in "main.tf".

Solution

Reviewed the configuration and corrected all missing braces until the configuration validated successfully.

---

📚 Key Learnings

- Writing Infrastructure as Code using Terraform HCL
- Understanding Terraform state management
- Managing dependencies between AWS resources
- Difference between "terraform plan" and "terraform apply"
- Automating cloud infrastructure deployments
- Using the AWS CLI to retrieve compatible AMIs and instance types

---

🚀 Future Improvements

- Provision an RDS MySQL database with Terraform
- Use Terraform variables for reusable configurations
- Store Terraform state remotely in an S3 backend
- Organize infrastructure using Terraform modules
- Implement Terraform workspaces for multiple environments
- Integrate Terraform into a CI/CD pipeline using GitHub Actions

---

🧠 Project Summary

This project demonstrates how Infrastructure as Code (IaC) replaces manual cloud provisioning with automated, repeatable deployments.

Instead of spending time configuring AWS resources through the console, the complete environment can be provisioned, updated, or destroyed using Terraform commands.

This approach improves consistency, reduces configuration errors, and forms a core practice of modern DevOps and Cloud Engineering.

---

👨‍💻 Author

Emmanuel

DevOps / Cloud Engineering Portfolio Project
