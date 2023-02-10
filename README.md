# Git Basics

## What is Git?

Git is a distributed, open-source version control system. It enables tracking code, merging changes, and reverting to older versions. It is usually used for coordinating work among programmers collaboratively developing source code during software development.

Due to its flexibility and popularity, Git has become an industry standard as it supports almost all development environments, command-line tools, and operating systems. 

For a more detailed history review, the [A Short History of Git](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git) link contains interesting information. Or the [Wikipedia page for Git](https://en.wikipedia.org/wiki/Git).
<br />

## How does Git work?

Git stores files and their history in a local repository. Whenever you save changes you have made, Git creates a commit. A commit is a snapshot of current files. These commits are linked with each other, forming a development history graph. The commits are identified by a unique hash which is used to compare and revert the changes made.  
<br />

### Here is a basic overview of how Git works:

#### Starting a new repository 
1. Create a "repository" 
2. Copy (or clone) the repository to your local machine
3. Add a file to your local repo and "commit" the changes
4. "Push" your changes to your main branch
<br />

#### Starting from an existing repository 
1. "Pull" the changes to your local machine
2. Create a "branch" (version), make a change, commit the change
3. Open a "pull request" (propose changes to the main branch)
4. "Merge" your branch to the main branch
<br />

## The benefits of Git?

-   Track changes: It allows developers to view historical changes. Development history makes it easy to identify and fix bugs.
-   IDE Integration: Due to its popularity, Git integration is available in all development environments, for example VSCode.
-   Team collaboration: A developer team can view their progress, and by using branches, they can work individually on a task and merge changes with the main version. Pull requests, resolving merge conflicts, and code review promote team collaboration.
<br />

## Basic Commands

Let's learn about the most common Git commands that we'll be using. The basic commands include initializing the Git repository, saving changes, checking logs, pushing the changes to the remote server, and merging. 

-   `git init` create a Git repository in a local directory.
-   `git clone` Copy the entire repository from a remote server to remote directory. 
-   `git add` Add a single file or multiple files and folders to the staging area.
-   `git commit –m "Message"` Create a snapshot of changes and save it in the repository. 
-   `git config` uses to set user-specific configurations like email, username, and file format. 
-   `git status` Shows the list of changed files or files that have yet to be staged and committed.  
-   `git push` Send local commits to remote branch of repository.  
-   `git checkout -b <branch-name>` Creates a new branch and switches to a new branch.
-   `git remote –v` view all remote repositories.
-   `git branch –d <branch-name>` Delete the branch.
-   `git pull` Merge commits to a local directory from a remote repository. 
-   `git merge <branch-name>` After resolving merge conflicts the command blends selected branch into the current branch.
-   `git log` show a detailed list of commits for the current branch.

<div style="page-break-after: always"></div>

