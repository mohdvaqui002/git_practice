Step,Action,Command
1a 1,Create & Enter Project Folder -mkdir my-devops-project && cd my-devops-project
1a.2,Initialize Git Repository,git init
1b,Create Project Files,touch Code.txt Log.txt Output.txt
1c,Stage Specific Files,git add Code.txt Output.txt
1d,Commit Staged Changes,"git commit -m ""Initial commit of Code and Output files"""
1e.1,Link to Remote Repository,git remote add origin <your-github-repo-url>
1e.2,Push to GitHub (Main),git push -u origin main
