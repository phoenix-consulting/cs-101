# An Introduction to Git
Woohoo y'all get a custom introduction to how to use Git and GitHub!

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