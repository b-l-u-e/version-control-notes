# Git

Git is a distributed version control system. It tracks changes in any set of computer files, usually used for coordinating work among programmers who are collaboratively developing source code during software development.

## Difference between Git and Text Editor in terms of what they save and their record keeping.

### What they save?

- `Text Editor`: saves all the words in a document as a single file. For example, if you’re writing an essay, the text editor would save your entire essay as `essay.doc`

- `Git`: is a version control system that records differences in files and folders. It doesn’t just save your files, it keeps track of the changes you make to those files. So, if you’re writing code for a software project, Git would help you manage and track changes to your code files over time

### Record keeping

- Text Editor: does not keep a history of changes. If you make changes to a document in a text editor and save it, you won’t be able to revert back to a previous version unless you’ve manually saved different versions of the document.

- Git: keeps a historical record of each save. This means you can easily look at or restore file states from the past. It’s like having a detailed history of every change that’s been made, who made it, and when it was made.


### Does Git work at local or remote level? Both

- `Local Level`: Git is a distributed version control system, which means every Git directory on your computer is a full-fledged repository with complete history and full version-tracking capabilities, independent of network access or a central server. You can make commits, create branches, merge changes, and do almost everything locally without needing to communicate with a remote repository.

- `Remote Level`: While you can work entirely within your local repository, the power of Git comes in its ability to synchronize your work with others. This is where remote repositories come into play. Remote repositories are versions of your project that are hosted on the internet or network somewhere. You can push your local changes to the remote repository to share your work with others, and you can pull their changes from the remote repository to your local repository to keep your local repository up-to-date.

## Some key features of Git:

- `Snapshots, Not Differences`: Unlike most other version control systems (VCSs) that think of the information they store as a set of files and the changes made to each file over time, Git thinks of its data more like a series of snapshots of a miniature filesystem. 

Every time you commit, or save the state of your project, Git takes a picture of what all your files look like at that moment and stores a reference to that snapshot.

- `Nearly Every Operation Is Local`: Most operations in Git need only local files and resources to operate. This means you see the project history almost instantly. If you want to see the changes introduced between the current version of a file and the file a month ago, Git can look up the file a month ago and do a local difference calculation.

- `Collaboration`: Git is used to collaborate on code3. It helps you keep track of code changes3.


## Working with Git

1: Connecting to Github via HTTPS.

- Generate a Personal Access Token.Remember to copy the generated token and make note of it since it will be hidden once leave the page

2: Connecting to Github via SSH.

- Open the terminal

  ```bash
  ssh-keygen -t ed25519 -C "your@email.com"
  ```
- Keys will be generated on stored in .ssh folder
  ```bash
  ls ~/.ssh/
  ```
- To get the public key and add them to github
  ```bash
  cat ~/.ssh/<YOUR KEY>.pub
  ```
- Go to `github` -> `Settings` -> `SSH and GPG keys` -> `create new SSH key` -> `Paste your public key` -> Click `add SSH key`.

## **How git works?**

1: Create a repository and clone repository to your machine.

2: Git work flow: `Modified` -> `staged` -> `committed`

3: Modified: Adding, removing and updating files in the repository

4: Staged: Git to track files needs to be put in staged area: `git add`

5: Committed: Git will save the files and have a snapshot of the changes: `git commit`

6: Remote Repository: Files gets pushed to remote repository. `git push`

7: From remote repository files can be fetched `git fetch`, checked out`git checkout`, merged to working directory `git merge`

8: To unstage the committed files changed

```bash
git restore --staged <file>
```

9: Good practice to check git status to confirm there no pending commits.
```bash
git status
```

10: To create a new branch

```bash
git checkout -B <branch name>
git branch
```

NOTE: ```Git branch``` -> just creates a branch but `Git checkout` -> moves you from main branch to branch that you created.
NOTE: Git branches exist in isolation.Changes need to be merged back to the main branch.

11: How to add files to new branch and push changes

```bash
touch <filename>.txt
git add <filename>.txt
git commit -m "first commit to new branch"
git push -u origin <branch name>
```

NOTE: The purpose of pull request is to obtain a peer review of changes made to the branch.
NOTE: The purpose of push request is it compares a snapshot of your local repository with the remote one and only replaces the files that have been changed.

## Remote vs Local

- Remote refers to any other remote repository to which developers can push changes.
- Local refers to your machine which is accessible by you.
- To specify which branch want to merge with:

  ```bash
  git pull <remote> <branch>
  ```
- To set tracking information for particular branch can do this:

  ```bash
  git branch --set-upstream-to=origin/<branch> master
  ```

## Feature workflow

- Feature branching means you create a new branch from the main line and work on this dedicated branch until the task is completed.

  ```bash
  > git pull
  > git checkout -b feature/<new-branch-name>
  > git add .
  > git add README.md
  > git commit -m 'message'

  > git push -u origin feature/<new-branch-name>
  ```

## HEAD

Its a special pointer which is one of the .git folder.

```bash
cd .git
cat HEAD
cat /refs/heads/main
```

## DIFF commands

`Git status` - shows which files were changed.

`Git diff` - shows what changes were made(commits, branches, individual files)

Example

```bash
ls -la
vim README.md
git diff HEAD README.md
git log --pretty=oneline
git diff <main branch> <another branch>
```

## BLAME

`Git blame` - is used to look at changes of a specific file and shows the dates, time and users who made the changes.

```bash
git blame <file name>
git blame -L 5,15 <file name>
git blame -l <file name>
```

=> Message format

- (Commit ID/Hash -> Author -> Date -> Time -> Line Number -> Content)

```bash
git log -p <Commit ID>
```

## Forking

“***Forking***” in Git refers to creating a copy of an existing repository. 

This is often done when you want to experiment with changes without affecting the original project, or when you want to start your own project based on the code of an existing one.

**Here’s how forking works in Git:**

- `Fork the Repository` : The process begins with an official public repository stored on a server. When a new developer wants to start working on the project, they do not directly clone the official repository. Instead, they fork the official repository to create a copy of it on the server.

- `Clone the Forked Repository` : After they have created their server-side copy, the developer performs a `git clone` to get a copy of it onto their local machine. This serves as their private development environment.

- `Make Changes` : The developer makes changes on their local copy of the repository.

- `Push Changes to the Forked Repository` : When they’re ready to publish a local commit, they push the commit to their own public repository not the official one.

- `Create a Pull Request`: Then, they file a pull request with the main repository, which lets the project maintainer know that an update is ready to be integrated. The pull request also serves as a convenient discussion thread if there are issues with the contributed code.


### Does GitHub work at a local or remote level?

`GitHub` primarily works at a remote level. It is a web-based hosting service for Git repositories. While Git is a distributed version control system that operates on your local machine, GitHub is a platform where you can push your local Git repositories to share your code and collaborate with others.

### Here’s how GitHub works:

- `Remote Storage` : GitHub serves as a remote storage facility for your coding projects. You can push your local Git repositories to GitHub, making it a central place where you and others can access the code.

- `Collaboration`: GitHub facilitates collaboration among developers1. It allows multiple people to work on the same project without overwriting each other’s changes. Developers can clone the remote repository to their local machines, make changes locally, and then push those changes back to the GitHub repository.

- `Version Control`: Like Git, GitHub also provides version control. However, while Git tracks changes on your local machine, GitHub tracks changes that have been pushed to the remote repository. This means you can see the history of changes made to a project on GitHub.