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


# Git vs. Team Foundation Version Control (TFVC)

Now that you know Azure DevOps (VSTS) supports two types of version control systems — **Git** and **TFVC** — the big question is:

## Which One Should You Use?

### 👉 Short Answer:

There’s **no single right answer**. It depends on your **team’s needs**, **workflow**, and **project context**.

---

## ✅ Pros and ❌ Cons of TFVC

### ✅ Pros

* **Familiarity**: If you've used centralized version control before, TFVC will feel familiar.
* **Frequent server communication**: Makes tracking changes straightforward.
* **Granular security**:

  * Fine-grained control over who can do what at the folder or file level.
* **Handles large repositories well**:

  * Great for massive codebases with many binaries and components.
* **Mature tooling**:

  * In development since **TFS 2005**.
  * Battle-tested and stable.

### ❌ Cons

* **Declining popularity**:

  * TFVC is not widely adopted anymore.
  * Think of it as the *MySpace* or *Friendster* of version control.
* **Weak offline support**:

  * Hard to go back to TFVC once you've experienced Git’s offline capabilities.
* **Poor code review experience**:

  * The flow is clunky and not very usable.
* **Folder-based branching**:

  * Complex and confusing compared to Git's lightweight branching.

---

## ✅ Pros and ❌ Cons of Git

### ✅ Pros

* **Modern and popular**:

  * Actively used and loved in the dev community.
* **Excellent offline support**:

  * Full history and most features available **without a network**.
* **Easy branching**:

  * Intuitive and fast, compared to TFVC's folder-based branching.
* **Pull request-based code reviews**:

  * First-class support for peer reviews and collaboration.
* **Cross-platform & familiar**:

  * Works across OSes.
  * Skills from GitHub, GitLab, Bitbucket, etc., transfer directly.
* **Strong community & active development**:

  * Used by major teams like Microsoft’s own Windows team.
  * Microsoft is actively contributing to Git.

### ❌ Cons

* **Steep learning curve**:

  * Especially for teams coming from centralized systems like TFVC.
  * Easy to get confused and accidentally lose changes at first.
* **Simplified security model**:

  * Repository-level permissions (access is usually all or nothing).
* **Scalability issues with large repos**:

  * Historically not great with massive codebases.
  * Microsoft is working on this, and support is improving steadily.

---

## So... Git or TFVC?

### 🧠 It Depends:

* If you're working in a **legacy system** with a massive codebase, or need **advanced security**, **TFVC** might be a better fit.
* If you're **starting fresh**, want **modern workflows**, **great tooling**, and **offline support** — start with **Git**.

> 🔖 **Recommendation**:
> If you don’t have a strong reason to use TFVC, **start with Git**.

