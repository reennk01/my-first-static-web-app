# 🌐 my-first-static-web-app

## 🚀 Deploying a Static Website to Azure Using GitHub Actions

This project demonstrates how to deploy a static HTML website using Azure Static Web Apps and GitHub Actions. The process involves integrating your GitHub repository with Azure and setting up an automated CI/CD pipeline.

> 🔗 Based on [Microsoft Docs – Get Started with Azure Static Web Apps](https://learn.microsoft.com/en-us/azure/static-web-apps/get-started-portal?tabs=vanilla-javascript&pivots=github)

---

## ✅ Prerequisites

- A GitHub account with a repository containing:
  - `index.html` (main static page)
  - Optional: `README.md`
- An [Azure account](https://azure.microsoft.com/)

---

## 📝 Steps to Deploy

### 1. Create a GitHub Repository

- Go to [GitHub](https://github.com)
- Create a new repository (public or private)
- Add your `index.html` file to the **root** of the repo
- Commit and push the changes to the `main` branch:

```bash
git add index.html
git commit -m "Initial commit"
git push origin main
```

---

### 2. Create a Static Web App in Azure

- Go to the [Azure Portal](https://portal.azure.com)
- Search for **Static Web Apps**
- Click **Create**
- Fill out the form with:
  - **Subscription** and **Resource Group**
  - **Name**: (e.g., `my-first-static-web-app`)
  - **Hosting Plan**: Free
  - **Region**: Your nearest region
  - **Source**: GitHub
- Click **Sign in with GitHub** and authorize access
- Choose your repository and select the `main` branch
- Configure build settings:
  - **App location**: `/`
  - **API location**: *(leave blank)*
  - **Output location**: *(leave blank or `/`)*
- Click **Review + Create** → then **Create**

---

### 3. Azure Automatically Adds a GitHub Actions Workflow

After creating the Static Web App:
- Azure generates a workflow YAML file at:

  ```
  .github/workflows/azure-static-web-apps-<env>.yml
  ```

- This file contains the configuration to deploy your app on each push to the `main` branch.

---

### 4. Push Your Files and Trigger Deployment

Push your files (if not already pushed):

```bash
git add .
git commit -m "Add index.html for Azure deployment"
git push origin main
```

- This triggers the **GitHub Actions workflow** automatically.

---

### 5. Monitor Deployment Status

- Go to your repository on GitHub
- Click the **Actions** tab
- Look for **Azure Static Web Apps CI/CD**
- If successful, you'll see a green ✅

---

### 6. 🎉 Your Site Is Live!

After successful deployment:
- Azure assigns a free public URL like:

  ```
  https://<your-site-name>.azurestaticapps.net
  ```

- You can also view this in the Azure Portal under your Static Web App resource.



