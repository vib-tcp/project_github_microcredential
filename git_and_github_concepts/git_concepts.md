# GIT AND GITHUB CONCEPTS

## What is Git and Github?
**Git:** 
Git is a software to create a timeline of your projects. It keeps track of all changes you make during your project development and allows you to go back to each version at any point in time. You can save changes, and once you commit them to a version that is a snapshot in time.

**GitHub:**
Online repository to collect different git projects. GitHub can be used as an online backup of all your timelines that were created in git. As a web-based platform, GitHub offers several features that extend beyond the basic functionalities of git. These include:  
- Repository Hosting: GitHub hosts Git repositories online, making them accessible from anywhere. 
- Pull Requests: This feature allows developers to propose changes to a codebase, review code, and discuss modifications before merging.  
- Issues and Bug Tracking: GitHub provides a built-in issue tracker to manage bugs, feature requests, and other tasks. 
- Project Management Tools: GitHub offers project boards, milestones, and other tools to help manage and organize development tasks. 
- Code Reviews: GitHub facilitates code reviews with inline comments and discussions on pull requests.  
- Actions and CI/CD: GitHub Actions allows you to automate workflows, including continuous integration and continuous deployment (CI/CD). 

## How to start your timeline/repository?
**Start a local repository:**  
When you are in your local project folder, you can start the timeline by initializing git, this will create a .git file. Git tracks every subfolder in your root folder, so no need to initialize it twice.  
`git init`

**Start from a remote repository:**  
1. On github, you can go to a remote repository, and clone it to your local machine. No need to initialize the timeline again.  
`git clone ssh-address-repository`

2. You can also first 'fork' to create a personal copy of a repository on GitHub. It allows you to freely experiment with changes without affecting the original repository.

## Where is Git/GitHub? Three conceptual areas:
**1. Developing area**  
My computer: developing area with local folder where project is developed. 

**2. Preparation: staging area?**  
If we do `git add`, we send it to the staging area, which is the place where you add files to prepare for commit. Location to prepare new snapshots to the timeline (before commit). 

**3. Local repository: where is the timeline?**  
The local repository on your computer is where all the versions live. It is the .git folder you have initialized. Typically only text files. 

**4. Remote area (GitHub):**  
It is the remote repository. In the context of this course, we use GitHub. You first need to make a repository in GitHub, then you can use the ssh address of the repository to make a bridge on your computer to the remote repository. After that, you can push your local repository to the remote one. Make sure to always clean up your working tree first (check with `git status`).

GIT WORKFLOW:
1. adjust your files and save (developing area)

2. once you are ready, you should do:  
`git add file_A`: records the changes made to file_A and adds it to the staging area  
`git add *`: records the changes made to all files and adds it to the staging area  

3. commit changes:  
`git commit -m "message"`: you send from staging area to local commit, linked to a meaningful message.  

4. push changes to remote repository:  
`git push`: send commit to remote area  

5. retrieve remote changes locally:  
`git pull`: get updates

## Collaborations:
**Adding collaborators:** You can grant other GitHub users access to your repository as collaborators, allowing them to push changes.

**Fetching changes:** Fetching changes from a remote repository downloads changes but does not apply them to your local branch.

**Pulling changes:** Pulling changes from a remote repository downloads and merges them to your local branch.

**Conflicts:** If you are working with someone simultaneously and somebody pushes it before you, this will create a conflict, because Git cannot automatically merge changes. When you try to push your modifications, you will get an error. You need to manually resolve conflicts by editing the conflicting files. For this, you first need to pull the latest version (containing the commit of your collaborator), then you can modify the file and look at the conflict closely and resolve. After that, you need to git add, commit and push it again. 

**Pull requests:** A pull request is a way to propose changes to a repository and facilitate collaborations. While a request for a pull exists as a git concept, the formalized pull request is a feature of web-based git hosting services like GitHub. You create a pull request when you want to merge changes from one branch into another, and you need someone to review and approve them before merging.  
    1. Push your changes to GitHub  
    2. Open GitHub and navigate to your repository  
    3. Click the "Pull Requests" tab and create a new pull request, selecting your feature branch and the main branch  
    4. Once reviewed, the pull request can be merged.  

GitHub provides extensive documentation on pull requests in their [GitHub Docs platform](https://docs.github.com/en/pull-requests).  

## Tag a commit
Git allows to create tags to mark specific points in the timeline of your repository. Tags can be used to specify specific versions of the code in a project. They can also be used to denote significant milestones in the development process.  
You can use `git tag <tag_name>` to add a tag to a commit in your timeline.  
It is important to note that tags must be included in the push command. When you push, you need to add `<tag_name>`to push a specific tag or `--tags` to push all tags. 
To remove a tag, use `git tag -d <tag_name>` to delete a specific tag, but you also need to delete it manually on github.  

**A note on releases:** Releases are a GitHub feature. They work on top of the tags feature and provide a way of packaging and distributing specific versions of the project. In addition to including release notes, releases can also have downloadable assets, like software source code.  

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

**A note on direct merging and pull requests**
While you can directly merge a branch into your main branch, the commands described above do not include a review process. In collaborative projects that are hosted in web-platforms such as GitHub, the use of a pull request to bring code changes from a branch into the main branch of a project is advisable. Pull requests allow for collaborators to review and comment on changes, giving chance for useful feedback and code improvements.   

