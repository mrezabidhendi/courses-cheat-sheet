##### `git status`
- see the changes to the project files and directory

##### `git add .`
##### `git add file_name`
- add untracked files to git project in order to track them (stage files)

##### `git commit -m "MESSAGE"`
- save the changes to the tracked files with the respective message regarding the changes

##### `git restore --staged file_name`
- unstage file

##### `git log`
- see the history for all commits

##### `git reset [Commit ID]`
- go back to the commit with the specified ID and just forget about whatever commited after that particular commit.

##### `git stash`
- change the files that are being tracked by git to how they were in the latest commit! If they have been changed the changes will be undone.

##### `git stash pop`
- bring the changes that were done to the files back. files would feature the changes done after the latest commit and before being stashed.

##### `git stash clear`
- clears the stash and whatever changes that were not commited would be lost forever!

##### `git remote add origin URL`
- Connect the local project to a remote git project via URL

##### `git remote -v`
- show the URLs attached to Local Project

##### `git push origin branch_name`
- push the local changes to an origin server

>### NEVER COMMIT NON-FINALIZED CHANGES TO THE MAIN BRANCH
- while developing always have a branch for developement and only commit the finalized code (production/release) there.

##### `git clone [URL]`
- cloning a URL to your Local device

##### `git remote add upstream [URL]`
- add another URL as upstream to your project (it will be shown whenever you run `git remote -v` command) (usecase e.g. when you forked a project on your account and you wanna add link to the main project as upstream)

##### `git branch branch_name`
- create a branch with the name passed as argument

##### `git checkout branch_name`
- switch to the specified branch

> This text added in v4.2069-beta branch.

##### **\*REPEAT\***
##### `git push origin branch_name`
- push the local changes ***to a branch*** to an origin server

##### `git push origin branch_name -f`
- with the -f flag we ***force*** the branch to be pushed. it overwrites any commits that are only present in the online/remote repo.

##### `git fetch --all --prune`
- 
##### `git reset --hard upstream/main`
-
##### `git pull upstream main`
-

##### `git rebase -i [commit ID]`
- this command is used to squash multiple comments into one