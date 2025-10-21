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


# Git Demo (Part 2 of 4): Connect Visual Studio to a Git Repository in Azure DevOps

In this part of the demo, we’ll:

* Connect **Visual Studio** to the Git repo we created in **Part 1**
* Clone the repository to our local machine
* Add a new console app
* Commit changes locally
* Review the commit locally (but not push yet!)

---

## 🔗 Step 1: Clone the Git Repository

1. Go to your Azure DevOps organization:

   ```
   https://dev.azure.com/{your-org}
   ```

   Example:

   ```
   https://dev.azure.com/benday-ps
   ```

2. Open the project you created in Part 1 (`git-demo`), then:

   * Navigate to **Repos** (left-hand menu)
   * Click **Clone** (upper right corner)

3. In the Clone window:

   * Choose **Visual Studio** as the cloning option
   * (Alternatively, copy the HTTPS URL for use in command line)

4. Visual Studio will open a **Clone Repository** dialog:

   * Choose a local path where you want the repo stored
   * Click **Clone**

---

## 🧭 Step 2: Explore the Cloned Repo in Visual Studio

Once the repo is cloned:

* Visual Studio opens in **Folder View**
* You'll see `.gitignore` and `README.md` (created in Part 1)

### Optional: Switch to Team Explorer

* If **Team Explorer** is not open:

  * Go to `View > Team Explorer` or search for it in the top search bar
* Team Explorer allows you to interact with:

  * Azure DevOps
  * Git version control
  * Builds, work items, etc.

---

## 🛠️ Step 3: Create a Console App Inside the Repo

1. In **Team Explorer**, scroll to **Solutions** and click **New**.
2. Create a new **Console Application**.

   * Name it: `Benday.HelloWorld`
   * Click **Create**

---

## 📝 Step 4: Make a Change and Commit

1. Visual Studio shows new files in the **Solution Explorer**.
2. Optionally, remove or comment out `"Hello, World!"` for a change.
3. **Build** the solution to ensure everything compiles.
4. Go to **Team Explorer > Changes**:

   * You'll see all modified/added files
   * Add a commit message, e.g.,:

     ```
     Created hello world
     ```
   * Click **Commit All**

> ✅ You’ve now committed changes **locally**.
> They are NOT yet pushed to Azure DevOps.

---

## 🧪 Step 5: Verify Local Commit

1. In Team Explorer, click the commit ID (e.g., `#1a2b3c`).
2. You'll see:

   * Commit message
   * Files included in the commit
   * Commit timestamp

---

## 🖥️ Step 6: Check Azure DevOps (Remote Repo)

1. In Team Explorer, click **Home > Web Portal**.

2. Navigate to:

   * **Repos > Files**
   * Then go to **History**

3. What do you see?

   * Only the **initial commit**
   * ❌ Your local commit is **not there yet** — because it hasn't been **pushed** to the server.

---

## ⚠️ Important Concept: Local vs Remote

| Action     | Description                                 |
| ---------- | ------------------------------------------- |
| **Commit** | Saves changes **locally**                   |
| **Push**   | Uploads local commits to **Azure DevOps**   |
| **Pull**   | Downloads new changes from **Azure DevOps** |


# Git Demo (Part 3 of 4): Getting Latest from Azure DevOps

In this part, we'll:

* Simulate a **server-side change** using the Azure DevOps web interface
* Use **Fetch** and **Pull** from Visual Studio to bring those changes locally

---

## 📝 Step 1: Make a Change in Azure DevOps Web Interface

1. Go to your Azure DevOps project:

   ```
   https://dev.azure.com/{your-org}/{your-project}
   ```

2. Navigate to:

   * **Repos > Files**
   * Click on the `README.md` file

3. Click **Edit**, then make a change:

   ```md
   BLAH, BLAH, BLAH!
   ```

4. Scroll down and enter a commit message:

   ```
   Updated README.md to say blah blah blah
   ```

5. Click **Commit**.

### ✅ Result:

You now have a new commit on the server that **does not exist on your local machine yet**.

---

## 🧭 Step 2: Open Visual Studio and Sync

1. Open **Visual Studio** and navigate to:

   ```
   View > Team Explorer
   ```

2. In **Team Explorer**, click on **Sync**.

This view shows:

* **Outgoing Commits**: Commits on your machine not yet pushed
* **Incoming Commits**: Commits on the server not yet pulled down

---

## 🔄 Step 3: Fetch and Pull

### Option 1: One-click Sync (Not Recommended for Beginners)

* Clicking **Sync** does both pull & push in one step.
* Can be confusing if you’re worried about automatic merges.

### ✅ Recommended: Manual `Fetch` + `Pull`

1. Click **Fetch**:

   * This checks the server for new commits.
   * You'll see the server-side commit (e.g., “Updated README.md…”).

2. Optionally:

   * Right-click on the fetched commit → **View Commit Details** (to inspect the change)

3. Click **Pull**:

   * This downloads the commit from the server and merges it into your local repo.

---

## 🔍 Step 4: Verify the Changes Locally

1. Go to **Solution Explorer**
2. Switch to **Folder View** (if not already in that view)
3. Open `README.md`

You should now see:

```md
BLAH, BLAH, BLAH!
```

### ✅ Merge Successful!

* You’ve now pulled server-side changes into your local environment.
* Your local commits (e.g., `Created hello world`) still exist but are not yet pushed.

---

## 🧠 Key Concepts Recap

| Git Command | Purpose                                                                         |
| ----------- | ------------------------------------------------------------------------------- |
| **Fetch**   | Retrieves metadata about new commits from the server — *but doesn't merge them* |
| **Pull**    | Retrieves and **merges** new commits from the server                            |
| **Push**    | Sends your **local commits** to the remote repository                           |
| **Sync**    | Fetch + Pull + Push in one action                                               |

# 🧩 Git Demo (Part 4 of 4): Sharing Changes Back to Azure DevOps

In this final part of the Git demo, you'll learn how to:

* Fix a bug in code
* Associate your Git commit with a **work item**
* Push your changes to Azure DevOps
* View the **link between commits and work items**

---

## 🔧 Step 1: Create a Work Item in Azure DevOps

1. Go to your Azure DevOps project.
2. Navigate to **Boards > Work Items**.
3. Click **New Work Item** → choose **Issue** (or Bug, Task, etc.)
4. Fill in the details:

   * **Title**: `Hello world doesn't say hello world`
   * **Status**: Change to `Doing`
   * **Assigned To**: Yourself
5. Click **Save**

   > 🔢 Note the Work Item ID (e.g., `#1`) – you’ll use this to link your commit.

---

## 🖥 Step 2: Make Code Changes in Visual Studio

1. Open your project in **Visual Studio**
2. Locate the line:

   ```csharp
   // Console.WriteLine("Hello World");
   ```
3. Uncomment or fix it:

   ```csharp
   Console.WriteLine("Hello World");
   ```
4. **Build** the solution to confirm it compiles.

---

## 🔗 Step 3: Associate the Work Item with the Commit

There are two ways to link your code changes to the work item:

### ✅ Option 1: Use Team Explorer GUI

1. In **Team Explorer**, go to **Work Items**
2. Right-click the work item → **Relate to Changes**
3. Now, go to **Changes** – it should show the work item under **Related Work Items**

### 🧪 Option 2: Add Work Item ID in Commit Message

```bash
git commit -m "Fix the bug #1"
```

> Replace `#1` with your actual work item ID. This automatically links the commit during push.

---

## 💾 Step 4: Commit and Push Changes

### Option A: From Team Explorer (Manual)

1. In **Team Explorer > Changes**, enter a commit message:

   ```
   Fixed the bug
   ```

2. Click **Commit All** to save locally.

3. Go to **Sync**

   * Under **Outgoing Commits**, click **Push** to send the changes to Azure DevOps.

### Option B: Commit and Push in One Step

* Choose **Commit All and Push** from the Changes tab.

---

## 🧠 Step 5: Verify Commit in Azure DevOps

1. Go to **Repos > History**

   * You should see a new commit: `Fixed the bug`

2. Click on the commit

   * View code changes (diff)
   * Confirm that it's associated with Work Item `#1`

3. Go to **Boards > Work Items**

   * Open the work item
   * You'll now see a **linked commit**
   * Mark the issue as **Done** if completed

---

## 🧵 Recap

| Task                     | Git                   | Azure DevOps                   |
| ------------------------ | --------------------- | ------------------------------ |
| Create Work Item         | N/A                   | Boards                         |
| Modify Code              | ✅                     |                                |
| Link Commit to Work Item | `#1` in commit or GUI | Boards ↔ Repos                 |
| Commit & Push            | `Commit`, then `Push` | Shows up in History            |
| Track Work               |                       | Work Item shows commit history |








