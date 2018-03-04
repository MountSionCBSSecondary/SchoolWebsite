Before you start the tutorial, we will assume that you have git installed onto your computer.
If you don’t have git, then you can learn how to install it [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). Here is a guide on the commands of [git also.](http://feedhenry.org/student-help-guide/topic04-git-introduction/book-git-tutorial/index.html#/Basics)

Before you can add your own changes to the school website, you first need to “fork” the repo of which that you want to change. To “fork” a repo means to get your own copy of the repo, in this case our school website.  

![cap1](https://i.imgur.com/rzHlCWQ.png)

To confirm that you forked the repo then you can go onto your own github profile and see if it’s there.

![cap2](https://i.imgur.com/DyHeBql.png)

We then click onto the repo page and download our forked repo 

![cap3](https://i.imgur.com/JZpSjYc.png)

In this guide I will assume that you do not have an SSH key. Although SSH keys aren’t vital, they make it easier to push things onto your github account.  
You then open up your terminal if you’re on mac or linux. If you’re on windows then you open your powershell.  You then travel to the file where you want to save your repo using the  ```cd <FOLDER>``` command. 

Once you get there you type ```git clone https://github.com/YOURUSERNAME/SchoolWebsite.git```.
You should get a message similar to this one 

```
Cloning into 'SchoolWebsite'...
remote: Counting objects: 12, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 12 (delta 0), reused 9 (Delta 0), pack-reused 0
Unpacking objects: 100% (12/12), done.
```

You are now able to edit your forked repo, and can push your changes up to your repo, now all we need to do is make a branch, so that we are able to do a pull request.

You can make a branch by typing ```git checkout -b <BRANCHNAME>```.
You will be automatically switched to the new branch. The reason you use branches is so that you don’t push things to the master branch and potentially break your repo. Branches are a safe space for experimenting with the code. You can push,commit and add things to branches just like with the master branch. You can switch between branches using ```git checkout <BRANCHNAME>```. 

We push our changes up to our repo with the branch, and then go onto the forked repos github page, and you will see that you are able to do a compare/pull request.

![cap4](https://i.imgur.com/lgqfZVg.png)

You click the button and you arrive on this screen

![cap5](https://i.imgur.com/UsKsemn.png)

Write the changes that you made in the title and and a small comment for more detail if needed. You then click the “create pull request” and that’s it.  You wait for the administrators to accept or deny your changes.  If it’s accepted then your changes will be live on the master repo.  If it isn’t accepted then you make the changes that the admins request and do another pull request
