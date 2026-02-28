# 🚀 Terraform AWS EC2 Deployment

This project demonstrates how to create an AWS EC2 instance using **Terraform (Infrastructure as Code)**.

Instead of creating resources manually in AWS Console, Terraform automates the entire setup.

---

## 📌 What This Project Creates

- ✅ EC2 Instance  
- ✅ Security Group (Ports 22, 80, 8080 open)  
- ✅ SSH Key Pair  
- ✅ Public IP Output  

---

## 🛠 Technologies Used

- Terraform
- AWS EC2
- AWS IAM
- AWS CLI
- Ubuntu/Linux
- SSH

---

## ⚙ Prerequisites

Before running this project, you need:

- AWS Account  
- IAM User with programmatic access  
- Terraform installed  
- AWS CLI installed  

---

## 🚀 How to Run This Project

### 1️⃣ Configure AWS


aws configure

Enter your:

Access Key

Secret Key

Region (example: ap-south-1)

Output format (json)

2️⃣ Initialize Terraform
terraform init
3️⃣ Preview Changes
terraform plan
4️⃣ Create Infrastructure
terraform apply

Type:

yes

After successful execution, Terraform will show:

instance_public_ip = xx.xx.xx.xx
🔐 Connect to EC2
ssh -i ~/.ssh/id_rsa ubuntu@PUBLIC_IP

Replace PUBLIC_IP with the IP shown after apply.

💸 Destroy Resources (Important)

To avoid AWS charges:

terraform destroy

Type:
yes

🎯 What You Learn

Infrastructure as Code (IaC)

AWS EC2 automation

Security group configuration

Terraform workflow (init → plan → apply → destroy)

👨‍💻 Author

Suman M
