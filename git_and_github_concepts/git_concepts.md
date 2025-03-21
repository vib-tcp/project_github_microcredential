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
On github, you can go to a remote repository, and clone it to your local machine. No need to initialize the timeline again. 
`git clone ssh-address-repository`

## Where is Git/GitHub? Three conceptual areas:
**1. Developing area**
My computer: developing area with local folder where project is developed. 

**2. Preparation: staging area?**
If we do `git add`, we send it to the staging area, which is the place where you add files to prepare for commit. Location to prepare new snapshots to the timeline (before commit). 

**3. Local repostitory: where is the timeline?**
The local repository on your computer is where all the versions live. It is the .git folder you have initialized. Typically only text files. 

**4. Remote area: GitHub**
It is the remote repository. You first need to make a repository in GitHub, then you can use the ssh address of the repository to make a bridge on your computer to the remote repository. After that, you can push your local repository to the remote one. Make sure to always clean up your working tree first (check with git status).

WORKING ORDER:
1. adjust your files and save (developing area)
2. once you are ready, you should do:
`git add file_A`: send a copy of the file to the staging area\
`git add *`: send a copy of all modified files to the staging area\
3. commit changes:
`git commit -m "message"`: you send from staging area to local commit, linked to a meaningful message.\

4. push changes to remote repository:
`git push`: send commit to remote areay

##Branches


