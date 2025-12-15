# cloud-devops-k8s-platform
Enterprise-Style Kubernetes Platform using AWS EKS, Terraform, Helm, and CI/CD
# Cloud DevOps Kubernetes Platform

## Overview
This project demonstrates a **production-style Cloud DevOps platform** built on Kubernetes.  
It focuses on automating infrastructure, deploying microservices reliably, and applying security and observability best practices.

The goal is to showcase hands-on experience with **AWS EKS, Terraform, Helm, CI/CD, and Kubernetes operations** in an enterprise-like environment.

---

## What This Project Covers
- Kubernetes cluster provisioning using **Terraform**
- Microservices deployment using **Helm charts**
- Automated build and deployment with **CI/CD pipelines**
- Kubernetes security (**RBAC, ServiceAccounts, Secrets**)
- Monitoring and logging with **Prometheus, Grafana, and Loki**
- Clear documentation and operational practices

---

## Architecture (High Level)
- AWS VPC
- Amazon EKS
- Managed node groups
- Ingress controller
- Frontend and backend microservices
- CI/CD pipeline
- Observability stack

User  
↓  
Ingress  
↓  
Service  
↓  
Pods (Frontend / Backend)

---

## Tech Stack
- **Cloud:** AWS (EKS, VPC, IAM, ECR)
- **Infrastructure as Code:** Terraform
- **Containers & Orchestration:** Docker, Kubernetes
- **Packaging:** Helm
- **CI/CD:** GitHub Actions
- **Monitoring:** Prometheus, Grafana
- **Logging:** Loki

---

## Repository Structure

├── terraform/        # Infrastructure (EKS, VPC, IAM)
├── helm/             # Helm charts
│   ├── frontend/
│   └── backend/
├── apps/             # Application source code
├── ci-cd/            # CI/CD pipelines
└── README.md

---

## How It Works

### 1. Provision Infrastructure
Infrastructure is created using Terraform.

    cd terraform
    terraform init
    terraform apply

### 2. Configure Kubernetes

- Connect to the EKS cluster
- Create namespaces (dev, prod)
- Install ingress controller and metrics server

### 3. Deploy Applications

Applications are deployed using Helm charts.
    helm install backend ./helm/backend -n dev
    helm install frontend ./helm/frontend -n dev

Helm charts include:
- Resource requests and limits
- Liveness and readiness probes
- Environment-based configuration

### 4. CI/CD Automation

A GitHub Actions pipeline:
1. Builds Docker images
2. Pushes images to Amazon ECR
3. Runs Helm lint
4. Deploys applications to Kubernetes

### Security

- Namespace-level RBAC
- Dedicated ServiceAccounts per application
- Secrets managed securely
- Least-privilege access model

### Monitoring & Logging

- Prometheus collects cluster and application metrics
- Grafana visualizes performance and health
- Loki centralizes application logs for troubleshooting

---

## Why This Project

This project reflects how Kubernetes platforms are built and operated in real enterprise environments, with an emphasis on:
- Reliability
- Security
- Automation
- Observability
- Documentation
  
