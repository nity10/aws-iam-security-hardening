# aws-iam-security-hardening
Project 3: AWS Identity &amp; Security Governance

# 🛡️ AWS Cloud Security: IAM Roles & Network Hardening

## 📌 Project Overview
This project implements the "Defense in Depth" security strategy on AWS. It focuses on granular access control using **IAM Roles** and network traffic filtering using **Security Groups**.

## ⚙️ Implementation Steps

### 1. Network Security (Security Groups)
Created a custom Security Group (`practise1`) to enforce the **Principle of Least Privilege**:
- **Allowed:** SSH (Port 22) strictly for system administration.
- **Blocked:** All other traffic by default.
- **Verification Test:** Attempted to connect via **RDP (Remote Desktop Protocol)**. The connection failed as expected, confirming that the Security Group correctly filtered out unauthorized protocols and that the Linux instance does not expose a GUI by default.

### 2. Identity & Access Management (IAM)
Instead of hardcoding AWS credentials (access keys) into the instance, I used an **IAM Role** for secure access.
- **Role Name:** `admin_prac8`
- **Policy Attached:** `AmazonS3FullAccess`
- **Use Case:** This allows the EC2 instance to safely upload/download files from S3 buckets without storing sensitive API keys on the server.

## ✅ Key Takeaways
- **Security Groups** act as a stateful firewall at the instance level.
- **IAM Roles** are the industry standard for granting permissions to AWS resources (like EC2) securely.
