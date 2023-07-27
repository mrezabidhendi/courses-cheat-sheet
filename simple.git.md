## git status
- see the changes to the project files and directory

## git add .
## git add file_name
- add untracked files to git project in order to track them (stage files)

## git commit -m "MESSAGE"
- save the changes to the tracked files with the respective message regarding the changes

## git restore --staged file_name
- unstage file

## git log
- see the history for all commits

## git reset [Commit ID]
- go back to the commit with the specified ID and just forget about whatever commited after that particular commit.

## git stash
- change the files that are being tracked by git to how they were in the latest commit! If they have been changed the changes will be undone.

## git stash pop
- bring the changes that were done to the files back. files would feature the changes done after the latest commit and before being stashed.

## git stash clear
- clears the stash and whatever changes that were not commited would be lost forever!

## git remote add origin URL
- Connect the local project to a remote git project via URL

## git remote -v
- show the URLs attached to Local Project

