Step,Action,Command
1a 1,Create & Enter Project Folder -mkdir my-devops-project && cd my-devops-project
1a.2,Initialize Git Repository,git init
1b,Create Project Files,touch Code.txt Log.txt Output.txt
1c,Stage Specific Files,git add Code.txt Output.txt
1d,Commit Staged Changes,"git commit -m ""Initial commit of Code and Output files"""
1e.1,Link to Remote Repository,git remote add origin <your-github-repo-url>
1e.2,Push to GitHub (Main),git push -u origin main
------------------------------------------------------------------------------------------------------------------------------------------------------------------
Git handson: Branching and Stashing Workflow
This project demonstrates a technical Git workflow involving branch management, stashing untracked files, and cross-branch synchronization.

🚀 Tasks Performed
1. Initialization
Set up the local working directory and established the base state in the master branch.

Bash
git init
touch feature1.txt feature2.txt
git add .
git commit -m "Initial commit with feature files"
2. Branch Infrastructure
Created a multi-branch environment to isolate development and feature work.

Bash
git branch develop
git branch feature1
git branch feature2
3. Stash Management (Work-in-Progress)
Handled a "context switch" scenario by stashing untracked files in the develop branch before moving to a feature branch.

Bash
git checkout develop
touch develop.txt
# Using -u to include untracked files in the stash
git stash -u
4. Feature Development
Switched to the feature1 branch to perform independent updates.

Bash
git checkout feature1
touch new.txt
git add new.txt
git commit -m "Add new.txt to feature1"
5. Integration and Finalization
Returned to the develop branch to retrieve the stashed work and finalize the commit history.

Bash
git checkout develop
git stash pop
git add develop.txt
git commit -m "Commit develop.txt after unstashing"
🛠️ Commands Summary (For Submission)
The following sequence represents the complete command history used for this assignment:

git init

touch feature1.txt feature2.txt

git add .

git commit -m "Initial commit"

git branch develop

git branch feature1

git branch feature2

git checkout develop

touch develop.txt

git stash -u

git checkout feature1

touch new.txt

git add new.txt

git commit -m "Add new.txt"

git checkout develop

git stash pop

git add develop.txt

git commit -m "Add develop.txt"

📝 Logical Highlights
The Stash Strategy: Used git stash -u because develop.txt was a new, untracked file. Standard stashing would have ignored it.

Branch Isolation: Ensured feature1 and develop remained independent until the specific tasks required a switch.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Project Overview
Git & GitHub Branching Workflow
This project demonstrates basic Git operations including multi-branch management, file versioning, and remote synchronization with GitHub.

## Tasks Performed
1. Initialized a Git working directory.
2. Created branches: Develop, F1, and f2.
3. Committed main.txt to the master branch.
4. Committed branch-specific files: develop.txt, f1.txt, and f2.txt.
5. Pushed all branches to the remote GitHub repository.
6. Cleaned up by deleting the f2 branch locally and on GitHub.

---

## Execution Commands

### Step 1: Initial Setup
git init
touch main.txt
git add main.txt
git commit -m "Initial commit: add main.txt"

### Step 2: Branch Creation
git branch Develop
git branch F1
git branch f2

### Step 3: File Management per Branch
# Develop Branch
git checkout Develop
touch develop.txt
git add develop.txt
git commit -m "Add develop.txt to Develop branch"

# F1 Branch
git checkout F1
touch f1.txt
git add f1.txt
git commit -m "Add f1.txt to F1 branch"

# f2 Branch
git checkout f2
touch f2.txt
git add f2.txt
git commit -m "Add f2.txt to f2 branch"

### Step 4: GitHub Integration
# Note: Replace <URL> with your specific repository link
git remote add origin <URL>
git push origin --all

### Step 5: Branch Deletion
# Return to master to perform deletion
git checkout master
git branch -d f2
git push origin --delete f2

---

## Final Branch Structure
- master (main.txt)
- Develop (develop.txt)
- F1 (f1.txt)
- f2 (Deleted)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
  # Git Branching & Merging Assignment

This project demonstrates a standard DevOps workflow involving branch creation, feature isolation, and cross-branch synchronization.

## 🚀 Workflow Summary

| Step | Action | Description |
| :--- | :--- | :--- |
| **1** | Initialize | Setup master branch with `master.txt`. |
| **2** | Branching | Create `public1`, `public2`, and `private` environments. |
| **3** | Feature Work | Add content to `public1`. |
| **4** | Integration | Merge public features into `master`. |
| **5** | Updates | Modify `master.txt` in `private` and sync to all branches. |

---

## 🛠 Commands Executed

### 1. Initialization and Setup
```bash
git init
touch master.txt
git add master.txt
git commit -m "Step 1: Initialize master with master.txt"

git branch public1
git branch public2
git branch private

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

