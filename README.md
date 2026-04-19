# 🚀 Azure 3-Tier Architecture using Terraform

## 📌 Overview
This project demonstrates provisioning of a **secure 3-tier architecture** in Microsoft Azure using **Terraform (Infrastructure as Code)**.

The architecture includes:
- Web Tier (Public VM)
- App Tier (Private VM)
- Database Tier (Highly Secured Private VM)

---

## 🧱 Architecture

![Architecture](images/architecture.png)

---

## 🏗️ Resources Created

- Resource Group
- Virtual Network (VNet)
- Subnets:
  - Web Subnet
  - App Subnet
  - DB Subnet
- Network Security Groups (NSGs)
- Public IP (Web VM only)
- Network Interfaces
- Linux Virtual Machines:
  - Web VM
  - App VM
  - DB VM

---

## 🔐 Security Design

- Only Web VM has Public Access
- App VM is accessible **only from Web Subnet**
- DB VM is accessible **only from App Subnet**
- NSGs enforce strict inbound rules
- No direct internet exposure for App & DB tiers

---

## ⚙️ Technologies Used

- Terraform
- Microsoft Azure
- Azure CLI
- Linux (Ubuntu / RHEL)

---

## 🚀 Deployment Steps

```bash
# Login to Azure
az login

# Initialize Terraform
terraform init

# Validate configuration
terraform validate

# Plan deployment
terraform plan

# Apply changes
terraform apply


🧪 Testing
Web Tier

Access via browser:

http://<web-public-ip>
App Tier (Private Access)
SSH → Web VM → App VM
DB Tier (Restricted Access)
SSH → Web → App → DB
