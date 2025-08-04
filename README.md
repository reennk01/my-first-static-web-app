# my-first-static-web-app

🚀 Deploying a Static Website to Azure Using GitHub Actions
This project demonstrates how to deploy a static HTML website using Azure Static Web Apps and GitHub Actions. The process involves integrating your GitHub repository with Azure and setting up an automated deployment pipeline.

🔗 Based on: Microsoft Docs – Get started with Azure Static Web Apps

✅ Prerequisites
A GitHub account with a repository containing:

index.html (your main static web page)

Optional: README.md

An Azure account

📝 Steps to Deploy
1. Create a GitHub Repository
Go to GitHub

Create a new repository (public or private)

Add your index.html file to the root of the repo

Commit and push the changes to the main branch

2. Create a Static Web App in Azure
Go to Azure Portal

Search for Static Web Apps in the search bar

Click Create

Fill out the required details:

Subscription and Resource Group

Name: (e.g. my-first-static-web-app)

Hosting plan: Free

Region: Your nearest region

Source: GitHub

Click Sign in with GitHub and authorize access

Choose your repository and the main branch

For build settings:

App location: /

API location: (leave blank)

Output location: (leave blank or / if unsure)

Click Review + Create → then Create

3. Azure Automatically Creates a GitHub Actions Workflow
Once the Static Web App is created:

Azure will automatically add a GitHub Actions YAML file to your repo at:
.github/workflows/azure-static-web-apps-<env>.yml

This file contains instructions to deploy your app whenever you push to the main branch.

4. Push Your Files and Trigger Deployment
   
git add .
git commit -m "Add index.html for Azure deployment"
git push origin main

This triggers the GitHub Actions workflow created by Azure.

6. View Deployment Status in GitHub
Go to your GitHub repo

Click the Actions tab

Look for Azure Static Web Apps CI/CD

You should see a green ✅ if successful

6. Your Site Is Live!
Once deployment is successful:

Azure assigns a free URL like:
https://<random-name>.azurestaticapps.net

You can view this URL from the Azure Portal under your Static Web App resource.
