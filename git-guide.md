# An Introduction to Git
Woohoo y'all get a custom introduction to how to use Git and GitHub!

[Christopher Zou](chriswzou.github.io), 11/2021

## What is Git?
You know how you can hit save, undo, and redo things when you're working in Microsoft Word? 
The underlying software is called version control software, so named because it allows you
to keep track of what version of something you're working on. **Git** is like the version control software
in word, but it works for any kind of file, not just inside Word documents: it allows us to
save, undo, and redo things when it comes to code, pictures, and more. **GitHub** is like Google
Drive when it comes to everything that Git tracks: it saves our files in the cloud and lets us collaborate
with others.

You should make a GitHub account if you haven't already!

## Some Basic Git Concepts
1. The most fundamental unit in Git is the repository. You can think of repositories like top-level folders. 
They can have files or other folders inside of them.
2. Saves in Git are called *commits*. They're like snapshots of sets of files at given points in time.
3. Git relies on *branches* for collaborative development and organization. You can think of each branch as 
representing a series of changes to files you're tracking. A lot of learning to use Git is learning how to work with branches.
4. When using Git to track files, you'll generally have a local repository and a remote repository. Imagine that you had
a Google Doc that you downloaded as a Word document to your computer; the Word document on your computer is the local repository,
while the version in the cloud still is the remote repository.

## Git Commands
These commands are usable while you're in the Terminal (Mac) or Git Bash (PC) in a directory where Git has been enabled. Separate
tutorials on using your command line tools coming soon!

- `git init` will initialize a git repository in a folder
- `git status` will show you what files you're tracking and what branch you're on, along with other goodies
- `git log` will show you your commit history
- `git add` will tell Git to track certain files
    - `git add -p` will give you options to see all of the changes you're making before starting to track files
    - `git add -A` will add all files that you don't have added in this folder
- `git commit -m "message here"` will save all of the files you're tracking as a snapshot in your commit history
- `git pull` pulls files from remote repositories into your local repository
- `git push` pushes files from your local repository into remote repositories
- `git branch` shows you all branches and what branch you're currently on
- `git checkout -b new-branch-name` creates a new branch and switches to it
- `git checkout branch-name` switches to a given branch
- `git rebase branch-name` takes all the commits in your current branch and stacks them on top of the given branch's commit history

## Git workflow
Suppose for example that you want to do some work on the Phoenix website. Here we'll walk through a full workflow.

First, we want to clone the repository. Navigate to the folder where you want the website to be saved. Then in your terminal, type
```
git clone https://github.com/phoenix-consulting/pcg-site-2.git
```
We get https://github.com/phoenix-consulting/pcg-site-2.git from visiting the [repository on GitHub](https://github.com/phoenix-consulting/pcg-site-2)
and clicking the green "Code" button.

Once you've got the repository cloned, change into that directory. Run
```
git status
```
and you should see something like this:
```
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```
If you already had the repository cloned, make sure that you run
```
git pull
```
to get the latest changes from the remote repository. To make edits, create a new branch like so:
```
git checkout -b my-branch-name
```
Make your edits and use the following commands to save as you work on your branch:
```
git add -A
git commit -m "Your commit message here"
```
Creating descriptive commit messages will help others to better understand your work! Making many small commits provides better safety in case you accidentally do something to your repository.

Once you've committed all your edits, run the following series of commands:
```
git checkout master
git pull
git checkout my-branch-name
git rebase master
```
This will take your commits and save them on top of the remote master branch's commit history. 

Now here's the point where things will differ depending on whether you're working independently or not. If you're working independently, you can run these
commands:
```
git checkout master
git rebase my-branch-name
git push
```
In the event that you're working with others, it's better to follow a pull request workflow. Make sure that you're on your branch using `git checkout my-branch-name`. Then
run:
```
git push origin my-branch-name
```
Navigate to the repository on GitHub and you'll see a pop-up that says "Create pull request." Go ahead with this process and eventually you'll be able to merge your pull request
with master. In companies, your pull requests are typically reviewed by others. For our purposes, you can assume that once you've merged the pull request, you'll be able to
use `git pull` to retrieve the new, updated master branch.

At this point, it's good practice to pull from master and delete your local branch:
```
git checkout master
git pull
git branch -d my-branch-name
```
And that's it! You've mastered a basic Git workflow that will serve you for years to come :)

## Additional Questions?
- Official Git documentation: https://git-scm.com/docs
- Combining commits using Git squash: https://www.youtube.com/watch?v=V5KrD7CmO4o
- Fixing common Git mistakes: https://www.edureka.co/blog/common-git-mistakes/
