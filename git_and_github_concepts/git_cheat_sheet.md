# This is a cheat sheet for git and github
## Git commands
`git init`: to initialize a repo  

`git add`: to add files to the staging area. See usage details for staging area in concepts_dictionary.md

`git commit -m "meaningful message"`: to commit files from the staging area  

`git status`: to show current status

`git log`: to see the log of all commits. Can be used with `-n #` where `#` is the number of commits in the past to show. `--abbrev-commits` will provide the abbreviated SHA for the commits.

`git diff <commit1> <commit2>`: to show differences between commits. Where <commit1> and <commit2> are the SHA of the commits to be compared. First will be compared to second.