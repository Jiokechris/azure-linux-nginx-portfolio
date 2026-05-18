# Azure Linux VM Portfolio Deployment

## Project Overview

This project demonstrates the deployment of a cloud-hosted portfolio website using a Linux Virtual Machine on Microsoft Azure.

The project was built as part of my Cloud Engineering learning journey to gain practical experience with:

- Infrastructure as a Service (IaaS)
- Linux server administration
- SSH remote access
- Nginx web server deployment
- Cloud networking
- Public IP hosting

The website was deployed manually on a live Ubuntu Server virtual machine running in Azure cloud infrastructure.

---

# Technologies Used

- Microsoft Azure
- Ubuntu Server 24.04 LTS
- Nginx Web Server
- Linux CLI
- SSH
- HTML
- CSS
- GitHub

---

# Cloud Architecture

User → Internet → Azure Virtual Machine → Ubuntu Linux → Nginx → Portfolio Website

---

# Project Objectives

The main goal of this project was to:

- Deploy a Linux virtual machine in Azure
- Configure SSH access securely
- Install and manage Nginx
- Host a static portfolio website
- Understand Azure networking concepts
- Practice cloud infrastructure deployment manually

---

# Deployment Steps

## 1. Azure VM Creation

Created an Ubuntu Linux Virtual Machine in Microsoft Azure.

Configured:
- Resource Group
- Public IP
- Authentication using SSH key
- Network Security Group rules
- Port 22 (SSH)
- Port 80 (HTTP)

---

## 2. SSH Connection

Connected remotely into the Linux VM using SSH from PowerShell.

Example:

```bash
ssh -i chijiokeazure_key.pem azureuser@PUBLIC_IP
```

---

## 3. Linux Server Update

Updated the server packages:

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 4. Nginx Installation

Installed Nginx web server:

```bash
sudo apt install nginx -y
```

Started and enabled the service:

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

---

## 5. Website Deployment

Moved the portfolio HTML project into:

```bash
/var/www/html
```

Replaced the default Nginx landing page with custom portfolio code.

---

# Challenges Encountered

## 1. SSH Permission Denied Error

Issue:

```text
Permission denied (publickey)
```

Cause:
- Incorrect SSH username used initially

Fix:
- Verified correct Azure VM username
- Reconnected using:

```bash
ssh -i chijiokeazure_key.pem azureuser@PUBLIC_IP
```

---

## 2. Network Security Group Understanding

Challenge:
Understanding inbound rules and cloud firewall behavior.

Learned:
- Port 22 allows SSH access
- Port 80 allows web traffic
- Azure NSG controls inbound traffic

---

## 3. Character Encoding Issue

Issue:
HTML bullet symbols displayed as:

```text
â€¢
```

Fix:
- Replaced symbols with semantic HTML lists using:
```html
<ul>
<li></li>
</ul>
```

---

# Skills Demonstrated

- Cloud VM provisioning
- Linux server management
- SSH authentication
- Web server deployment
- Cloud networking basics
- Infrastructure troubleshooting
- Static website hosting

---

# Screenshots

## Azure VM Running

Add screenshot here:
```text
screenshots/azure-vm.png
```

---

## SSH Terminal Session

Add screenshot here:
```text
screenshots/ssh-terminal.png
```

---

## Live Website

Add screenshot here:
```text
screenshots/portfolio-site.png
```

---

# Future Improvements

- Add HTTPS using Certbot and SSL
- Configure custom domain
- Automate deployment with GitHub Actions
- Containerize application using Docker
- Deploy using Kubernetes
- Add CI/CD pipeline

---

# Author

## Chijioke C Odoh

Cloud Engineering Learner focused on:
- AWS
- Azure
- Linux
- DevOps
- Infrastructure Automation

GitHub:
https://github.com/Jiokechris

LinkedIn:
https://www.linkedin.com/in/chijioke-odoh-a263001bb/