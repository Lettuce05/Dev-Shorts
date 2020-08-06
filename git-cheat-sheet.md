# Git Cheat Sheet

**Create a new repository from current directory**

    git init

<br> </br>
**Show files in staging area**

    git status

<br> </br>
**Add a file to staging area**

    git add <fileName>

<br> </br>
**Add all files in current directory to staging area**

    git add .

<br> </br>
**Commit changes to repository and add commit message**

    git commit -m "Git commit message"

<br> </br>
**Show all previous commits**

    git log

<br> </br>
**Roll back to previously committed version**

    git checkout <fileName>

<br> </br>
**Show the difference between current file and previously committed version**

    git diff <fileName>

<br> </br>
**Remove all files currently in staging area**

    git rm --cached -r .

<br> </br>
**Add any files that you want git to ignore and not to add, inside of the git ignore file (This is not a command)**

    .gitignore

<br> </br>
**Clone a git repository to current directory**

    git clone <url>

<br> </br>
**Show all branches**

    git branch

<br> </br>
**Create a new branch**

    git branch <newBranchName>

<br> </br>
**Change current working branch**

    git checkout <branchName>

<br> </br>
**Merge specified branch to master(if command is run from master)**

    git merge <branchName>
