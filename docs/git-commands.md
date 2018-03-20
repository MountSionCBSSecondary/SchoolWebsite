# Git Hub Command Guide
The following is a number of scenarios that you will encounter while contributing to this repo, a convention in this document is to use `<< >>` to indicate text that you will need to replace when running the commands on your own machine.

## Clone this REPO
Before you begin, you will need to clone this repo
```
git clone https://github.com/MountSionCBSSecondary/SchoolWebsite.git
```
The above command will download a copy of the repo. This copy of the repo will have the remote name of `origin`.

## Add your own Remote
Once you have the origin remote you will need to add a remote to your own fork of the repo. This can be done with the following command, just replace the placeholder with your own github name.

It should also be noted you will need to have forked the repo, how to do this can be seen in [our tutorial](Tutorial.md)

```
git remote add <<your-name>> https://github.com/<<Your Github UserName Here>>/SchoolWebsite.git
```

## Committing and Creating PR's
So now you have following completed:
- The repo cloned
- Your fork remote added
- The main repo remote added
You can now begin to work and create your own PR against the main repo. To do this, you must create a branch. It is a good convention to give the branch a descriptive name, usually something descibing the work in the PR, keep this name short and too the point, example `add-contact-page`

```
git checkout -b <<desciptive-name-here>>
```
Now you are working on a new branch, when you are happy with your changes or just want to save the changes to the branch you can commit it, it is good practice to run the following command first to see what files have been changed by your work.
```
git status
```
If all the files listed are the ones you are happy with to commit to your branch run the following series of commands.
```
git add .
git commit -m '<<describe the changes here>>'
git push <<your-remote-name>> <<your-branch-name>>
```
Now you have pushed your changes on your branch to your remote, refer to [our tutorial](tutorial.md) on how to create a PR from here

## Checking out other peoples PR's
In order to check out someones PR you need to add that persons remote, this can be done with the following command, just replace the tags with the persons GitHub name
```
git remote add <<persons-name>> https://github.com/<<Persons-GitHub-userName>>/SchoolWebsite.git
```
Now that the person who created the PR's remote is added to your git project, you will need to fetch that person's branches, that can be done with the following command after you have added their remote
```
git fetch <<persons-name>>
```
Now you have access to the branches associated with that person's fork of the repo. If you run the following:
```
git branch -v
```
You will see a list of available branches to you locally, you will now need to check the PR on GitHub to see what branch the PR was created on, once you got the name you can enter the following
```
git checkout <<PR-branch-name>>
```
Now you can view and run the code of the pr locally. Once you are done you can checkout a different branch or if you wish to return to the branch you were on before you checked out the PR run the following command
```
git checkout -
```
## Rebasing your own PR
So with multiple people working on a project the master branch (the original repo) can get ahead of the branch you are working on, so you will need to catch your work up to the master, this is known as Rebasing.

This process is done by the following, first you need to checkout master, the master is the branch that is in line with the origin repo on GitHub, once you are on the master branch you will need to pull the changes down from GitHub. Now your master branch locally is uptodate with the github repo. Next, you need to check out the branch you want to rebase, once on this branch, you can rebase off your local master branch. So to do that you can run the following commands
```
git checkout master
git pull origin
git checkout <<branch-to-rebase>>
git rebase master
```
Now your branch is up to date with the GitHub repo, since your branch is now out of sync with your PR, you will have to push with some force to apply the rebase to your PR, this can be done with the following
```
git push --force-with-lease <<your-github-name>> <<your-branch-name>>
```
WARNING: force with lease should only be used when rebasing and when you have followed the above instructions and successfully completed a rebase with no errors and conflicts unless you are otherwise told.
It should also be noted, that pushing with force is not recommended as you run the risk of deleting someone else's work. It is a good habit to build to never push directly to master, especially on a repo where more then one person is working on

## Stashing
Stashing is a method you may need when you want to change branches for instance and you have uncommitted changes, this can happen when you wish to checkout a PR if this is the case and you do not want to commit your changes just yet you can stash them.

Stashing will basically save your changes locally which you can apply to your branch at a later time.

So if you wish to stash your changes you can simply run
```
git stash
```
Now all you uncommitted changes will be stashed and you will be free to switch branches, to view your stash you can run the following
```
git stash list
```
You will notice each stash has an associated number, ranging from `{0 . . . n}` `n` being the number of stashes you have, the latest stash will be `0` and the oldest stash will be `n`

When you return to your branch an are ready to return to work and wish to restore your latest stash, simply run the following
```
git stash apply stash@{0}
```
This will apply the changes in your latest stash to your current branch if you want to apply changes from a different stash simply replace `0` with the corresponding stash number.

