## Why Version Control?

Whether you're working solo, with a team, or across multiple teams, version control is essential because it's the **integration point** for everything you do.

* Even if you're working alone, version control:

  * Gives you a **single place to store your code**
  * **Protects you from mistakes**
* Working with others makes version control even more critical:

  * You're constantly **bringing code together**
  * There will be **conflicts** sometimes

Version control provides:

* Tools for **code integration**
* Features for **tracking changes** and **comparing history**

---

## Types of Version Control in Azure DevOps

There are **two types of version control systems** available in Azure DevOps:

### 1. **Team Foundation Version Control (TFVC)**

* **Centralized version control system**
* Created by **Microsoft**
* Available since **TFS 2005**

### 2. **Git**

* **Distributed version control system**
* Created by **Linus Torvalds**
* Initial release: **April 2005**
* **Supported in TFS/Azure DevOps since 2013**

---

## Centralized vs Distributed Version Control

### Centralized (TFVC)

* Requires a **network connection** for most operations:

  * Add
  * Edit
  * Delete
  * Check-in/Check-out
  * Branch
  * Merge
* The **central server tracks** what’s on your machine
* **Local workspaces** in TFVC offer limited offline capabilities:

  * You can undo a checkout
  * Still requires some communication with the server

### Distributed (Git)

* **No network connection needed** for most operations:

  * Add
  * Edit
  * Delete
  * Check-in
  * Branch
  * Merge
  * Undo
* You have a **complete copy of the repo locally**
* You can:

  * Revert to any version (even from 2 years ago) **offline**
* The central server **doesn't know what you have** until you **push** your changes

---

## Key Differences

| Feature                 | TFVC (Centralized)         | Git (Distributed)            |
| ----------------------- | -------------------------- | ---------------------------- |
| **Network Dependency**  | Needed for most operations | Needed only to share changes |
| **Offline Work**        | Very limited               | Fully offline                |
| **History & Reversion** | Server-based               | Local full history           |
| **Syncing Changes**     | Continuous communication   | Batch via `push`             |