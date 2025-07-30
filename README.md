
# Three-Tier Application Infrastructure using Terraform (AWS)

This project sets up a full three-tier architecture on AWS using Terraform — including VPC, subnets, security groups, EC2 instances, ALB, and RDS (MySQL).

---

## 📁 Project Structure

```
Three-Tier-Application/
│
├── main.tf
├── vpc.tf
├── subnet.tf
├── ec2.tf
├── alb.tf
├── rds.tf
├── variables.tf
├── outputs.tf
└── README.md
```

---

## ✅ Prerequisites

Ensure you have the following installed on your system:

- [Terraform](https://developer.hashicorp.com/terraform/install)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- [Git](https://git-scm.com/downloads)
- An existing AWS EC2 Key Pair

---

## 📂 Git Clone

First, clone the repository:

```bash
git clone https://github.com/devops/Three-Tier-Application.git
cd Three-Tier-Application
```

---

## 🔐 Key Pair Setup

This project expects a key pair named `tests`. Either:

1. **Create a new key pair in AWS named `tests`**, or  
2. **Edit the code** to use your existing key pair:

> In your Terraform files (e.g., `ec2.tf`), find and replace:

```hcl
key_name = "tests"
```

with

```hcl
key_name = "your-key-name"
```

To locate all such occurrences in PowerShell:

```powershell
Get-ChildItem -Recurse -Include *.tf | Select-String -Pattern 'key_name'
```

---

## 🚀 Terraform Workflow

### 1. Initialize Terraform

```bash
terraform init
```

### 2. Validate Configuration

```bash
terraform validate
```

### 3. Plan Infrastructure Changes

```bash
terraform plan
```

### 4. Apply the Configuration

```bash
terraform apply
```

Confirm with `yes` when prompted.

---

## 📦 Output

After successful deployment, Terraform will display:

- The DNS name of the Application Load Balancer (ALB)
- Your deployed resources on AWS

---

## 🧹 Cleanup

To destroy all resources created by Terraform:

terraform destroy

