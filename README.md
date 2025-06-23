# 🚀 GitHub Actions CI/CD Pipeline

> A fully automated pipeline that builds, containers, and deploys a Node.js web app to an EC2 instance using GitHub Actions, Docker, and GitHub Container Registry (GHCR).

---

## 📁 Project Structure
```
GITHUB-ACTION/
├── app.js                    
├── package.json              
├── package-lock.json         
├── Dockerfile                 
├── .gitignore                
└── .github/
    └── workflows/
        └── cicd-pipeline.yml  GitHub Actions CI/CD workflow
```

---

## 🧠 Project Learning Outcomes

### 🔧 Concepts You’ll Master:

| Concept                     | Explanation                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **GitHub Actions**         | Automate your development workflow end-to-end                              |
| **Docker**                 | Package your app in a consistent, portable environment                     |
| **GitHub Container Registry (GHCR)** | Secure image hosting integrated with GitHub                        |
| **EC2 Deployment via SSH** | Real-world deployment pipeline to a Linux-based cloud server               |
| **Secrets Management**     | Securely pass credentials using GitHub Secrets                             |

---

## ☁️ EC2 Deployment Overview

| Configuration     | Value                        |
|-------------------|------------------------------|
| Instance Type     | t2.micro (Free Tier)         |
| OS                | Amazon Linux 2023            |
| User              | ec2-user                     |
| Open Ports        | 22 (SSH), 3000 (Web App)     |
| Docker Installed  | Manually using `yum`         |
---

## 🔐 GitHub Repository Secrets

Add these secrets under **GitHub > Settings > Actions > Secrets and variables > Repository secrets**:

| Secret Name     | Description                                     |
|------------------|-------------------------------------------------|
| `EC2_HOST`       | http://43.205.99.236/              |
| `EC2_USERNAME`   | `ec2-user`  |
| `EC2_SSH_KEY`    | The **entire content** of your `.pem` key file (confidential) |

---

### 📸 Screenshots

| Description                   | Preview |
|------------------------------|---------|
| EC2 Instance Launched        | ![EC2 Instance](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20174117.png?raw=true) |
| Security Group Configuration | ![Security Group](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20174217.png?raw=true) |
| SSH Access to EC2            | ![SSH Access](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20174024.png?raw=true) |
| Docker Installed Manually    | ![Docker Install](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20173958.png?raw=true) |
| GitHub Actions Workflow Run  | ![Workflows](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20180051.png?raw=true) |
| Application Live on EC2      | ![Live App](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20180027.png?raw=true) |

 ---

## 🌐 Access Your App

After successful deployment, visit your application in the browser using the EC2 public IP:

🔗 **[http://43.205.99.236:3000/](http://43.205.99.236:3000/)**

---

### 💼 Real-World Relevance

This is exactly how modern teams build, test, and deploy applications — automatically, reliably, and securely.

You're now ready to apply this knowledge to real-world projects or take your DevOps learning even further! 🚀

---

### 🧠 What You Learned

By completing this hands-on capstone assignment, you’ve learned how to:

- 🐳 **Containerize** and ship applications efficiently using Docker.
- ⚙️ **Automate builds and deployments** with GitHub Actions workflows.
- 🔐 **Manage secrets securely** within GitHub repositories.
- ☁️ **Use EC2 as a staging or production environment** for your applications.
- 🧪 Understand how modern **CI/CD pipelines** operate in professional DevOps environments.

---



