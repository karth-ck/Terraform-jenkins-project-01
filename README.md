# Terraform Jenkins Project

This project demonstrates how to automate Terraform deployment using Jenkins pipelines. It provisions infrastructure on AWS, deploys an EC2 instance, and hosts a simple HTML website. After deployment, the pipeline displays the public IP of the instance where the site is live.

---

## 🔧 Tech Stack

- **Terraform**
- **Jenkins**
- **AWS (EC2)**
- **GitHub**
- **HTML (for hosted webpage)**

---

## 📁 Project Structure

- `Jenkinsfile` – Automates the Terraform workflow using Jenkins pipeline.
- `main.tf` – Terraform configuration to provision AWS resources (e.g., EC2, Security Group).
- `variables.tf` – Stores Terraform variable definitions.
- `outputs.tf` – Defines output variables (like instance public IP).
- `index.html` – A simple webpage hosted on the EC2 instance.

---

## 🚀 Jenkins Pipeline Overview

The pipeline has the following stages:

1. **Checkout**  
   - Clones the `US-456` branch from the GitHub repo.

2. **Terraform Init**  
   - Initializes the Terraform working directory.

3. **Terraform Plan**  
   - Creates an execution plan (`tfplan`).

4. **Terraform Apply on Merge (main branch only)**  
   - Applies the plan only if the latest commit is a **merge commit** on the `main` branch.

5. **Show Instance IP**  
   - Displays the public IP of the EC2 instance after deployment.

---

## 🔐 Prerequisites

Ensure the following before running this project:

- Jenkins server set up with:
  - AWS credentials added (ID: `aws-creds`)
  - Git plugin
  - Terraform installed and added to Jenkins path
- GitHub access to the repository
- AWS account with EC2 provisioning permissions

---

## 🌐 Output

After a successful merge into `main` and pipeline run, you'll see this message in Jenkins logs:

