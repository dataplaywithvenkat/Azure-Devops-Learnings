# Git Demo (Part 1 of 4): Initializing a Git Repository in Azure DevOps

In this part of the Git demo, we’ll walk through the **initial setup** process:

---

## 📋 Overview

### Demo Structure:

1. **Initialize a Git repository** (you are here ✅)
2. Use **Git + Visual Studio + Azure Repos web interface**
3. **Pull (Get Latest)** – sync changes from Azure DevOps to local
4. **Push** – send changes from local to Azure DevOps

---

## 🛠️ Step 1: Create a New Azure DevOps Project

1. Open your browser and go to your Azure DevOps organization URL:

   ```
   https://dev.azure.com/{your-org-name}
   ```

   Example:

   ```
   https://dev.azure.com/benday-ps
   ```

2. Click on **"Create project"** — available from:

   * The homepage
   * Or go to **Organization Settings > Projects > New team project**

3. Enter the **Project Name**:

   ```
   git-demo
   ```

4. Set the **Visibility**:

   * ✅ **Private** (recommended for internal work)
   * ❌ Public (for open-source/public access)

5. Click **Advanced** to view more options:

   * **Version Control**: Select `Git`
   * **Work Item Process Template**: Select `Basic`

     * Other options: Agile, Scrum, CMMI (not covered in this demo)

6. Click **Create**.

---

## 📁 Step 2: Set Up Git Repo and `.gitignore`

Once your project is created:

1. Navigate to the **Azure Repos** section on the left-hand menu.

   * You'll land in an **empty Git repository** that was auto-created.

2. Scroll down (important on smaller screens) to find:

   * Option to **add a README**
   * Option to **add a `.gitignore`**

3. Choose a `.gitignore` template:

   * For this demo: Select `Visual Studio`

4. Click **Initialize**.

---

## 📄 What’s in the `.gitignore` File?

The `.gitignore` file tells Git which files/folders **not to track**.
This helps keep your repository clean and avoids adding temporary or compiled files.

Example rules from the Visual Studio template:

```gitignore
# Ignore build results
[Bb]in/
[Oo]bj/
```

* This means Git will ignore any folder named `bin` or `obj` throughout your solution.
* These are **local-only** and **should not be committed** to source control.

---

## ✅ Summary of Part 1

You have now:

* Created a **new Azure DevOps project**
* Initialized a **Git repository**
* Added a **Visual Studio-specific `.gitignore`**

Your repo now includes:

* `.gitignore`
* `README.md` (optional)

