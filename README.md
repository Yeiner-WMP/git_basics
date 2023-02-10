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

## Setting Up by Creating a new repository

In this little guide we are going to see how to create a repository using GitHub but this principle also applies to other platforms.

1. In the case of GitHub, in the `Repositories` tab we can see the `New` button to create a new repository.

![GitHub Create Repository](https://www.dropbox.com/s/l985o7lcajj90lo/git_001.png?dl=0&raw=1)

2. Once `New` is selected, the next step is to define the name of the repository, the type of access ( public, private ) and other options for the repository.

![GitHub Create Repository](https://www.dropbox.com/s/46q4257lmjrvpc9/git_002.png?dl=0&raw=1)

3. Continuing with the setup, the next step is to configure the folder in your work environment. For this we will follow the following steps.

- On the command line go to the folder where the project will work.
- We will use the following commands for this initial task.
<br />

**Clone the newly created repository**
```bash
git clone git@github.com:[YOUR_USER]/[your-project].git
```

**Update the local git config if you don't have it configured.**
```bash
git config --local user.email "yaguirre@westmonroe.com"
git config --local user.name "Yeiner Aguirre S."
```

**Create the first file README.md**
```bash
echo "# git-basics" >> README.md
```

**Add file to upload to repository.**
```bash
git add README.md
```

**Create first `commit` to the repository.**
```bash
git commit -m "first commit"
```

**Push the changes to the repository.**
```bash
git push --set-upstream origin readme
```

<div style="page-break-after: always"></div>

# Working with Git
## Git Branches

Branches are most powerful when you're working on a team. You can work on your own part of a project from your own branch, pull updates from your repository, and then merge all your work into the main branch when it's ready.

It is recommended to work with branches: for example, if you want to work on project documentation, create a documentation branch using `git checkout` or `git branch`. Make changes in the README file and when you have finalized the changes, merge the branch with the base.
<br />


```bash
git checkout -b readme
--> Modify file README.md
git add README.md
git commit -m "Git initial document for KT."
git push --set-upstream origin readme
```

![GitHub](https://www.dropbox.com/s/qz3td7cxaswtl5d/git_005.png?dl=0&raw=1)
<br />

<div style="page-break-after: always"></div>

### Pull Request [GitHub]

We will now create pull requests using the GitHub GUI by clicking the `Compare & pull request` button. You can write a detailed explanation of the features that were added and click the pull request button. As the following pictures show.

![GitHub Pull Request](https://www.dropbox.com/s/yvy9ya85qshxb75/git_006.png?dl=0&raw=1)
![GitHub File Diff](https://www.dropbox.com/s/5174t1xm87k2db8/git_007.png?dl=0&raw=1)

<div style="page-break-after: always"></div>

### Merge a pull request [GitHub]

In case all goes well, the next step is to click the "Merge Pull Request" button and congratulations, we have successfully created a pull request and merged it into the `main` branch.

![GitHub Merge](https://www.dropbox.com/s/gxeng406a1509fs/git_008.png?dl=0&raw=1)

<div style="page-break-after: always"></div>

## Git Rebase

Rebasing is the process of moving or combining a sequence of commits to a new base commit.

The primary reason for rebasing is to maintain a linear project history. For example, consider a situation where the main branch has progressed since you started working on a feature branch. You want to get the latest updates to the main branch in your feature branch, but you want to keep your branch's history clean so it appears as if you've been working off the latest main branch.
<br />

**Example:**
****
```bash
git checkout -b new_feature
--> Modify file README.md
echo "# Other MD file." >> Other.md
git add README.md Other.md
git commit -m "New file and possible topics for KT."
git push --set-upstream origin new_feature
```
<br />

```bash
*   3668f59 Merge pull request #1 from Yeiner-WMP/new_feature :: (2023-02-09 | Yeiner-WMP)
|\
| * 4e21758 New file and possible topics for KT. :: (2023-02-09 | Yeiner Aguirre)
|/
| * c1637a8 Git initial document for KT. :: (2023-02-09 | Yeiner Aguirre)
|/
* 105b046 first commit :: (2023-02-09 | Yeiner Aguirre)
```

**Optiomal Path**
```bash
git checkout main
git pull
git checkout readme
git rebase main
git pull 
```

<div style="page-break-after: always"></div>

## What is a Git Merge Conflict?

A `merge conflict` is an event that occurs when Git cannot automatically resolve differences in code between two commits. 

![Git Merge Conflict - ](https://www.dropbox.com/s/z3l9809p94abvg4/git_010.png?dl=0&raw=1)


```bash
$ git rebase main
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
error: could not apply c1637a8... Git initial document for KT.
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply c1637a8... Git initial document for KT.
```

The easiest way to solve a conflicted file is to open it and make any necessary changes. To help identify the differences between the state of repositories or files Git provides the `git diff` command.

```bash
git diff
nano README.md
git add README.md
git rebase --continue
git pull
git push
```

<div style="page-break-after: always"></div>

##  Squash Your Commits

`Squashing` your commits means that you combine multiple existing commits into a single one. There are different ways and tools when it comes to squashing commits. **Interactive Rebase** and **Merge** are the two main ways to squash commits.
<br />

### Interactive Rebase 

By starting an Interactive Rebase session and typing `git rebase -i HEAD~3` you can perform the action. It is important to remember that to push the changes to the branch after a rebase, you need to `force push` your commits using the `-f` or `--force` flag in the `git push` command on Git.
<br />

```bash
# Rebase and Squash extra commits.
git rebase -i HEAD~3
git pull
git push -f 
```


### Merge

Squashing is also an option when merging branches
<br />

```bash
git merge --squash main

Squash commit -- not updating HEAD Automatic merge went well; stopped before committing as requested
```

<div style="page-break-after: always"></div>

### Pull Requests

This strategy - using squash when merging - is often used when a Pull Request is closed. Code hosting platforms like GitHub, GitLab, or Bitbucket support this as an option when merging a Pull Request:
<br />

![GitHub Squash Merge](https://www.dropbox.com/s/ib0p639o44x03ge/git_014.png?dl=0&raw=1)

<div style="page-break-after: always"></div>

##  Other Git Commands to Know

### Git Stash

`git stash` temporarily shelves (or _stashes_) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on.

**How to use git stash**

The following is an example of how git stash is used:

```bash
# Asume you are woring in branch A and needs to work in 
# another branck to do a quick fix.
$ git stash

# You complete the work in the other branch and return to 
# your previous branch and need to continue your "stashed"
# work to get your stashed changes back run.
$ git stash pop
```
<br/>

### Git Cherry Pick

Cherry picking is the act of picking a commit from a branch and applying it to another.

`git cherry-pick` is a powerful command that enables arbitrary Git commits to be picked by reference and appended to the current working HEAD. 

Cherry picking can cause duplicate commits and many scenarios where cherry picking would work, traditional merges are preferred instead.

Command uses:

```bash
git cherry-pick af02e0b
git cherry-pick af02e0b --no-commit
```

<div style="page-break-after: always"></div>

# Resources to consider

1. [What is Git](https://www.atlassian.com/git/tutorials/what-is-git)
2. [Getting Git Right](https://www.atlassian.com/git)
3. [Git Documentation](https://git-scm.com/doc)
4. [Git Cheat Sheet :: English](https://training.github.com/downloads/github-git-cheat-sheet.pdf)
5. [Hoja de referencia para Git :: Español](https://training.github.com/downloads/es_ES/github-git-cheat-sheet.pdf)
