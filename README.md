# aws-devops-projects
Hands-on AWS DevOps projects by Hardel Santos-Sanchez
# ELASTIC KUBERNETES SERVICES

A hands-on AWS DevOps project that demonstrates how to automatically deploy a simple web server on an EC2 instance using a user data script.

## 🧰 Tools & Services Used
- **Amazon EC2**
- **Amazon Linux AMI**
- **User Data (Bash Script)**
- **IAM (for instance access)**
- **Security Groups**
- **Web Server (Apache/HTTPD)**

## 🚀 Project Goal
To launch a virtual machine on AWS and have it automatically install and run a web server that serves a simple HTML page—without logging into the instance manually.

## 📐 Architecture Diagram


## 🛠️ Setup Instructions

1. **Launch EC2 Instance**
   - Use Amazon Linux 2023 AMI
   - Instance type: `t2.micro` (Free Tier)
   - Open ports 22 (SSH) and 80 (HTTP)

2. **Paste this in User Data field:**

   ```bash
   #!/bin/bash
   yum update -y
   yum install -y httpd
   echo "<h1>Hello from EC2!</h1>" > /var/www/html/index.html
   systemctl enable httpd
   systemctl start httpd
