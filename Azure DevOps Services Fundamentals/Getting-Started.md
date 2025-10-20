# 🚀 Getting Started with Azure DevOps

### A Beginner-Friendly Walkthrough

---

## 📚 Table of Contents

1. [Create Your First Project in Azure DevOps](#1-create-your-first-project-in-azure-devops)
2. [What Did You Actually Create?](#2-what-did-you-actually-create)
3. [Understanding the Azure DevOps Organization](#3-understanding-the-azure-devops-organization)
4. [How to Access Organization Settings](#4-how-to-access-organization-settings)
5. [Adding Users to Your Project](#5-adding-users-to-your-project)
6. [Checking If You're Using Azure Active Directory](#6-checking-if-youre-using-azure-active-directory)
7. [Demo: Add a Microsoft Account User](#7-demo-add-a-microsoft-account-user)

---

## 1. ✅ Create Your First Project in Azure DevOps

Before you can create a project in Azure DevOps, you’ll need a **Microsoft account (MSA)**. Most personal email accounts ending in `@outlook.com`, `@hotmail.com`, or `@live.com` are MSAs.

### 🔹 Step-by-Step:

1. **Create or verify a Microsoft Account:**

   * Go to 👉 [https://signup.live.com](https://signup.live.com) if you don’t have one.

2. **Go to Azure DevOps:**

   * Visit 👉 [https://dev.azure.com](https://dev.azure.com)

3. **Start Free:**

   * Click the **"Start free"** button
   * Sign in using your Microsoft Account

4. **Create Your Project:**

   * Enter a **Project Name** (e.g., `ps-azure-devops`)
   * Set **Visibility** to **Private**
   * Click **Create project**

5. **Explore the Project Dashboard:**

   * You’ll land on the **Summary** page
   * Use the sidebar to access:

     * **Boards** (project management)
     * **Repos** (version control)
     * **Pipelines** (CI/CD automation)
     * **Test Plans** (QA testing)
     * **Artifacts** (package management)
     * **Dashboards** and **Wiki**

---

## 2. 📦 What Did You Actually Create?

While you created a *project*, you also created several key components under the hood.

| Component                  | Description                                                       |
| -------------------------- | ----------------------------------------------------------------- |
| **Team Project**           | A container for code, tasks, builds, and other development assets |
| **Version Control (Repo)** | Git-based source control system                                   |
| **Boards**                 | Kanban and sprint tools for work item tracking                    |
| **Pipelines**              | For automating builds and deployments                             |
| **Test Plans**             | Tools for test case management                                    |
| **Wiki**                   | Markdown-powered documentation                                    |
| **Dashboards**             | Visual reporting and charts                                       |
| **Artifacts**              | Host private NuGet/npm packages, etc.                             |

---

## 3. 🏢 Understanding the Azure DevOps Organization

When you created your project, Azure DevOps also created an **organization**—a high-level container that holds your projects.

| Term               | Equivalent                                      |
| ------------------ | ----------------------------------------------- |
| **Organization**   | Azure DevOps tenant (formerly "Account")        |
| **Team Project**   | A development workspace within the organization |
| **TFS Comparison** | Organization = TPC (Team Project Collection)    |

You can have **multiple projects** under the same organization.

---

## 4. ⚙️ How to Access Organization Settings

There are two ways to access your Azure DevOps **Organization Settings**:

### ✅ Method 1: From Azure DevOps

1. Go to 👉 [https://dev.azure.com](https://dev.azure.com)
2. Open your **project**
3. **DO NOT** click "Project settings" (this is project-specific)
4. Instead, click the **organization name** at the top (e.g., `benday-ps`)
5. In the new view, click **"Organization settings"** (bottom-left)

### ✅ Method 2: From Azure Portal

1. Go to 👉 [https://portal.azure.com](https://portal.azure.com)
2. Search for **Azure DevOps Organizations**
3. Select your DevOps org and manage settings

---

## 5. 👥 Adding Users to Your Project

Azure DevOps supports **two types of user accounts**:

| Type                             | Description                                        |
| -------------------------------- | -------------------------------------------------- |
| **MSA (Microsoft Account)**      | Personal accounts like `@outlook.com`, `@live.com` |
| **AAD (Azure Active Directory)** | Enterprise/work accounts tied to a company domain  |

### Key Differences:

| Feature          | MSA                            | AAD                                 |
| ---------------- | ------------------------------ | ----------------------------------- |
| Ownership        | User owns their own account    | Organization owns the user identity |
| Setup Complexity | Simple                         | Requires Azure AD integration       |
| Use Case         | Small teams, personal projects | Enterprises, corporate control      |

---

## 6. 🔍 Checking If You're Using Azure Active Directory

To find out if your organization is connected to Azure AD:

1. Go to 👉 [https://dev.azure.com/your-org-name](https://dev.azure.com/your-org-name)
2. Click **Organization Settings**
3. Select **Azure Active Directory** from the side menu
4. If you see a **“Connect Directory”** button → you’re **not connected** to Azure AD

---

## 7. 🎬 Demo: Add a Microsoft Account User

Here’s how to add a user with a Microsoft Account (MSA) to your organization:

### 👣 Steps:

1. Navigate to **Organization Settings > Users**
2. Click **Add new users**
3. Enter the email (e.g., `benday@live.com`)
4. Set:

   * **Access Level**: Basic (free for up to 5 users)
   * **Project(s)**: Click into the box and select one or more projects
   * **Role**: Choose between Reader, Contributor, or Project Administrator
5. Check **Send email invitation**
6. Click **Add**

### 👥 As the Invited User:

1. Open the email invitation
2. Click **Join now**
3. Log in with your Microsoft Account
4. Access the project and view dashboards, code, etc.

After joining, go back to **Organization Settings > Users** to verify that:

* Their **last access time** is updated
* Their **access level** reflects any subscriptions (e.g., Visual Studio Enterprise)

---

