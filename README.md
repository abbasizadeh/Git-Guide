# Git-Guide
Some GIT useful commands

# Git init
- git help ... --> help
- git init   --> Initializes Git repository in the directory

- git status  --> shows the status of the repository (checks if any changes has been changed in the repository (untracked files)

- git add filename.format  --> adds the new file to de repository (moving the files to the 'stage')
- git add -A  --> adding all the files in the repository 
if there are files that star with the same name like 'page1.html', 'page2.html', 'page3.html'
we can add it like this: git add page*

- git commit -m 'message' --> commits the added file
- git show CommitCode  --> shows what happened in the commit
 
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
When a part of a remote file is chaged/modified by two poeple at a same time, git cannot execute the push/pull comands, this is called conflict.

- git remote add origin https://github.com/abbasizadeh/Git.git  --> adds remote dirctory to the repository address with the name of origin.

- git remote  --> shows the remotes
- git remote -v  --> shows the remotes with more explanations 
- git push -u origin master  --> send the origin (remote) to the master branch, -u keeps the address of origin and we dont need write "origin master" for the next pushes.

## Dealing with conflict
We cannot push the changes to github because someone esle has made a chenge in the same file same branch same line,
to be able to solve this we can follow the steps bellow:

           1- firt we can try to use "git pull". In this case git will try to auto merge the changes if it is possible. 
           2- if the conflict message appears, look at the git status to show where are you and what needs to be committed.
                              it probably shows " both modified: filename.format".
           3- if we open the file, it shows the location of HEAD as follow:
           <<<<<<< HEAD
            changes 
           =======
           >>>>>>> e964917e453f0d740e65c2597dbee05e024773c9
           from "<<<<< HEAD" to "=======" is our modifications, and from "=======" to ">>>>>>> commit name" is the other persons modifications.
           4- now we should commit the changes manually.
           5- after modifying the file we can add, commit and push it to the origin. 
           

         
# Tags
When we reach a certain level in our development (like a developing a software) when can tap it. Tags can be used as the name of the versions.
- git tag -a v3.7 -m "message"  --> tagged as version 3.7. 
- git tag  --> shows the version.

- git tag -a v1.8 CommitCode  --> write a commit message in a older versions.

- git tag -l "v*"  --> shows all the tags starts with v.

- git show v1.8  --> shows version 1.8.

if we want to push our tags on the origin:
- git push origin v1.8  --> adds v1.8 to the origin.
or
- git push origin --tags  --> adds all the tags to the origin.

- git checkout v1.8


# Signatures (GPG key)
Defining a pair of keys to sign your commits and changes. Then everyone can make sure that the commits are belong to you.
first we should install GPG and create a GPG key.

- git config  --global user.name
- git config --global user.signaturekey KeyCode
- gpg --list-secret-keys --keyid-format LONG --> list of your key
- git tag -s v2.1 -m "message"  --> tags with singing
- git show v2.1
- git tag -v v2.1  --> verifying the signature
- git commit -S -m "message"  --> signing a commit

# Debugging with github and gitlab

- git help blame
- git blame 
- git bisect start  --> start the binary search for finding the bug
- git bisect bad CommitCode  --> specifying a commit where something goes wrong
Then git starts seaching and brings us different commits and we should tell it if the commit is OK or doesnt work well as follows:
   git bisect good 
   git bisect good
   git bisect bad

# Gitlab
Unlike github, we can install gitlab and use it as a private repository.
You can contribute with other developer and do fork, merge request and so on.
