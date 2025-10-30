# GitOps-CI-CD-Pipeline-with-GitLab-AWS-EKS-and-Helm

[![GitLab CI/CD](https://img.shields.io/badge/GitLab-CI%2FCD-orange)](https://gitlab.com)
[![Terraform](https://img.shields.io/badge/Terraform-v1.5+-blue)](https://terraform.io)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.27+-blue)](https://kubernetes.io)
[![AWS EKS](https://img.shields.io/badge/AWS-EKS-orange)](https://aws.amazon.com/eks/)

## Overview

A production-grade GitOps implementation demonstrating automated infrastructure provisioning, continuous integration, and continuous deployment using modern DevOps tools and practices. This project showcases a complete CI/CD workflow using GitLab, Terraform, AWS EKS, Helm, and Docker.

## Architecture

This project implements a three-pipeline GitOps architecture:

1. **Infrastructure Pipeline (Terraform)** - Manages AWS EKS cluster lifecycle
2. **CI Pipeline (Application)** - Builds, tests, and containerizes Java application
3. **CD Pipeline (Helm)** - Deploys application to Kubernetes cluster

### Key Features

- Infrastructure as Code using Terraform for EKS cluster management
- Automated CI/CD pipelines with GitLab CI/CD
- Container orchestration with Kubernetes on AWS EKS
- Helm-based application deployment with environment-specific configurations
- Automated drift detection for infrastructure compliance
- Code quality enforcement with SonarCloud and Checkstyle
- Docker containerization with GitLab Container Registry
- IAM role-based authentication for secure AWS access
- Scheduled drift detection with Slack notifications

## Technology Stack

### Core Technologies

| Category | Tools |
|----------|-------|
| **Version Control & CI/CD** | GitLab, Git |
| **Cloud Infrastructure** | AWS (EKS, EC2, VPC, IAM, S3) |
| **Infrastructure as Code** | Terraform |
| **Container Orchestration** | Kubernetes (EKS), Helm |
| **Containerization** | Docker |
| **Build & Test** | Maven, JUnit, Checkstyle |
| **Code Quality** | SonarCloud |
| **Notifications** | Slack |

## Repository Structure

.
├── terraform/ # EKS infrastructure code
├── helm-charts/ # Kubernetes deployment manifests
├── application/ # Java application source code
├── scripts/ # Automation scripts
└── docs/ # Detailed documentation

## Prerequisites

- AWS Account with appropriate permissions
- GitLab account (Free tier sufficient)
- Basic understanding of Kubernetes, Docker, and CI/CD concepts
- AWS CLI configured locally
- Terraform v1.5+
- kubectl v1.27+
- Helm v3+

## GitOps Principles

This project implements core GitOps principles:

- **Git as Single Source of Truth** - All configurations stored in Git repositories
- **Declarative Configuration** - Infrastructure and applications defined declaratively
- **Automated Synchronization** - Pipelines automatically apply changes
- **Continuous Reconciliation** - Drift detection ensures compliance
- **Version Control** - Complete audit trail of all changes

## Key Benefits

- **Full Automation** - Zero manual deployments
- **Traceability** - Complete audit trail via Git commits
- **Easy Rollback** - Revert Git commits to rollback changes
- **Drift Detection** - Automated checks ensure infrastructure integrity
- **Fast Deployment** - Automated pipelines reduce deployment time
- **Reduced Errors** - Automated validation catches mistakes early
- **Environment Consistency** - Same pipeline for all environments

## Security Best Practices

- IAM roles for EC2 runner (no hardcoded credentials)
- Secrets stored in GitLab CI/CD variables
- Protected branches with approval requirements
- Network isolation via VPC configuration
- Regular security scanning with SonarCloud
