# Cheat sheet
This file gives an overview of often-used commands. Use `--help` to get an overview of all the options

## Basic workflow
`git init`: initaliazes .git file

`git add <filename>`: add to staging area

`git commit -m 'message'`: commit to local repo

`git push`: push changes from local to online repo

`git pull`: pull cahnge from online to local repo 

## Additional commands
`git status`: check status of all files (unstaged, uncomitted, comitted)

`git log`: history of git commands, **push q to exit**
Options: 
- `-n <number>` (only `number` recent ones are shown)
- `--abbrev-commit` (shorter relevant name for commit)


`git diff <commit ID1> <commit ID2>`: shows difference between two versions. Always compares ID1 to ID2 (ID1 is considered original, ID2 the new one). Compares line by line.

Alternative: `git show <commit ID1> <commit ID2>` (shows to versions sperately, compare yourself)

Alternative: use a GUI (gitlens)

`git revert`: reinstates last commit AS A COMMIT(<-> reset which doesn't save the changes!)

`git clone <ssh-address>`: creates a local repo (and adds LINK/bridge - so no need to do this anymore, but all .ignore files are gone), go to GitHub and retrieve SSH address (click on Code, and then dropdown menu)

`git tag <tag_name> <commit ID>`: adds a tag to current (if no `<commit ID>` specified) or specified version of local repo (on existing commit, not next one!)

`git push --tags`: tags need to be pushed specifically!!

`git branch <name>`: work apart from main branch & only when it is fixed you merge the branches. There will be several 'heads', one for each branch.
`git branch -b <name>`: creates new branch and immediately moves to there

`git checkout <name>`: jump between branches, also modifies working directory!
`git checkout <commit_id>`: jump to a previous commit node, which creates 'a detached head', which is unlinked to the main

`git switch -c <new_branch_name>`: creates new branch from detached head
Dea`git switch -`: move back from detached head to before

`git merge <branch_name>`: merges the specified branch INTO the current branch (which should probably be `main`)

`git branch -l`: prints an overview of branches
`git branch -a`: prints an overview of branches, including online branches

`git branch -m old-name new-name`: change name of specified branch

`git push -u origin feature-branch`: in order to push branch to online repo for the first time
`git push --al`: pushes all branches to remote repo

## GitHub commands

Create a new GitHub repo from command line (private, current wd)
`gh repo create my-new-repo --private --source=. --remote=origin --push`

`gh pr create --base main --head my-feature-branch --title "Add new feature" --body "This PR adds a new feature."`: create a new pull request