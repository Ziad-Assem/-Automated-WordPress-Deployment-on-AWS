
# 🚀 Automated WordPress Deployment on AWS

This project automates the deployment of a WordPress site on AWS using **Terraform**, **Ansible**, and **Jenkins**. It provisions infrastructure and installs all necessary components (Apache, PHP, WordPress, and MariaDB) across separate EC2 instances, following infrastructure-as-code and DevOps best practices.

![Ansible](https://img.shields.io/badge/Ansible-%231A1918.svg?style=for-the-badge&logo=ansible&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-%235835CC.svg?style=for-the-badge&logo=terraform&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white)

![Ansible-project](https://github.com/user-attachments/assets/fedd6659-6dfa-4012-b052-b5b4d75351e5)
---

## 🗂️ Project Structure

```
.
├── ansible/
│   ├── ansible.cfg
│   ├── roles/
│   │   ├── apache/
│   │   │   └── tasks/
│   │   ├── mariadb/
│   │   │   └── tasks/
│   │   └── php_wordpress/
│   │       └── tasks/
│   └── README.md
│
├── terraform/
│   ├── modules/
│   │   ├── alb/
│   │   ├── ec2/
│   │   ├── gateways/
│   │   ├── security_group/
│   │   ├── vpc/
│   │   └── vpc_peering/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│
├── Jenkinsfile
└── README.md
```

---

## 🧰 Tech Stack

- **Cloud Provider**: AWS  
- **Provisioning**: Terraform (modular structure)  
- **Configuration Management**: Ansible (with roles)  
- **CI/CD**: Jenkins  

---

## 📦 Features

- Modular and reusable Terraform code
- Ansible roles for:
  - `apache` — web server setup
  - `php_wordpress` — PHP & WordPress installation
  - `mariadb` — database server configuration
- Infrastructure:
  - Custom VPC and subnets
  - EC2 instances for web and DB
  - Security groups
  - (Optional) ALB, VPC peering, and internet gateways
- Jenkins pipeline to automate provisioning and configuration

---

## 🔧 Prerequisites

- AWS CLI configured
- SSH key pair for EC2 access
- Jenkins server with:
  - Terraform & Ansible installed
  - Required plugins: Git, Ansible, Terraform
- IAM user with necessary AWS permissions

---

## 🚀 How to Use

### 1. Clone the Repo

```bash
git clone https://github.com/Mohamed-Mahmoud98/Automated-WordPress-Deployment-on-AWS.git
cd Automated-WordPress-Deployment-on-AWS
```

### 2. Deploy Infrastructure with Terraform

```bash
cd terraform
terraform init
terraform apply
```

Terraform will:
- Create a VPC and subnets
- Launch EC2 instances for WordPress and MariaDB
- Configure security groups

### 3. Configure Servers with Ansible

Update your `inventory` file with the public IPs from Terraform outputs, then:

```bash
cd ../ansible
ansible-playbook -i inventory roles/apache/tasks/main.yml
ansible-playbook -i inventory roles/php_wordpress/tasks/main.yml
ansible-playbook -i inventory roles/mariadb/tasks/main.yml
```

### 4. Jenkins Pipeline (Optional but Recommended)

- Create a Jenkins pipeline and point it to the `Jenkinsfile`
- Trigger the pipeline to automate Terraform and Ansible runs
- Note: Make sure to replace any placeholder credentials (e.g., AWS access keys, SSH keys, GitHub tokens) in the Jenkinsfile or related configurations with your actual credentials.
- It is recommended to use Jenkins Credentials Manager to securely store and inject these values rather than hardcoding them.
---
## 🌐 Access Your WordPress Site

After successful deployment and configuration, navigate to the public IP of the WordPress EC2 instance in your browser to complete the WordPress setup.

---

## 🖥️ WordPress Interface
🔐 WordPress Login Page

![Login Page](https://github.com/user-attachments/assets/5c312343-cea8-4168-85fb-c42d5a07745c)

🏠 WordPress Main Page

![Main Page](https://github.com/user-attachments/assets/3b27ce7a-aa6c-4e00-bf6d-9877af8b184a)

---



## 👨‍💻 Authors

**Mohamed Mahmoud**

[![GitHub](https://img.shields.io/badge/GitHub-Ziad--Assem-blue)](https://github.com/Ziad-Assem)  
[![Email](https://img.shields.io/badge/Email-ziadassem3000%40gmail.com-red)](mailto:ziadassem3000@gmail.com)
---

