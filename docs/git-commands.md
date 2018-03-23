# Git Command Guide
For a detailed guide on how to fork the repo and push changes you can check out [our tutorial](Tutorial.md) guide. This command guide is a point of reference to a number of scenarios that you will encounter while contributing to this repo. A convention in this document is to use `<< >>` to indicate text that you will need to replace when running the commands on your own machine.

## Clone this REPO
Before you begin, you will need to clone this repo
```
git clone https://github.com/MountSionCBSSecondary/SchoolWebsite.git
```
The above command will download a copy of the repo to your local machine. This copy of the repo will have the remote name of `origin`.

## Add your own Remote
Once you have the origin remote configured locally (i.e. your local copy knows where original repo is), you will need to configure your fork as a remote locally(i.e. your local copy knows where your fork is)
A remote is a URL and it is github's way of specifying where a repo is stored. There are two ways to talk to a remote `https` and `ssh` For example the school website `https` remote is `https://github.com/MountSionCBSSecondary/SchoolWebsite.git` and the `ssh` remote is `git@github.com:MountSionCBSSecondary/SchoolWebsite.git` 

It should also be noted you will need to have forked the repo, how to do this can be seen in [our tutorial](Tutorial.md)

```
git remote add <<your-name>> https://github.com/<<Your Github UserName Here>>/SchoolWebsite.git
```

## Committing and Creating PR's
So now you have following completed:
- The repo cloned
- Your fork remote added
- The main repo remote added

Before you can begin working on the repo we need to understand what a `branch` is. `Master` is a `branch` the main `branch` where our code will live. When we want to add features or experiment with the website we will need to create a new `branch`, when you create a new `branch` you are creating a new environment (which is identical to `master` branch) to which you can apply changes to and test without the worry of breaking, causing errors or adding bugs to our `Master` branch.

When you are happy with the changes you made to your `branch` and you want to add the changes to our `Master` branch then you will need to create a `Pull Request`, this is basically where you can show the changes you made to the whole team, and as a team we can discuss and review your changes. When at least two team members have reviewed and approved the changes, the creator of the pr can then merge it to `Master`. You can also request another team member to merge you pr to master if you like.

You can now begin to work and create your own PR against the main repo. To do this, you must create a branch. It is a good convention to give the branch a descriptive name, usually something descibing the work in the PR, keep this name short and to the point, example `add-contact-page`

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
It should also be noted it is often the case where you will not want to add all files to your commit. Below is an example of an output when I ran `git status` while working on this guide.
```
On branch add-cheat-sheet
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   docs/git-commands.md
        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
```
As can be seen here there is two files that have been modified, since the changes in `index.html` is out of the scope of the PR releated to the guide, we only want to add the `docs/git-commands.md`. This can be done as follows. 
```
git add docs/git-commands.md
```
After running the above command if we run `git status` again we get the following output.
```
On branch add-cheat-sheet
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   docs/git-commands.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   index.html
```
As we can see, the `docs/git-commands.md` file is now after moving to `changes to be committed`, and the `index.html` file is under `not staged for commit`. This is exactly what we want, we can now proceed with adding a message and pushing our changes as shown above.

Now you have pushed your changes on your branch to your remote, refer to [our tutorial](Tutorial.md) on how to create a PR from here

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
Now you can view and run the code of the PR locally. Once you are done you can checkout a different branch or if you wish to return to the branch you were on before you checked out the PR run the following command
```
git checkout -
```
## Rebasing your own PR
With multiple people working on the same project, the master branch may have changed by the time you're ready to make your PR. Your branch must be up to date with the latest version of the master branch before you make a PR. This is known as `rebasing`.

This process is done by the following, first you need to checkout master, `the master is the branch that is in line with the origin repo on GitHub`, once you are on the master branch you will need to pull the changes down from GitHub. Now your master branch locally is up to date with the github repo. Next, you need to check out the branch you want to rebase, once on this branch, you can rebase off your local master branch. So to do that you can run the following commands
```
git checkout master
git pull origin master
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

## Resetting
It should be noted that resetting can potentially be dangerous as you will lose any uncommited or stashed changes when you run the command.

If you need to return to a previous state you can run the following command. It will reset your code locally to the code of the commit you specify in the command.

```
git reset --hard << commit >>
```
