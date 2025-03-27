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

## Stage and snapshop
These are common commands used for working with snapshots and the Git staging area:

`git status`: to show current status. Use it to show modified files in the working directory, staged for your next commit. 

`git add`: to add files to the staging area. See usage details for staging area in the [git concepts](/git_and_github_concepts/git_concepts.md) file.

`git reset [file]`: unstage a file while retaining the changes in your working directory

`git commit -m "meaningful message"`: to commit files from the staging area.  

## Inspect and compare
Commands to examine logs, diffs and object information  

`git log`: to see the log of all commits (for the currently active branch). Can be used with `-n #` where `#` is the number of commits in the past to show. `--abbrev-commits` will provide the abbreviated SHA for the commits.  

`git log branchA..branchB`: show the commits on branchA that are not on branchB.

`git log --follow [file]`: show the commits that changed the specified file, even across renames

`git diff`: to show the difference between changes in your working directory and staged area.

`git diff --staged`: to show differences between staging area in all local files and the repository. If you add a filename, you will only see the staged changes in a certain file. Alternative: `git diff --cached`

`git diff <commit1> <commit2>`: to show differences between commits. Where <commit1> and <commit2> are the SHA of the commits to be compared. First will be compared to second.  

`git diff <branch1> <branch2>`: show differences between two branches. 

