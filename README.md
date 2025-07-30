
# Three-Tier Application Infrastructure using Terraform (AWS)

This project sets up a full three-tier architecture on AWS using Terraform — including VPC, subnets, security groups, EC2 instances, ALB, and RDS (MySQL).

---

## 📁 Project Structure

```
Three-Tier-Application/
│
├── alb.tf
├── data.sh
├── database_sg.tf
├── ec2.tf
├── igw.tf
├── outputs.tf
├── provider.tf
├── rds.tf
├── route_table.tf
├── subnet.tf
├── vars.tf
├── vpc.tf
├── web_sg.tf
```

| File              | Description |
|-------------------|-------------|
| `alb.tf`          | Defines the Application Load Balancer and target group configuration. |
| `data.sh`         | Startup script for EC2 instances. |
| `database_sg.tf`  | Security Group for the RDS database allowing only internal access. |
| `ec2.tf`          | Launch configuration for web and app EC2 instances. |
| `igw.tf`          | Configures the Internet Gateway to allow internet access to public subnets. |
| `outputs.tf`      | Outputs values like ALB DNS or RDS endpoint. |
| `provider.tf`     | Declares the AWS provider and region. |
| `rds.tf`          | Provisions the MySQL RDS instance and its subnet group. |
| `route_table.tf`  | Route tables for public/private subnet traffic flow. |
| `subnet.tf`       | Creates public and private subnets across multiple AZs. |
| `vars.tf`         | Variable definitions (e.g., AMI ID, key name, region). |
| `vpc.tf`          | Defines the VPC and associated settings (CIDR, DNS, etc.). |
| `web_sg.tf`       | Security Group for web and app servers, including ALB access. |

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

