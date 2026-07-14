# Project 07 – Kubernetes Deployment with Minikube

## Overview

This project demonstrates the deployment of a containerized application on a local Kubernetes cluster using **Minikube**. It showcases fundamental Kubernetes concepts, including Deployments, Pods, Services, replica management, and the Kubernetes Dashboard.

The goal of this project was to gain hands-on experience with Kubernetes orchestration and understand how applications are deployed and managed in a Kubernetes environment.

---

## Architecture

```
                Kubernetes Cluster (Minikube)
                           │
                           ▼
                    Deployment
                  (2 Replica Pods)
                    │         │
                    ▼         ▼
                 Pod 1      Pod 2
                    \         /
                     \       /
                      ▼     ▼
                 NodePort Service
                        │
                        ▼
                   User Browser
```

---

## Technology Stack

| Tool | Purpose |
|------|---------|
| Kubernetes | Container orchestration |
| Minikube | Local Kubernetes cluster |
| Docker | Container runtime |
| kubectl | Kubernetes command-line tool |
| NGINX | Sample web application |

---

## Project Features

- Local Kubernetes cluster using Minikube
- Application deployment using Kubernetes Deployments
- Two running pod replicas for high availability
- NodePort Service for external access
- Kubernetes Dashboard for cluster visualization
- Automatic pod recovery through Kubernetes self-healing

---

## Deployment Steps

### Start the Minikube Cluster

```bash
minikube start --driver=docker
```

### Deploy the Application

```bash
kubectl apply -f k8s-deployment.yaml
```

### Verify Resources

```bash
kubectl get pods

kubectl get deployments

kubectl get services
```

### Access the Application

```bash
minikube service nodejs-app
```

### Launch the Kubernetes Dashboard

```bash
minikube dashboard
```

---

## Kubernetes Concepts Demonstrated

- Pods
- Deployments
- ReplicaSets
- Services
- NodePort networking
- Container orchestration
- Self-healing
- Scaling applications
- Cluster management with kubectl

---

## Project Outcome

Successfully deployed a containerized application to a Kubernetes cluster and managed it using Kubernetes resources.

The application was exposed through a NodePort Service, while Kubernetes automatically maintained the desired number of running replicas, demonstrating its self-healing capabilities.

---

## Skills Demonstrated

- Kubernetes Fundamentals
- Container Orchestration
- Pod Management
- Deployments & ReplicaSets
- Service Networking
- kubectl Administration
- Minikube Cluster Management
- Docker Integration
- Linux Command Line

---

## Screenshots
<img width="955" height="538" alt="Screenshot 2026-07-14 110459" src="https://github.com/user-attachments/assets/f7660f99-6d5c-4167-ae06-5ecc90feef03" />

<img width="959" height="539" alt="Screenshot 2026-07-09 121036" src="https://github.com/user-attachments/assets/66afdb50-11ec-43bb-8bb9-d0eda13e6e56" />
<img width="953" height="484" alt="Screenshot 2026-07-14 122840" src="https://github.com/user-attachments/assets/84ba702b-2cdc-4eec-b3e2-14066bbb5026" />
<img width="817" height="458" alt="Screenshot 2026-07-14 123018" src="https://github.com/user-attachments/assets/75b2a11f-0071-473d-9701-958acc3b123f" />
<img width="957" height="538" alt="Screenshot 2026-07-14 123421" src="https://github.com/user-attachments/assets/5a3d090f-971f-4997-bbd1-379355f49dda" />


---

## Key Learnings

Through this project, I gained hands-on experience with:

- Deploying applications on Kubernetes.
- Managing Pods and Deployments.
- Exposing applications using Services.
- Scaling applications with replicas.
- Using kubectl to manage cluster resources.
- Understanding Kubernetes self-healing and desired state management.
- Navigating and monitoring resources using the Kubernetes Dashboard.
