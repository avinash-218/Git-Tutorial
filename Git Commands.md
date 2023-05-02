# Git Tutorial
Reference : https://youtube.com/playlist?list=PL-osiE80TeTuRUfjRe54Eea17-YfnOOAx

## [Git Tutorial for Beginners: Command-Line Fundamentals](https://youtu.be/HVsySz-h9r4)

#### Version
- git --version : view git version

#### Config
- git config --global user.name "your_name" : set username
- git config --global user.email "your_email" : set email
- git config -- list : list all configuration

#### Help
- git help "verb" : help
- git "verb" --help : help

#### Initialize Existing Code
- git init

#### Remove Git Initialization
- rm -rf .git

#### Status
- git status

#### Git Ignore
- Add files to ignore tracking
- Can use wildcards also : *.py all python files

#### Staging Area
- git add "files" : add files to staging area
- git rm --cached "files" : remove files from staging area
- git reset "files" : remove files from staging area
- git reset : remove all modified files from staging area
- git add . : add all files to staging area
- git add --all (or) git add -A : add all files to staging area
- git add -A dir_path/ : add all files in the directory to staging area
- git add -u : add all modified / updated files (not new files)

#### Commit
- git commit -m "your_message" : commit changes with commit message

#### Log
- git log : View commit histories

#### Git Clone
- git clone "url" "path_to_clone" : clone repository from url to the path specified

#### Info about Remote Repo
- git remote -v : Show remote repository url

#### Git Difference
- git diff : show changes made
- Minus Sign : removed lines
- Plus Sign : added lines

#### Git Push & Pull
- git pull origin "branch" : any changes made by others after last pull or clone is pulled from remote
- git push origin "branch" : push local changes to remote
- git push -u origin "branch_name" : push local changes to remote repository branch. "u" states that the local branch and remote branch are linked so that next time if just git push and git pull is done, the changes are pushed or pulled between these two branches only.

#### Git Branches
- git branch -a : list all branches (local and remote). * in front of a branch is the current branch
- git branch "branch_name" : create branch
- git checkout "branch_name" : Switch to the branch specified

#### Merge Branches
- To merge new branch with branch "master"
- git checkout master ; Checkout to master branch
- git pull origin master : Pull any changes in remote (if made)
- git branch --merged : View branches merged with current branch so far
- git merge "branch_to_merge" : merge specified branch to current branch
- git push origin master : now push the merged branch to remote

#### Delete Branch
- After feature is done, delete the branch
- git branch -d "branch_name" : delete  the specified branch locally (not remotely)
- git push origin --delete "branch_name" : delete branch in remote repository

## [Git Tutorial: Fixing Common Mistakes and Undoing Bad Commits](https://youtu.be/FdZecVxzJbk)

#### Undo Changes to Last Commit
- git checkout "file" : rollback to previous commit in the file

#### Change last commit message
- git commit --amend -m "new_commit_message" : replace last commit message with the new commit message
- commit hash is different now

#### Change last Commit itself
- git commit --amend
- Press :wq to save the commit with same commit message
- commit hash is different now

#### Commit History Statistics
- git log --stat : see all the changes made inside the history of commits

#### Cherry Pick - Copy Commit from one branch to another branch
- git cherry-pick "commit_hash" : Copy the commit with specified hash to current branch

#### Git Reset - Delete Commit & Changes
- Three Types
	+ Reset Soft
	+ Reset Mixed (default)
	+ Reset Hard	
- git reset --soft "hash_commit" : Delete the commit but retains the changes made in staging area
- git reset "hash_commit" : Delete the commit and remove the changes from staging area but the changes are in working directory
- git reset --hard "hash_commit" : Delete the commit and remove the changes from staging area and from working directory (only tracked files).
- git clean -df : get rid of changes made in untracked directories (d) and files (f)
- Deleted files by git hard are stored approximately for 30 days. After this, those deletion can't be recovered.

#### Git RefLog
- git reflog : View commit Log including Amend, Cherry pick, Reset

#### Git Checkout - Recover Deleted Commit
- git checkout "commit_hash" : Undo deleted commit
- git branch "branch_name" "commit_hash" : Make branch from detached head

#### Git Revert
- git revert "commit_hash" : Undo the changes made by the specified commit but the undo is made as a new commit so that this will be helpful in situations when other developers have already pulled the commit.

#### Git Diff - Between two commits
- git diff "commit1_hash" "commit1_hash" : show difference between the changes between the mentioned two commits

## [Git Tutorial: Using the Stash Command](https://youtu.be/KLEDKgMmbBI)

#### Git Stash
- git stash save "stash message" : temporary save without commit so that we can move to other branches
- git stash list : view the temporarily saved changes
- git stash apply "stash{id}" : load the temporarily saved stash
- git stash pop : pop the first stash
- git stash drop "stash{id" : drop the saved stash
- git stash clear : drop all saved stash