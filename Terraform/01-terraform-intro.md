# 🚀 Terraform & Infrastructure as Code (IaC)

> Learn the fundamentals of **Terraform** and **Infrastructure as Code (IaC)**—the modern approach to provisioning and managing cloud infrastructure efficiently and consistently.

---

# 📚 Table of Contents

- [What is Terraform?](#-what-is-terraform)
- [What is Infrastructure as Code (IaC)?](#-what-is-infrastructure-as-code-iac)
- [Why Use IaC?](#-why-use-iac)
- [Problems Solved by IaC](#-problems-solved-by-iac)
- [Terraform vs Other IaC Tools](#-terraform-vs-other-iac-tools)
- [Terraform Core Concepts](#-terraform-core-concepts)
- [Installing Terraform](#-installing-terraform)
- [Configure AWS CLI](#-configure-aws-cli)
- [Basic Terraform Configuration](#-basic-terraform-configuration)
- [Terraform Workflow](#-terraform-workflow)
- [Common Terraform Commands](#-common-terraform-commands)
- [Terraform State File](#-terraform-state-file)
- [Understanding Terraform Plan Symbols](#-understanding-terraform-plan-symbols)
- [Best Practices](#-best-practices)
- [Key Takeaways](#-key-takeaways)

---

# 🌍 What is Terraform?

**Terraform** is an **Infrastructure as Code (IaC)** tool developed by **HashiCorp** that allows you to create, update, and manage cloud infrastructure using code.

Instead of manually creating resources from a cloud console, Terraform automates the entire infrastructure provisioning process.

### Terraform can manage resources on:

- AWS
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud
- VMware
- Kubernetes
- GitHub
- Cloudflare
- And hundreds of other providers

---

# ☁️ What is Infrastructure as Code (IaC)?

Infrastructure as Code (IaC) is the practice of defining and managing infrastructure using configuration files instead of manually creating resources through a web console.

Infrastructure includes:

- Servers
- Virtual Machines
- Networks
- Databases
- Load Balancers
- Storage
- IAM Users & Roles
- DNS Records
- Kubernetes Clusters

### Traditional Method

```
Login → AWS Console → Click → Create → Configure
```

### Infrastructure as Code

```
Write Code → Run Terraform → Infrastructure Created
```

---

# ✅ Why Use IaC?

Infrastructure as Code offers several advantages over manual cloud provisioning.

- Automates infrastructure creation
- Reduces deployment time
- Makes infrastructure reproducible
- Keeps environments consistent
- Reduces human error
- Enables version control with Git
- Improves team collaboration

---

# ❌ Problems Solved by IaC

| Manual Cloud Management | Terraform (IaC) |
|--------------------------|-----------------|
| Repetitive clicking | Fully automated |
| Human errors | Consistent deployments |
| Difficult to reproduce | Easily reproducible |
| No version history | Git version control |
| Slow deployments | Fast deployments |
| Hard to scale | Easily scalable |

---

# ⚖️ Terraform vs Other IaC Tools

| Tool | Language | Cloud Support | Best For |
|------|----------|---------------|-----------|
| Terraform | HCL | Multi-Cloud | Infrastructure Provisioning |
| AWS CloudFormation | JSON / YAML | AWS Only | AWS Infrastructure |
| Pulumi | Python, Go, JavaScript, TypeScript, C# | Multi-Cloud | Developers |
| Ansible | YAML | Multi-Cloud | Configuration Management |

---

# 🧠 Terraform Core Concepts

## 1️⃣ Declarative

Terraform uses a **declarative approach**.

You describe **what** infrastructure you want, and Terraform figures out **how** to create it.

Example:

> "Create one EC2 instance."

Terraform automatically determines the required steps.

---

## 2️⃣ Cloud Agnostic

Terraform uses the same workflow for different cloud providers.

Example:

```
AWS
Azure
Google Cloud
Oracle Cloud
```

Only the provider changes.

---

## 3️⃣ Providers

Providers allow Terraform to communicate with cloud platforms.

Examples:

- AWS Provider
- Azure Provider
- Google Provider
- Kubernetes Provider
- GitHub Provider

---

## 4️⃣ Resources

Resources represent the actual cloud infrastructure.

Examples:

- EC2 Instance
- S3 Bucket
- VPC
- IAM User
- Security Group

---

# 💻 Installing Terraform

## Ubuntu

```bash
wget -O - https://apt.releases.hashicorp.com/gpg | \
sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update
sudo apt install terraform
```

---

## macOS

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

---

## Windows (Chocolatey)

```powershell
choco install terraform
```

---

## Verify Installation

```bash
terraform -version
```

Example Output

```
Terraform v1.x.x
```

---

# 🔑 Configure AWS CLI

Terraform uses AWS credentials to create cloud resources.

Configure AWS CLI:

```bash
aws configure
```

Provide:

```
AWS Access Key ID
AWS Secret Access Key
Default Region
Output Format
```

Verify credentials:

```bash
aws sts get-caller-identity
```

---

# 📄 Basic Terraform Configuration

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "demo_bucket" {
  bucket = "my-demo-bucket-2026"
}
```

---

# 🔄 Terraform Workflow

```
                Write Configuration
                       │
                       ▼
              terraform init
                       │
                       ▼
              terraform validate
                       │
                       ▼
               terraform plan
                       │
                       ▼
              terraform apply
                       │
                       ▼
          Infrastructure Created
                       │
                       ▼
             terraform destroy
```

---

# ⚡ Common Terraform Commands

| Command | Description |
|----------|-------------|
| `terraform init` | Initialize Terraform project |
| `terraform validate` | Validate configuration syntax |
| `terraform fmt` | Format Terraform files |
| `terraform plan` | Preview infrastructure changes |
| `terraform apply` | Create or update infrastructure |
| `terraform destroy` | Delete infrastructure |
| `terraform show` | Display current state |
| `terraform output` | Display output values |
| `terraform state list` | List managed resources |
| `terraform state show` | Display resource details |

---

# 📂 Terraform State File

Terraform stores infrastructure information in:

```text
terraform.tfstate
```

The state file contains:

- Resource IDs
- Current infrastructure details
- Dependencies
- Metadata
- Resource mapping

### Why is it Important?

- Tracks deployed resources
- Prevents duplicate creation
- Detects infrastructure drift
- Calculates future changes

---

# ⚠️ Never Do These

- ❌ Edit `terraform.tfstate` manually
- ❌ Commit state files to GitHub
- ❌ Share state files publicly
- ❌ Delete state files accidentally

---

# 🔍 Understanding Terraform Plan Symbols

| Symbol | Meaning |
|---------|----------|
| `+` | Resource will be created |
| `-` | Resource will be destroyed |
| `~` | Resource will be updated |
| `-/+` | Resource will be replaced |

Example:

```
~ aws_instance.web

Name:
Old → WebServer
New → ProductionServer
```

Terraform updates the existing resource without recreating it.

---

# ⭐ Best Practices

- Use Git for version control.
- Run `terraform fmt` before committing code.
- Always execute `terraform plan` before `terraform apply`.
- Store sensitive values using variables or secrets.
- Use remote backends (S3 + DynamoDB) for team collaboration.
- Keep Terraform code modular.
- Never hardcode credentials.
- Use meaningful resource names.
- Add comments where necessary.
- Keep one responsibility per module.

---

# 📝 Key Takeaways

After completing this topic, you should understand:

- ✅ What Terraform is
- ✅ What Infrastructure as Code (IaC) means
- ✅ Benefits of IaC
- ✅ Terraform architecture
- ✅ Providers and Resources
- ✅ Terraform workflow
- ✅ Basic configuration
- ✅ Common Terraform commands
- ✅ Terraform state file
- ✅ Terraform best practices

---

# 📖 Next Topic

➡️ **02 - Terraform Installation & Setup**
