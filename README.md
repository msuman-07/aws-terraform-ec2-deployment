# 🚀 Terraform AWS EC2 Deployment (Infrastructure as Code)

This project demonstrates how to provision AWS infrastructure using **Terraform**.  
It creates an EC2 instance automatically with:

- SSH access
- HTTP access
- Jenkins port access (8080)
- Security group configuration
- Key pair authentication
- Public IP output

This project follows **Infrastructure as Code (IaC)** principles used in real-world DevOps environments.

---

# 📌 Project Overview

Terraform is used to automate AWS resource creation instead of manually configuring infrastructure in the AWS Console.

This project provisions:

✅ AWS EC2 instance  
✅ AWS Security Group  
✅ AWS Key Pair  
✅ Public IP output  

---

# 🏗 Architecture


Terraform
↓
AWS Provider
↓
EC2 Instance + Security Group + Key Pair
↓
Public IP Output


---

# 🛠 Tools & Technologies Used

- **Terraform** → Infrastructure as Code tool
- **AWS EC2** → Virtual Server
- **AWS IAM** → Authentication & Authorization
- **AWS CLI** → AWS configuration
- **Ubuntu/Linux** → Operating system
- **SSH** → Secure server access

---

# ⚙ Prerequisites

Before running this project, install:

- Ubuntu/Linux system OR Killercoda Playground
- AWS Account
- Terraform
- AWS CLI
- IAM User with Administrator access

---

# 🚀 Setup Guide (Step-by-Step)

---

## ✅ Step 1 — Install Terraform

### Install dependencies

sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
Add Hashicorp GPG key
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
Add repository
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
Install Terraform
sudo apt update
sudo apt-get install terraform
Verify installation
terraform -version

✅ Step 2 — Install AWS CLI
sudo apt update
sudo apt-get install -y unzip curl
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

Verify:

aws --version
✅ Step 3 — Create AWS IAM User

Go to AWS Console → https://console.aws.amazon.com

Open IAM service

Create new user → terraform-user

Select Programmatic access

Attach policy → AdministratorAccess

Download Access Key & Secret Key

✅ Step 4 — Configure AWS CLI
aws configure

Enter:

Access Key → YOUR_ACCESS_KEY
Secret Key → YOUR_SECRET_KEY
Region → ap-south-1
Output → json

Test connection:

aws ec2 describe-regions
✅ Step 5 — Generate SSH Key
ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa -N ""

Get public key:

cat ~/.ssh/id_rsa.pub

Copy the output and paste it inside main.tf.

📁 Project Structure
terraform-aws-ec2/
│
├── main.tf
├── README.md
└── .gitignore
🧩 Terraform Configuration

This project creates:

AWS provider configuration

Key pair for SSH access

Security group allowing ports 22, 80, 8080

EC2 instance

Public IP output

▶ Running Terraform
Initialize Terraform
terraform init

Downloads required AWS provider.

Preview Infrastructure Changes
terraform plan

Shows what resources will be created.

Create Infrastructure
terraform apply

Type:

yes

After successful execution:

instance_public_ip = xx.xx.xx.xx
🔐 Connect to EC2 Instance
ssh -i ~/.ssh/id_rsa ubuntu@PUBLIC_IP

You are now connected to your server.

💸 Destroy Infrastructure (IMPORTANT)

To avoid AWS charges:

terraform destroy

Type:

yes

Always destroy resources after testing.

🔒 Security Best Practices

Never upload AWS credentials to GitHub

Never commit private SSH keys

Always use .gitignore

Destroy unused resources to avoid billing

🎯 Key Terraform Concepts
Concept	Description
Provider	Cloud platform connection
Resource	Infrastructure component
State	Tracks infrastructure
Plan	Preview changes
Apply	Create infrastructure
Destroy	Delete infrastructure

🌟 Learning Outcomes

After completing this project you will understand:

Infrastructure as Code (IaC)

AWS automation using Terraform

EC2 provisioning

Security group configuration

Cloud deployment workflow

DevOps infrastructure management

👨‍💻 Author

Suman M
