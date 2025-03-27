# This is a cheat sheet for git and github

## Setup
This commands are for configuring user information used across all local repositories:

`git config --global user.name "[firstname lastname]"`: set a name that is identifiable for credit when review version history

`git config --global user.email "[valid-email]"`: set an email adress that will be associated with each history marker

`git config --global color.ui auto`: set automatic command line coloring for git for easy reviewing.

## Git setup & init
Commands to config user information, initialization and cloning repositories.

`git init`: to initialize an existing directory as a Git repository.  

`git clone [url]`: retrieve an entire remote repository via URL

## Stage and snapshot
These are common commands used for working with snapshots and the Git staging area:

`git status`: to show current status. Use it to show modified files in the working directory, staged for your next commit. 

`git add`: to add files to the staging area. See usage details for staging area in the [git concepts](/git_and_github_concepts/git_concepts.md) file.

`git reset [file]`: unstage a file while retaining the changes in your working directory

`git commit -m "meaningful message"`: to commit files from the staging area.  

## Branch and merge
Commands to isolate work in branches, change context and integrate changes 

`git branch <branch_name>`: create a new branch at the current commit

`git checkout <branch_name>`: switch to another branch 

`git merge <branch_name>`: merge the specified branch's history into the current one.

## Inspect and compare
Commands to examine logs, diffs and object information  

`git log`: to see the log of all commits (for the currently active branch). Can be used with `-n #` where `#` is the number of commits in the past to show. `--abbrev-commits` will provide the abbreviated SHA for the commits.  

`git log branchA..branchB`: show the commits on branchA that are not on branchB.

`git log --follow [file]`: show the commits that changed the specified file, even across renames

`git diff`: to show the difference between changes in your working directory and staged area.

`git diff --staged`: to show differences between staging area in all local files and the repository. If you add a filename, you will only see the staged changes in a certain file. Alternative: `git diff --cached`

`git diff <commit1> <commit2>`: to show differences between commits. Where <commit1> and <commit2> are the SHA of the commits to be compared. First will be compared to second.  

`git diff <branch1> <branch2>`: show differences between two branches. 

`git show [SHA]`: show any object in Git in human-readable format.

## Tracking path changes
Commands to version file removes and path changes

`git rm [file]`: delete the file from project and stage the removal of the commit

`git mv [existing-path] [new-path]`: change an existing file path and stage the move

`git log --stat -M`: show all commit logs with indication of any paths that were moved.

## Redo commits
Commands to erase mistakes and craft replacement history

`git revert [commit SHA]`: create a new commit, reverting changes from the specified commit. It generates an inversion of changes (safest option)

------ more dangerous option:

`git reset [commit]`: Undoes all commits after [commit], preserving changes locally. It switches the current branch to the target commit, leaving a difference as an uncommited change. 

`git reset --hard [commit]`: Discards all history and changes back to the specified command. 

**CAUTION**: changing history can have nasty side effects. If you need to change commits that exist on GitHub, proceed with caution. 


## Share and update
Commands to retrieve updates from another repository and updating local repository

`git remove add [alias] [url]`: add a git URL as an alias

`git fetch [alias]`: fetch down all the branches from that Git remote. It downloads all history from the remote tracking branches.

`git merge [alias]/[branch]`: merge a remote branch into your current local branch to bring it up to date.

`git push [alias] [branch]`: transmit local branch commits to the remote repository branch. 

`git pull`: Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. It is a combination of git fetch and git merge.  

## Tagging commits

`git tag`: list all tags

`git tag [name] [commit SHA]`: create a tag reference named 'name' for current commit. Add commit SHA to tag a specific commit instead of current one.

`git tag -d [name]`: remove a tag from local repository.  