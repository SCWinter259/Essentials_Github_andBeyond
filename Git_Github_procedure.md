## Before work

First of all, clone the remote repo to your local machine

`git clone [link of the repo]`

First thing to do everyday is to switch to local main branch

`git checkout main`

and pull everything down in case the remote main had some changes

`git pull`  (the full syntax is `git pull origin [branch name]`, but git pull is automatically from the remote main branch)

## Work

First of all, create a different local branch, because no one likes a straight unsafe commit directly to the main branch

`git branch [new branch name]`

Then switch to that branch and perform your work on it

`git checkout [branch name]`

## After work

Add all files. This means telling git to track all files

`git add .`

Commit your changes to the local branch

`git commit -m ["whatever the message may be"]`

Now checkout to main branch and push your work branch to github

`git checkout main` &nbsp; then &nbsp; `git push origin [name of the other branch]`

## Others

You can merge the changes you made to the main branch (although I encourage pulling from remote main branch)

`git merge`

After that, you may delete your work branch (you can leave it there if you want to continue working on the project)

`git branch -d [branch name]` &nbsp; (you may use capital D instead of d to force delete without the need to merge)