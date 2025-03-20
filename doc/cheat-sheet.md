# Git Commands Cheat Sheet


## Check documentation

- `git <command> --help`  => see the documentation for a git command.


## Git Configuration

- `git config --global --list`     => check global configurations
- `git config --global user.name "<your name>"` => set user name
- `git config --global user.email "<your email>"` => set user email


## Git Workflow

- `git status`                => check the status of the files in the current branch
- `git add <files/folders>`   => stage files/folders of choice
- `git add --all`             => stage all files/folders in the repository
- `git add .`                 => stage all files/folders in the repository
- `git restore --staged "<file>`  => remove file from the staging area



- `git commit -m "<message>`  => commit the staged files/folders with a message
- `git commit`               => commit the staged files/folders with, a text 
                                 editor will open for a multiline comment 

## Check versions and changes

- `git log`                => get a list of all the commits in the current branch
- `git log <file name>`    => get a list of all the commits for a specific file in the current branch
- `git log --abrev-commit` => get a list of all the commits with an abbreviated commit references
- `git log -n 3`           => get a list of the last three commits 

- `git diff <old commit> <new commit>`  => create diff between two commits
- `git show <old commit> <new commit>`  => shows the two file next to each other between two commits


## Connect with remote repository

- `git remote add origin git@github.com:ddebeer/<repository name>.git` 
  => "make a bridge" between local and remote repository (using ssh)
- `git push --set-upstream origin main`  => first push: to create a branch upstream (on the remote repository)
- `git push -u origin main`              => push form origin (local repository) the branch main
- `git push`   => send the latest version of the commit history to the remote repository


## reverting and restoring

- `git revert <commit ID>` => creates a new commit that is the same as the chosen one


## Collaborating 

- `git clone <ssh remote>` => creates a local repositor, creates "the bridge" and pulls the complete project (commit history)


## Tagging

- `HEAD` is the most recent commit, hence the HEAD changes with every new commit
- `git tag <name>`   => give the current commit a name of choice: a "tag"
- `git tag <name>`   => give the current commit a name of choice: a "tag"
- `git tag <name> <commit ID>`  => give the commit of choice a name.
- `git push --tags`  => push all the tags to the remote repository
- `git tag -d <name>` => delete the tag  BUT not on github, should be deleted manually.


## Branching

- `git branch <branch name>`   => creates a new branch with a chosen name
- `git chekcout <branch name>` => jumps to the chosen branch, new commits are
                                  added to that branch.
- `git chekcout HEAD`          => jumps to the most recent commit 

- `git branch -l`              => list the local branches
- `git branch -a`              => list all branches, local and remote
- `git branch -b <new branch>` => create a new branch and jump to it immediately.


- `git push --set-upstream origin <branch name>`  => push new branch and create a corresponding branch remote
- `git push --al`              => push all commits of all local branches

- `git chekcout <commit ID>`   => jumps to the chosen commit (i.e., travel in time)
- `git switch -c <new branch>` => create a new branch after traveling to a commit (in the path).

- `git log --graph --all`    => give a visual overview of all the branches


## merging

- `git merge <branch names>` => tries to merge the (HEAD of the) chosen branch with
                                the (HEAD of the) currently active branch. If merging
                                automatically is not possible, conflicts will need
                                to be resolved and commited.

- `git branch -d <branch name>` => delete a branch


