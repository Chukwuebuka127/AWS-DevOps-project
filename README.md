🚀 AWS DevOps Engineering Portfolio

«“I built and broke real infrastructure on AWS so I could learn how production systems actually behave.”»

This repository documents a hands-on DevOps engineering journey built on AWS. Every project here represents real infrastructure I designed, deployed, and debugged — not just tutorial walkthroughs.

The goal of this portfolio is simple:

«Show how I think as an engineer, not just what tools I’ve seen.»

---

👨‍💻 About This Portfolio

Most DevOps portfolios focus on certifications and tool lists.

This one focuses on systems thinking and execution.

I started from the basics and progressively built:

- Cloud infrastructure (AWS networking + compute)
- Containerized applications (Docker)
- Automated deployments (CI/CD pipelines)
- Infrastructure as Code (Terraform)
- Scalable architectures (Load balancing + Auto Scaling)
- Observability systems (Monitoring + alerting)

Every stage introduced real problems — and the documentation reflects how those problems were solved.

---

🧭 How to Navigate This Repo

Each branch represents a stage in system maturity.
| Stage | Branch | What I Built | What I Learned |
|------|--------|-------------|----------------|
| 01 | 01-two-tier | Node.js + MySQL deployed on AWS | Networking, EC2, RDS, security groups |
| 02 | 02-dockerized | Containerized application using Docker | Images, containers, environment consistency |
| 03 | 03-cicd | Automated deployments using CI/CD | GitHub Actions, automation workflows |
| 04 | 04-load-balancer | High availability architecture | ALB, Auto Scaling, fault tolerance |
| 05 | 05-terraform | Full infrastructure as code | Reproducible cloud environments |
| 06 | 06-kubernetes | Container orchestration at scale | Pods, deployments, service discovery |
| 07 | 07-monitoring | Observability layer | Metrics, logs, alerting, dashboards |


---

🧠 Architecture Evolution

Stage 1 — Basic Deployment

Simple 2-tier system:

Internet → EC2 (Node.js) → RDS (MySQL)

---

Stage 2 — Containerized System

Introduced Docker:

EC2 → Docker Container → RDS

---

Stage 3 — Automated Deployment

CI/CD pipeline added:

GitHub → CI/CD → EC2 deployment

---

Stage 4 — Scalable Architecture

Improved availability:

ALB → Auto Scaling Group → Multiple EC2 instances → RDS

---

Stage 5 — Infrastructure as Code

Everything becomes reproducible:

Terraform → Entire AWS stack

---

Stage 6 — Orchestration

Kubernetes introduced:

ALB → EKS Cluster → Pods → RDS

---

Stage 7 — Observability

System visibility added:

Prometheus + Grafana + CloudWatch alerts

---

⚙️ Tools & Technologies

- AWS (EC2, VPC, RDS, ALB, IAM, CloudWatch)
- Docker
- Kubernetes (EKS)
- Terraform
- GitHub Actions
- Linux (Ubuntu)
- Node.js
- MySQL
- Prometheus & Grafana

---

💡 Key Engineering Principles Applied

Throughout this project, I focused on:

- Separation of concerns (app vs infrastructure vs data)
- Reproducibility (Terraform-based infrastructure)
- Automation over manual work (CI/CD pipelines)
- Scalability thinking (load balancing + auto scaling)
- Failure awareness (logs, monitoring, debugging)
- Security basics (IAM roles, network isolation)

---

🧪 What This Repo Demonstrates

This is not just a list of tools.

It demonstrates:

- How I approach system design problems
- How I debug infrastructure issues
- How I evolve a system over time
- How I automate manual processes
- How I think in production environments

---

📊 Project Summary

- AWS Services Used: 12+
- Infrastructure rebuilt multiple times across stages
- CI/CD pipelines implemented and tested
- Containers deployed in real environments
- Monitoring and alerting configured
- Infrastructure defined as code (Terraform)

---

🔗 Connect With Me

- GitHub: https://github.com/Chukwuebuka127
- LinkedIn: https://https://www.linkedin.com/in/emmanuel-orjide-787722366?utm_source=share_via&utm_content=profile&utm_medium=member_android

---

«“I don’t just learn tools — I build systems, break them, and rebuild them better.”»
