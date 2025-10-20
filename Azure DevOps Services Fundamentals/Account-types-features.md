Here's your comprehensive, **well-organized Azure DevOps guide** in **Markdown format**, complete with a **Table of Contents** and all the sections clearly structured.

---

# Azure DevOps: Account Types, Billing, and Permissions Guide

## Table of Contents

1. [Overview](#overview)
2. [User Account Types](#user-account-types)

   * [Stakeholder](#stakeholder)
   * [Basic](#basic)
   * [Visual Studio Subscriber](#visual-studio-subscriber)
3. [Pricing and Add-ons](#pricing-and-add-ons)

   * [Basic User Licensing](#basic-user-licensing)
   * [Test Manager](#test-manager)
   * [Visual Studio Pricing](#visual-studio-pricing)
4. [Billing Setup](#billing-setup)

   * [Attaching Azure Subscription](#attaching-azure-subscription)
   * [Linking to Azure Active Directory (AAD)](#linking-to-azure-active-directory-aad)
5. [User Management](#user-management)

   * [Adding AAD Users](#adding-aad-users)
   * [Adding AAD Guest Users](#adding-aad-guest-users)
6. [Assigning Licenses](#assigning-licenses)
7. [Permissions Management](#permissions-management)

   * [Org-Level Permissions](#org-level-permissions)
   * [Project-Level Permissions](#project-level-permissions)
   * [Team-Level Permissions](#team-level-permissions)
8. [Summary](#summary)

---

## Overview

Azure DevOps is a powerful platform for managing software development processes. It offers both **free and paid** options, making it accessible for individual developers and scalable for enterprises.

You may start for free and only pay when you need extra features, more users, or advanced QA tools. Understanding account types, billing, and permissions is crucial for effective usage.

---

## User Account Types

Azure DevOps provides different **user access levels**, each with specific features and limitations.

### Stakeholder

* **Free unlimited users**
* Primarily **read-only** access
* Can:

  * Create and edit work items (e.g., tasks, backlog items)
  * Approve releases
  * View dashboards
  * Subscribe to alerts
* Cannot:

  * Access code
  * Run builds or releases
  * Create dashboards
* Ideal for project sponsors, business stakeholders, or external reviewers.

### Basic

* **First 5 users are free**
* After that, **$6/user/month**
* Includes everything in Stakeholder, plus:

  * Full access to Azure Repos (unlimited private Git repos)
  * Boards, Pipelines, and Artifacts
* **Does not include** Test Manager (QA tools)

### Visual Studio Subscriber

* Must have an active Visual Studio subscription
* Includes all **Basic** features
* **Does not count against** the 5 free Basic users
* **Enterprise** level includes Test Manager at no extra cost

---

## Pricing and Add-ons

### Basic User Licensing

| Users | Cost          |
| ----- | ------------- |
| 1–5   | Free          |
| 6+    | $6/user/month |

Example:

* 6 users = $6/month
* 10 users = 5 free + 5 paid = $30/month

### Test Manager

* Required for QA testing features
* Add-on for **Basic** users
* **Cost:** $52/user/month

### Visual Studio Pricing (2021 Reference)

| Edition      | Monthly | Annual  |
| ------------ | ------- | ------- |
| Professional | $45     | $539    |
| Enterprise   | $250    | ~$2,999 |

---

## Billing Setup

To use paid features, you need to **connect Azure DevOps to an Azure subscription**.

### Attaching Azure Subscription

1. Go to **Organization Settings → Billing**
2. Click **Set up billing**
3. Select an existing Azure subscription or create a new one
4. Click **Save** to connect

Now your Azure DevOps org can be billed via the linked Azure subscription.

---

### Linking to Azure Active Directory (AAD)

1. In Organization Settings, go to **Azure Active Directory**
2. Click **Connect directory**
3. Select your AAD tenant and click **Connect**
4. Sign out and sign back in (initially use your Microsoft account)

This step enables enterprise-grade security and seamless user management.

---

## User Management

You can manage both **internal** and **external (guest)** users via Azure AD and Azure DevOps.

### Adding AAD Users

1. Go to **portal.azure.com → Azure Active Directory → Users**
2. Click **New user** and fill in the user details
3. Go to **Azure DevOps → Organization Settings → Users**
4. Click **Add users**, search for the new user, assign project access, and click **Add**

### Adding AAD Guest Users

**Option 1 (From Azure DevOps):**

1. Go to **Organization Settings → Users → Add users**
2. Enter external email (e.g., `user@externaldomain.com`)
3. Confirm the prompt for adding an external user
4. Assign project and click **Add**

**Option 2 (From Azure Portal):**

1. Go to **Azure AD → Users → New guest user**
2. Fill in name and email → Click **Invite**
3. Go back to **Azure DevOps → Add users**
4. Search for the user and add to the desired project

---

## Assigning Licenses

To modify or assign access levels:

1. Go to **Azure DevOps → Organization Settings → Users**
2. Right-click on the user → **Change access level**
3. Choose one of:

   * Stakeholder
   * Basic
   * Basic + Test Plans
   * Visual Studio Subscriber
4. Click **Save**

> ⚠️ Enabling **Test Plans** will **incur additional charges**. Azure DevOps does not provide a warning—be mindful!

---

## Permissions Management

### Pro Tip 💡

**Use groups to manage permissions.** It’s simpler, safer, and more scalable than assigning permissions individually.

### Org-Level Permissions

* **Project Collection Administrators**:

  * Full control over all projects
  * Can create/delete projects
  * Always have **at least two** members here

### Project-Level Permissions

Each project has:

* **Project Administrators**: Full control over the project
* **Contributors**: Create/edit/delete work items and code
* **Readers**: View-only access

### Team-Level Permissions

* Typically mirrors **Contributors**
* Avoid granular customizations at team level to reduce complexity

---

### Permissions Demo

1. **Org-level**: Go to **Organization Settings → Permissions**

   * Select **Project Collection Administrators → Members**
   * Add a backup admin
2. **Project-level**: Go to **Project Settings → Permissions**

   * Add/remove members to Project Admins or Contributors
3. **Team-level**: Manage team memberships (generally mirrors Contributors)

---

## Summary

Here's a recap of what we've covered:

* Azure DevOps offers **free and paid** plans based on account types
* **Account types**: Stakeholder (free), Basic (first 5 free), Visual Studio Subscriber
* **Add-ons** like **Test Manager** are available for QA workflows
* Set up **billing** by attaching an Azure subscription
* Connect **Azure Active Directory** for enterprise security
* Add both **internal and guest users**
* Assign access levels with care (Test Plans = extra cost)
* **Manage permissions using groups** at org, project, and team levels

