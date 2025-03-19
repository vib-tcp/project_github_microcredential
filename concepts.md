# Welcome to our file explaining the different concepts we used on this project

## Here are some examples of what we did 
After Arthur forked and cloned the original, he created his own branch :

`git branch Arthur`  

Then proceeded to commit some changes:

`git add cheat_sheet`
`git commit -m "Added cheat sheet md and some initial info"`

After some other commits and conflict creation it was now time to merge his branch w/ the main one (from the main one):

`git merge Arthur`

But "oh oh", some massive conflict emerged. It was now time to decide which changes were the most relevant to keep before adding and commiting again!

## But how did we do all that ? How did we get there ? Well here is the knowledge needed.
First we both cloned the forked repository, using :
`git clone <SSH key>`
--> Cloning means that we're making a local copy of a repository from github.

I wanted to check out the branch from Arthur but I couldn't find it w/ `git branch -l`. That's right, because Arthur's branch needed to be checked-out before we could see it locally. Therefore I used :
`git checkout <ArthurBranch>`

Then you can create your own branch to experiment risk free while working on a collaboration: 
`git branch <MyBranchName>`

Then it's just a question of adding and commiting new changes before merging all branches. 





