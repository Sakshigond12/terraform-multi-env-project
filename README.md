# Multi-Environment Infrastructure using Terraform Workspaces
---

# 📖Project Overview

This project implements a multi-environment infrastructure on AWS using Terraform Workspaces. It enables the management of Development, Staging, and Production environments from a single Terraform codebase while keeping each environment isolated.

The infrastructure is built using Terraform modules to provision AWS resources such as VPC, EC2 instances, and S3 buckets, following Infrastructure as Code (IaC) best practices.

---

# 🏗 Architecture Diagram

![Architecture Diagram](https://github.com/Sakshigond12/terraform-multi-env-project/blob/360ba9881950efc897bd32798d5355b813fc09b0/Img/Architecture-diagram.png)

---

# 📂Project Structure

```
terraform-multi-env-project
│             
├── main.tf                    
├── variables.tf               
├── terraform.tf                 
│
├── modules                    
│   │
│   ├── vpc
│   │   └── main.tf            
│   │
│   ├── ec2
│   │   └── main.tf          
│   │           
│   └── s3
│       └── main.tf            
│
├── environments               
│   │
│   ├── dev.tfvars             
│   ├── staging.tfvars         
│   └── prod.tfvars            
│
├── Img                         
│   ├── Architecture-diagram.png
│   ├── Modular-terraform-project.png
│   ├── dev-production-staging-environment.png
│   ├── multi-env-vpc.png
│   ├── multi-env-s3-bucket.png
│   └── workspace-setup.png
│
└── README.md                  

```

---

# 🧰Technologies Used

- Terraform
- Amazon Web Services (AWS)
- Terraform Workspaces
- Terraform Modules

---

# 🧭Terraform Workspace Strategy

Terraform Workspaces allow multiple infrastructure environments to be managed using the same Terraform configuration.
Each workspace maintains a separate state file.

### Create Workspaces

```
terraform workspace new dev
terraform workspace new staging
terraform workspace new prod
```

### List Workspaces

```
terraform workspace list
```

### Switch Workspace

```
terraform workspace select dev
terraform workspace select staging
terraform workspace select prod
```

This ensures that:

- Each environment is isolated
- Infrastructure state is separated
- Deployment becomes safer and easier

---

# ⚙Environment Configuration

Each environment uses a separate variable file (.tfvars).

### Development Environment

```
instance_type = "t2.micro"
bucket_name   = "app-storage-dev"
environment   = "dev"
```

### Staging Environment

```
instance_type = "t2.small"
bucket_name   = "app-storage-staging"
environment   = "staging"
```

### Production Environment

```
instance_type = "t2.large"
bucket_name   = "app-storage-prod"
environment   = "prod"
```
---

# 🚀Deployment Steps

### Step 1: Initialize Terraform

```
terraform init
```

---

### Step 2: Create Workspaces

```
terraform workspace new dev
terraform workspace new staging
terraform workspace new prod
```

---

### Step 3: Deploy Development Environment

```
terraform workspace select dev
terraform apply 
```

---

### Step 4: Deploy Staging Environment

```
terraform workspace select staging
terraform apply 
```

---

### Step 5: Deploy Production Environment

```
terraform workspace select prod
terraform apply 
```

---

# ✅Environment Validation

After deployment, verify resources from the AWS Console.

### Development Environment

- VPC successfully created
- EC2 instance running
- S3 bucket created

### Staging Environment

- Separate infrastructure resources created

### Production Environment

- Production resources protected using lifecycle rules

---

# 📸Project Outputs

### 1 Modular Terraform Project Structure
![Modular Terraform](https://github.com/Sakshigond12/terraform-multi-env-project/blob/360ba9881950efc897bd32798d5355b813fc09b0/Img/Modular-terraform-code.png)

### 2 Development, Staging and Production Environment Setup
![Environment Setup](https://github.com/Sakshigond12/terraform-multi-env-project/blob/e3544b62e5dc70661ffd29978cfc9635628ec837/Img/dev-staging-production-env.png)

### 3 Multi Environment VPC Setup
![VPC Setup](https://github.com/Sakshigond12/terraform-multi-env-project/blob/360ba9881950efc897bd32798d5355b813fc09b0/Img/multi-env-vpc.png)

### 4 Multi Environment S3 Bucket
![S3 Bucket](https://github.com/Sakshigond12/terraform-multi-env-project/blob/main/Img/multi-env-s3-bucket.png?raw=true)

### 5 Terraform Workspace Setup
![Workspace Setup](https://github.com/Sakshigond12/terraform-multi-env-project/blob/main/Img/workspace-setup.png?raw=true)

---

## 📌 Conclusion

This project showcases how Terraform Workspaces can be used to manage multiple AWS environments from a single codebase. By implementing modular infrastructure and environment isolation, the project ensures scalable, organized, and reliable infrastructure management following modern DevOps best practices.

---
## 👩‍💻 Author

**Sakshi Gond**

Aspiring Cloud & DevOps Engineer  

🔗 GitHub: https://github.com/Sakshigond12

🔗 LinkedIn: https://linkedin.com/in/sakshi-gond-9ab9092a2
