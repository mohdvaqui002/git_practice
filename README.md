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
Git & GitHub Branching Workflow
-This repository demonstrates a standard Git branching strategy, including branch creation, file management, and remote synchronization.                            🚀 Workflow Tasks Initialize a local working directory with Develop, F1, and f2 branches.Commit core files to specific branches.Push all local branches to the remote GitHub repository.Perform cleanup by deleting branches locally and remotely.
💻 Commands Execution1. Initialization & Master BranchSetup the repository and commit the primary configuration file.Bashgit init
touch main.txt
git add main.txt
git commit -m "docs: add main.txt to master"
2. Branch ArchitectureCreate the environment and feature branches.Bashgit branch Develop
git branch F1
git branch f2
3. File DistributionSwitch to each branch to add their respective files.Develop BranchBashgit checkout Develop
touch develop.txt
git add develop.txt && git commit -m "feat: add develop.txt"
Feature Branches (F1 & f2)Bashgit checkout F1
touch f1.txt
git add f1.txt && git commit -m "feat: add f1.txt"

git checkout f2
touch f2.txt
git add f2.txt && git commit -m "feat: add f2.txt"
4. GitHub SynchronizationLink the local repository to GitHub and push all branches at once.Bash# Replace <URL> with your specific GitHub Repository URL
git remote add origin <URL>
git push origin --all
5. Repository CleanupRemove the f2 feature branch from both local and remote environments.Bash# Return to master before deletion
git checkout master

# Delete locally
git branch -d f2

# Delete from GitHub
git push origin --delete f2
🛠 Summary TableBranchFile IncludedStatusmastermain.txtActiveDevelopdevelop.txtActiveF1f1.txtActivef2f2.txtDeleted⚠️ A Note on PrecisionCase Sensitivity: Git is case-sensitive. Notice that Develop and F1 start with capitals while f2 is lowercase. Follow this exactly to avoid "branch not found" errors.Active Branch: You cannot delete f2 while you are standing on it. Always checkout master first.
