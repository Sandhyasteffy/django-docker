\# Automated Docker Application Deployment Using Jenkins, GHCR, Terraform and AWS



\## 📌 Project Overview



This project demonstrates a complete DevOps workflow for deploying a containerized Django application.



The application source code is maintained in GitHub. Jenkins automatically builds the Docker image and pushes it to GitHub Container Registry (GHCR). Terraform is used to provision the AWS infrastructure consisting of a VPC, two public subnets in different Availability Zones, and two EC2 instances.



The final Docker deployment to EC2 is performed manually as required for the project.



\---



\## 🏗️ Architecture



```text

Developer

&#x20;   │

&#x20;   ▼

&#x20;GitHub

&#x20;   │

&#x20;   ▼

&#x20;Jenkins

&#x20;   │

&#x20;   ├── Docker Build

&#x20;   │

&#x20;   ├── Docker Tag

&#x20;   │

&#x20;   └── Push Image

&#x20;         │

&#x20;         ▼

&#x20;       GHCR

&#x20;         │

&#x20;         │ Manual Pull

&#x20;         ▼

&#x20;    AWS VPC

&#x20;  11.0.0.0/16

&#x20;         │

&#x20;   ┌─────┴─────┐

&#x20;   │           │

&#x20;   ▼           ▼

Public       Public

Subnet 1     Subnet 2

11.0.1.0/24  11.0.2.0/24

AZ-1         AZ-2

&#x20;   │           │

&#x20;   ▼           ▼

&#x20; EC2-1       EC2-2

&#x20;   │           │

&#x20;   └── Docker ┘

