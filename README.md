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
