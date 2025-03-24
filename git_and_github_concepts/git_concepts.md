# GIT AND GITHUB CONCEPTS

## What is Git and Github?
**Git:** 
Git is a software to create a timeline of your projects. It keeps track of all changes you make during your project development and allows you to go back to each version at any point in time. You can save changes, and once you commit them to a version that is a snapshot in time.

**Github:**
Online repository to collect different git projects. Github is an online backup of all your timelines that were created in git.

## How to start your timeline/repository?
**Start a local repository:**
When you are in your local project folder, you can start the timeline by initializing git, this will create a .git file. Git tracks every subfolder in your root folder, so no need to initialize it twice. 
`git init`

**Start from a remote repository:**
1. On github, you can go to a remote repository, and clone it to your local machine. No need to initialize the timeline again. 
`git clone ssh-address-repository`

2. You can also first 'fork' to create a personal copy of a repository on GitHub. It allows you to freely experiment with changes without affecting the orignal repository.

## Where is Git/GitHub? Three conceptual areas:
**1. Developing area**
My computer: developing area with local folder where project is developed. 

**2. Preparation: staging area?**
If we do `git add`, we send it to the staging area, which is the place where you add files to prepare for commit. Location to prepare new snapshots to the timeline (before commit). 

**3. Local repostitory: where is the timeline?**
The local repository on your computer is where all the versions live. It is the .git folder you have initialized. Typically only text files. 

**4. Remote area: GitHub**
It is the remote repository. You first need to make a repository in GitHub, then you can use the ssh address of the repository to make a bridge on your computer to the remote repository. After that, you can push your local repository to the remote one. Make sure to always clean up your working tree first (check with git status).

GIT WORKFLOW:
1. adjust your files and save (developing area)
2. once you are ready, you should do:
`git add file_A`: send a copy of the file to the staging area\
`git add *`: send a copy of all modified files to the staging area\
3. commit changes:
`git commit -m "message"`: you send from staging area to local commit, linked to a meaningful message.\

4. push changes to remote repository:
`git push`: send commit to remote areay

5. retrieve remote changes locally
`git pull`: get updates

## Collaborations:
**Adding collaborators:** You can grant other GitHub users access to your repository as collaborators, allowing them to push changes.

**Pulling changes:** pulling fetches changes from a remote repository and merges them into the current branch.

**Conflicts:** If you are working with someone simultaneously and somebody pushes it before you, this will create a conflict, because Git cannot automatically merge changes. When you try to push your modifications, you will get an error. You need to manually resolve conflicts by editing the conflicting files. For this, you first need to pull the latest version (containing the commit of your collaborator), then you can modify the file and look at the conflict closely and resolve. After that, you need to git add, commit and push it again. 

**Pull requests:** A pull request is a way to propose changes to a repository and facilitate collaborations. You create a pull request when you want to merge changes from one branch into another, and you need someone to review and approve them before merging. 
    1. Push your changes to github
    2. Open GitHub and navitage to your repository
    3. Click the "Pull Requests" tab and create a new pull request, selecting your feature branch and the main branch
    4. Once reviewed, the pull request can be merged.

## Tag a commit
You can use git tag to tag/commit a useful commit in your timeline. This can be a stable release, a specific version,..
When you push, you need to add git push --tags as well. 
git tag -d <name> to delete a tag, but you also need to delete it manually on github. 

## Branches
A branch is an independent timeline that roots from the main timeline. You can use it to work independently on same project, to experiment without risk, etc.
`git branch <name>`: initiate a new branch

To move between branches you need to do git checkout.
`git checkout <branch_name>`: switches between branches.

Once you’ve completed work on a branch, you can merge it back into the main branch:
- first switch to the main branch: `git checkout main`
- merge your branch with main: `git merge <your_branch>`

Once merged, you can delete the branch:
`git branch -d <your_branch>`

## What is a .gitignore file?
In many cases, the project creates a lot of logs and other irrelevant files which are to be ignored. So to ignore those files, we have to put their names in“.gitignore” file.  
The .gitignore file specifies files and directories that should be ignored by Git. It is used to prevent certain files from being tracked or committed.

## GitHub history and keeping track of commits
You can create an overview of what commits have been done in the entire history of your project. It shows you the commit hashes (IDs), the author and date of the commit, and the message that was assigned to it. It is great for reviewing past changes or finding a specific commit.
`git log`: display commit history

You can keep track of what is going on in your working directory and staging area using git status.
`git status`: it shows you which files have been modified, which files are staged and which are untracked (new and not in git yet)

To compare different commits or files you can use git diff.
1. `git diff`: see unstaged changes (working directory vs last commit)
2. `git diff --cached` or `git diff --staged`: see staged changes (staging area vs last commit)
3. `git diff <commit1> <commit2>`: compare two commits 
