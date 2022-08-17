# Git-Guide
Some GIT useful commands

# Git init
- git init   --> Initializes Git repository in the directory

- git status  --> shows the status of the repository (checks if any changes has been changed in the repository (untracked files)

- git add filename.format  --> adds the new file to de repository (moving the files to the 'stage')
- git add -A  --> adding all the files in the repository 
if there are files that star with the same name like 'page1.html', 'page2.html', 'page3.html'
we can add it like this: git add page*

- git commit -m 'message' --> commits the added file
if you get stuck in git bash message environment write ':wq' and press 'Enter'

- git log  --> shows the commits 

In git, HEAD shows the last commit:
      git diff --> shows the difference between currnt (+++b) and old files (---a) and the location of HEAD 
                   @@ line number @@
                   ---a/filename.format is the old version (red)
                   +++b/filename.format is the latest version (green)
      
      1- git diff --staged --> shows rthe modifications in the stage level (before commiting) (it shows what is happening in the staging level).
      # git reset filename.format --> removing 'filename.format' from the file in staging level.
      2- git restore --staged filename.format  --> unstaging.
      3- git checkout -- filename.format --> in case you make a mess in the code and want to get back to your previous version.
                                          returning the reset file to its previous state.
 
# Branches 
- git branch --> shows all the branches and the branch you're in now

- git branch BranchName  --> creates a new branch

- git checkout BranchName --> switches to the BranchName

- git merge BranchName  --> adds the changes and modification to the master branch

To merge a branch with master:
      1- switch to the master branch
      2- use 'merge':  git merge BranchName
      
- git rm filename.format  --> removes a file from git system

- git branch -d BranchName  --> removes the branch (BranchName) 


# GitHub
- git clone https://github.com/abbasizadeh/Git.git  --> downloads a repo from github into your local computer

What is origin: The file that is cloned or download from a site like github is called origin,
        So if you make a change in the downloaded file and write 'git status command' you will receive 
        this message: Your branch is ahead of 'origin/main' by 1 commit.
 
- git push origin master/main  --> pushes master (local) into origin (github.com)

- git pull origin master/main  --> downloads from origin (github.com) into the master (local).

# Conflict 
When a part of a file is chaged/modified by two poeple at a same time, git cannot execute the push/pull comands, this is called conflict.

- git remote add origin https://github.com/abbasizadeh/Git.git  --> adds remote dirctory to the repository address with the name of origin.

- git remote  --> shows the remotes
- git remote -v  --> shows the remotes with more explanations 
- git push -u origin master  --> send the origin (remote) to the master branch
- 


















