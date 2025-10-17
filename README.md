# Static Website Deployment to AWS EC2 with Nginx

This project demonstrates how to automatically deploy a static HTML file (`index.html`) to an **AWS EC2** instance running **Nginx**, using **GitHub Actions** for CI/CD.

---

## 🧑‍💻 Author

**Name:** Emeka Nwosa  
**Slack Username:** @emekaN

---

## 🌍 Live Server

**Public URL:** [http://3.25.146.150/](http://3.25.146.150/)

The website is served directly from the EC2 instance at `/var/www/html/index.html` using Nginx.

---

## ⚙️ Deployment Workflow

Each time you push to the `main` branch, GitHub Actions will:

1. Connect to your EC2 instance via SSH.
2. Copy your latest `index.html` from the repository.
3. Replace the existing Nginx web root file at `/var/www/html/index.html`.
4. Restart the Nginx service.

---

## 🛠️ GitHub Secrets Configuration

To allow GitHub Actions to access your EC2 instance securely, set the following secrets in  
**Settings → Secrets and variables → Actions → New repository secret:**

| Secret Name   | Description                               | Example                   |
| ------------- | ----------------------------------------- | ------------------------- |
| `EC2_HOST`    | The public IP or DNS of your EC2 instance | `3.25.146.150`            |
| `EC2_USER`    | SSH username for the instance             | `ec2-user` or `ubuntu`    |
| `EC2_SSH_KEY` | Private SSH key content                   | (Paste your PEM key here) |

---
