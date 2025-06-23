# Github-Actions Take home Assignment
##  GitHub Actions CI/CD Pipeline

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
        └── cicd-pipeline.yml  
```

---

##  Project Learning Outcomes

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

##  GitHub Repository Secrets

Add these secrets under **GitHub > Settings > Actions > Secrets and variables > Repository secrets**:

| Secret Name     | Description                                     |
|------------------|-------------------------------------------------|
| `EC2_HOST`       |  43.205.99.236            |
| `EC2_USERNAME`   | `ec2-user`  |
| `EC2_SSH_KEY`    | The **entire content** of your `.pem` key file (confidential) |

---

# ✅ Steps to Implement CI/CD with GitHub Actions, Docker & EC2

---

## 1️⃣ Setup Node.js App

- Created `GITHUB-ACTION/` folder.
- Wrote a basic Express server in `app.js`.
- Initialized `package.json` and added `.gitignore`.

---

## 2️⃣ Dockerize the App

- Created a `Dockerfile` using `node:alpine`.
- Installed dependencies and exposed port `3000`.

---

## 3️⃣ Push to GitHub

- Pushed code to GitHub repo: `github_action-takehome`.

---

## 4️⃣ Setup GitHub Actions

- Added `.github/workflows/cicd-pipeline.yml`.
- Defined `build` (push to GHCR) and `deploy` (EC2 SSH) jobs.

---

## 5️⃣ Configure Secrets

Added in GitHub repo settings:

- `EC2_HOST` → EC2 IP (`43.205.99.236`)
- `EC2_USERNAME` → `ec2-user`
- `EC2_SSH_KEY` → Contents of `.pem` key

---

## 6️⃣ Launch EC2 Instance

- Launched **Amazon Linux 2023**, **t2.micro**.
- Opened ports `22` and `3000`.
- Installed Docker manually using `yum`.

---

## 7️⃣ Trigger CI/CD

- `git push` triggered GitHub Actions:
  - Built & pushed Docker image to GHCR.
  - Logged into EC2 and deployed the container.
  
---


## ✅ Fixes & Debugging

- Fixed missing `"start"` script in `package.json`.
- Used `:main` tag to pull latest Docker image.

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




