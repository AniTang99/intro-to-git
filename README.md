# How to Git Good

![Git_logo](/assets/Git-Logo-2Color.png)

## Introduction

Git is an open source, distributed version-control system (VCS). Essentially, it is a program which tracks changes to a collection of files and and allows multiple users to share and work on files at the same time without affecting each other (mostly).

![Merge Conflicts](/assets/winter-is-coming-brace-yourself-merge-conflicts-are-coming.webp)

## Overview

-   [Installation](#installation)
-   [Configuration](#configuration)
-   [Initialize/Clone Repositories](#initialize-or-clone-repositories)

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

-   Local:

-   Remote:

## Initialize or Clone Repositories

Intentional merge conflict time! Conflict 1
