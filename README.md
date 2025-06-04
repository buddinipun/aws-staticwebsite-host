# 🚀 Deploying a Static React Website to AWS Amplify

This guide walks through the steps I followed to build and deploy a static React application using **AWS Amplify** and **GitHub**. It showcases how to configure AWS for local development, initialize your React project, and deploy it using Amplify’s CI/CD integration.

---

## 📌 Prerequisites

- ✅ AWS Account
- ✅ GitHub Account
- ✅ Node.js + npm
- ✅ AWS CLI installed locally
- ✅ IAM Identity Center (SSO) configured in AWS
- ✅ React project initialized (e.g., with Vite or Create React App)

---

## 🛠️ Step 1: Set Up AWS for Local Development

### 🔐 Create IAM Identity Center (SSO) User for Amplify
1. Go to the [IAM Identity Center console](https://console.aws.amazon.com/singlesignon/home).
2. Choose **Enable with AWS Organizations** → click **Continue**.
3. Add a new user (e.g., `amplify_admin`) with Amplify permissions.
4. Set up a password:
   - Go to **Users > amplify_admin > Reset password**
   - Choose **Send email** to get password setup instructions

---

### ⚙️ Configure AWS CLI Profile Using SSO
1. Install AWS CLI: [Install Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
2. Run the following command to set up the local profile:

   ```bash
   aws configure sso


🧪** Step 2: Create & Run the React App**

npm create vite@latest staticwebsite -- --template react
cd staticwebsite
npm install
npm run dev


📂****** Step 3: Initialize GitHub Repository******

git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:<your-username>/staticwebsite.git
git branch -M main
git push -u origin main


🌐 **Step 4: Deploy to AWS Amplify**
Go to the AWS Amplify Console.

Click Create App > Host Web App.

Select GitHub as your repo source, and connect your GitHub account.

Choose the repository and branch you pushed (e.g., main).

Review and accept the default build settings.

Click Save and Deploy.

Once the build completes, click Visit deployed URL to view your live website!


✅ Deployment Complete!
Your static React application is now live and globally distributed via AWS Amplify's CDN. You can update your app by simply pushing new code to GitHub—Amplify handles automatic deployments!

📎 Resources
AWS Amplify Docs

Vite (React Template)

AWS CLI SSO Setup

# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

