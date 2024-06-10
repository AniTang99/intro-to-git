# How to Git Gud

![Git_logo](/assets/git-gud.jpg)

## Introduction

Git is an open source, distributed version-control system (VCS). Essentially, it is a program which tracks changes to a collection of files and and allows multiple users to share and work on files at the same time without affecting each other (mostly).

![Merge Conflicts](/assets/git-commands-copy.webp)

## Overview

-   [Installation](#installation)
-   [Configuration](#configuration)
-   [Git Terminology](#git-terminology)
-   [Initialize/Clone Repositories](#initialize-or-clone-repositories)
-   [Simple Git Workflow](#simple-git-workflow)
-   [Branching](#branches-as-far-as-the-eye-can-see)
-   [Merging Branches](#merge-the-branch)
-   [Helpful Commands](#helpful-commands)

## Installation

Git (All Platforms) - https://git-scm.com/downloads

Git Credential Manager (Windows/Mac/Linux) - https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md

GitHub Desktop (Windows/Mac/Linux) - https://desktop.github.com/

Visual Studio Code (Windows/Mac/Linux) - https://code.visualstudio.com/download

## Configuration

After installing Git, you will need to open a commandline window such as Git Bash, Command Prompt, Powershell, Terminal, etc. Git Bash comes bundled alongside the Windows installation of Git. You will need to set up your identity, namely an email and username associated with any commits you make with Git.

The following command sets the name you want attached to commits

```
git config --global user.name "your name"
```

Next, set the email associated with your commits. This email does not have to be your GitHub account email, it can be any email you want to use. However, it's recommended to use your GitHub email.

```
git config --global user.email "youraddress@email.com"
```

Now you're set to get started with Git!

## Git Terminology

The following is a short list of terms frequently used when using Git. There are many more but this will be a good starting point.

-   Repository (repo): The directory, located at the top level of a working tree, where Git keeps all the history and metadata for a project. Repositories are almost always referred to as repos.

-   Commit: a Git object, a snapshot of your entire repository compressed into a SHA.

-   Branch: a lightweight movable pointer to a commit.

-   Working Directory: The set of nested directories and files that contain the project that's being worked on.

-   Staging Area: The staging area is a middle ground between what you have done to your files (the working directory) and what you have last committed (the HEAD commit).

-   Local: A repository hosted on a local machine for an individual user.

-   Remote: A remote repository is hosted on a remote (this could be on the internet or an off-site server; it could even be the same machine in a different path) and is shared among multiple team members.

## Initialize or Clone Repositories

To begin, open up a terminal and move to where you want to place the project on your local machine using the cd (change directory) command.

```
cd path/to/project
```

The following commands will initialize an empty repo and add the files in the current directory.

```
git init
git add --all
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/AniTang99/test.git
git push -u origin main
```

The following commands will clone an exisiting repository from GitHub, for example, this repo.

```
git clone https://github.com/AniTang99/intro-to-git.git
```

![Local-Remote](/assets/local-remote.png)

## Simple Git Workflow

![Git stages](/assets/git_stages.png)

First, make the changes to the files you need to work on. Next, add the desired modified files to the staging area or add all using the `--all` flag.

**_NOTE: Use_** `git status` **_at anytime to understand the current state of the repo and working directory._**

```
git add README.md

// or to add all files that changed

git add --all
```

Next, you will need to create a commit object to actually finalize the changes you want and write it to history. The `-m` flag is required to set a message and is highly recommended. If you don't use it, your chosen text editor will open instead and you will be asked to type your message there.

```
git commit -m "Commit message; Make it short but somewhat descriptive"
```

Before sharing your latest changes, you will need to get the latest changes. This will merge your changes with the current state of the branch on the remote repo.

```
git pull
```

Finally, you will push your changes to the remote repo so you can share your changes with your team/mentor. The branch name will be whatever branch you are currently working in, for example, it could be `main`.

```
# This is only necessary on the first push to a branch
git push -u origin branchname

# follwing pushes can simply follow this
git push
```

## Branches as far as the eye can see

Create a copy of the current branch so you don't have to mess with a stable version of the repo. This is the true power of Git!

```
git branch NameOfBranch
git switch NameOfBranch
```

Now you would follow the same flow as you did before to make your changes and commit them. The only change is that you would push to the new branch instead.

```
git push -u origin NameOfBranch
```

![GitHub Flow](/assets/github-flow.png)

## Merge the Branch!

![Merge Conflict](/assets/winter-is-coming-brace-yourself-merge-conflicts-are-coming.webp)

Eventually, you will likely need to merge the branch you created back into the main branch. This is likely the trickiest part of Git but is easy once you understand it!

First, ensure all of your changes are saved and properly committed.

Next, you will switch to the branch you want to merge your changes into, for example, switch to main. **Make sure to ensure you are in the right branch using `git status`.**

```
git switch main
```

Now, you simply merge...

```
git merge NameOfBranch
```

![Fast-Forward Merge](/assets/03-04%20Fast%20forward%20merge.svg)

This will probably work 75% of the time without any conflicts. However, there is a chance that the files you modified were also modified in the branch you are trying to merge with, in fact, this can happen even when you `git pull` to get the latest changes.

These merge conflicts must be resolved and committed before the merge can be completed. The easiest way to resolve the conflicts would be to use an editor like VS Code which provides a 3-way merge editor or you can manually resolve them by using `git status` and modifying all of the files that are conflicted.

![3-way Merge](/assets/05-06%20Fast%20forward%20merge.svg)

Merge conflict demo

```
Modify this line in main and in a second branch and merge
```

## Helpful Commands

Displays the commit history. Flags show different levels of information.

```
git log
git log --oneline
git log --summary
```

This "stashes" the current uncommitted changes to a stack which can be reapplied later.

```
// Stash the changes
git stash

// Apply the changes on the stash
git stash apply

// Remove the changes from the stash and apply them
git stash pop

// Clears all stash entries
git stash clear
```
