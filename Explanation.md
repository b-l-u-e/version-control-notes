# Version control

Version control is the system that records all changes and modifications to files for tracking process.
Developers use the term source code or source code management.
Control systems available are centralized and distributed systems.
There are different types of changes: Add files; Modify or update files and deleting files.

## Goal:

Keep track of changes.
allow developers to access the history with the ability revert and roll back to the previous state

## Benefits of version control:

Revision history, Identity, Collaboration, Automation and Efficiency.

- Revision history provides a record of all changes in a project. It provides developers with the ability to revert to a stable point in time in cases where code edits cause issues or bugs. The ability to roll back to particular version or time allows teams to work faster and deliver code with more confidence.

- Identity provides all changes made are always recorded with the identity of the user that made them.

- Combining revision history and identity allows teams to see not only when the changes occured, but also who made the changes. Collaboration is important for developers work in a team.

- Automation delivering software in a wide scale is complex and time consuming hence version control helps keep track of all changes.It plays an integral role in the explosion of development operations.Devops is a set of practices, philosophies and tools that increase an organizations ability to deliver applications or services to a high quality and velocity.

- Efficiency team need to work efficiently so as to make the project a success.Team may work in processes from the agile methodology.

**Another aspect of version control is peer review.**

- Developers working on a task create a peer review once the code is ready for inspection.The peer review aims to get other developers on your team to review the code and provide feedback where necessary
- Version control for instagram use monolithic repository. Other companies use smaller repository called mirco-services for each item have their own code base.

**_Different version control systems: Subversion, Perforce, AWS Code Commit, Mercurial, Git_**

**Version control can be split into two types or categories: Centralized version and Distributed version**

### Centralized Version Control Systems (CVCS)

- Contain a server and client. The server contains the main repository that houses the full history of versions of the code base.Developers need to pull the request from server to their local machine.This gives the user their own working copy of the code base.The server holds the full history of changes.The client has the latest code, but every operation needs a connection to a server
- The server is the central copy of the project.After making changes to the code, the developer needs to push the changes to the central server so that other developers can see them.

### Distributed Version Control Systems (DVCS)

- Similar to the centralized model, still need to pull code down from server to view the latest changes.The difference **Every user is essentially a server and not a client**. This means every time pull request you have the entire history of the changes in local system

* Adv of CVCS: Easier to learn, More access controls to users
* Disadv of CVCS: Can be slower to estabilish connection to the server to perform any actions

* Adv of DVCS: Allow users to work in an offline state, Speed and performance are better

## A history of version control

- **_Concurrent Version System(CVS)_** - it was first developed in 1986 by Walter F.Tichy at Purdue university and released in 1990.
- CVS stores information about every file in a folder structure, including name of the file, its location in the folder structure, who last modified it, and when it was modified. However doesnt include integrity checks meaning data can become corrupted.When you update or submit changes if an error occurs the system accepts the partial or corrupted files.Additionally the system was designed mainly for text files not binary files such as images or videos.

- The Successor to CVS was **_Subversion(SVN)_** - CollabNet developed it in 2000 and included integrity checks.It supported the versioning of binary files better.It became popular in open source community with free hosting being offered for open source projects by Google and SourceForge.

- SVN used a **_ centralized VCS model _**. This means that all operations have to be done using a centralized server. If the server were down or slow, this would impede development.

- In 2005, two new projects started to develop distributed version control systems; Mercurial and Git.Both projects were created in response to an event involving the Linux Kernel development.

- Previously the Linux Kernel was using a proprietary VCS known as BitKeeper.BitKeeper was one of the first distributed version control systems intially released in 2000.Bitkeeper originally provided a free license to Linux Torvalds to support Linux's development.In 2005, the license was revoked hence led to Mercurial and Git projects.

- Mercurial was developed by Olivia Mackal. It developed as a high performance **_ distributed VCS _**. Many platforms offered Subversion hosting began to offer Mercury hosting too.It was found easy to transtion to mercurial repository by Subversion users.

- Git was developed by Linux Torvalds to host the Linux kernel's source code.Like Mercurial, it is **_ distributed VCS _**.It's first public release came in 2007.

- Git became popular in the open-source community due to its distributed VCS design and Github offering free Git hosting for open-source projects.

* Using version control needs a proper workflow to ensure code is managed correctly and reduce mistakes from happening.

**Continuous Integration** is used to automate the integration of code changes from multiple developers into a single main stream.Using workflow whereby small changes are merged frequently often many times per day will reduce the number of merge conflicts.

This process is widespread in test-driven software development strategies.CI is used to automatically compile the project and run tests on every code change to ensure that the build remains stable and prevent regressions in functionality.

**Continuous Delivery** is an extension of continuous integration.Once changes have been merged into the main stream, a continous delivery system automatically packages the application and prepares it for deployment.This helps avoid human error when packaging the application.

**Continuous Deployment** is an extension of continuous delivery.The goal is to deploy and release software to customers frequently and safely.

The strategy commonly involves automatically deploying to a test(also known as staging) environment first to validate the deployment package and software changes. Once validated, it can automatically deploy to the live(also known as production) environment for customers.

History of revisions

- **_Who made the change?_**
- **_What was the reason?_**
- **_Whats changed?_**
- **_When did it happen?_**

## Staging vs. Production

- Every development team needs to verify that the code they release is not going to cause any issues or bugs.
  -They set up different environments for different ways to test and verify.Common practice: Developer enivironment, a UAT or QA environment and staging environment

**Staging** environment should mimic your production environment.

- Reason: You want to test code in an environment that matches what you have in production.This allows teams to spot or find any potential issues prior to them getting to production.
- Staging env can be used for testing and verifying new features and allow other teams including QA or stakeholders to see and use those features as a pre-trial.
- Staging should cover all areas of architecture of the application including the database and any other services that may be required.
- Areas that benefit from staging environments include:

**_New features_** Developers submitting new features along with feature flags for turning them on and off should always do a testing round in a staging environment.They allow teams to verify that the feature works.It can be turned on and off via configuration flags and also that it does not break or interfere with existing functionality.

**_Testing_** QA teams will use it verify new features, configuration changes or software updates/patching.The types of testing covered will be unit testing, integration testing and performance testing.All except performance testing can be carried out in production.

**_Configuration Changes_** Configuration can cause headaches for teams esp in large cloud based architecture.Having staging environment will allow you to spot any potential issues or bottlenecks.

**Production**

- Production is live.Any issues or problems you may have should have been caught and fixed in the staging environment.The staging area gives the team a safety net to catch possible issues.

**_Downtime_** Downtime for any service especially customer facing will most likely be revenue impacting. For example customers cannot access website.

**_Vulnerabilities_** Cybersecurity should play a big role in what gets released in production.Any updates such as patching or moving to the latest version should be checked and verified.

**_Reputation_** Downtime or issues in production is damaging for a company as it does not instill confidence in end users. If something is down or broken it can cause the company to lose potential customers.

# Unix Commands

Change to Desktop directory

```
cd ~/Desktop
```

Create folder and change to folder directory

```
mkdir myproject && cd myproject
```

Create file and open file

```
touch index.js && code index.js
```

Bash commands

```
cd - Change directory.
ls - List command used for showing the content of a directory.
rm - Remove command used for removing file or a directory.
mv - Used to move files or folders to another location.
touch - Allows creating of a new empty file or to update timestamp on a file.
cp - Used to make a copy of a file or folder.
mkdir - Make a new directory.
pwd - Print work directory, shows the current location in the shell.
cat - Allows reading or concatentation of a file.
wc - word count eg. wc file1.txt -w
less - Displays the contents of a file one page at a time.
grep - Global regular expression, allows for searchinf contents of files or folders.
```

Every bash command has flags which allow you to change the output of the command itself.

The man pages great way to recall the different flags that are available.

To edit files in bash usually can use VI or Vim. VI stands for visual editor and it allows you to make edits and changes to a file and save them.Vim is better version of VI.

Vim uses modes to determine commands you can work with:

```
Normal mode: default mode
Insert mode: Allows the contents of the files to be edited
Command line mode: Normal commands begin with :
```

Note:
Using Git Bash on Windows

```
bashrc file is mainly for configurations.It is essentially a script file that's executed when first open the terminal window.

Use command less .bashrc

bash_profile file is used more for env variables example can use it for setting env variables for my java home directory or python home directory.

Use command less .bash_profile
```

**_Create a simple shell script_**

> Use Vim and create new file "testshell.sh

```
vim testshell.sh
```

> At the top of the file put in what type of file want it to be in this case its going to be a bash file

```
> Press "i" on your keyboard it will set to INSERT MODE

#!/bin/bash (This lets the operating system know that it is a bash script)
```

> Edit the file

```
echo "Hello world!"
```

> To save the file

```
:wq! then press enter
```

> To check the file

```
ls -la
```

> Notice: The file cannot be run at the moment or not executable since its just a read write file. Hence we want the file to be executable (rwx)

```
chmod 755 testshell.sh && ls -la
```

> After command above we can run the file from command line.To run a file

```
./testshell.sh
```

## Pipes

A coding tool that allows the output of one command to be used as the input for a different command

```
Examples:
ls | wc -w
cat file1.txt | wc -w
cat file1.txt file2.txt | wc -w
```

## Redirection

There are 3 types of redirection:
std input, std output and std err.

**_std input_** - represented by 0. The redirection input gives you the option to record your input and save it to a file either by overwriting or appending the file.

- How to take input?

```
cat > input.txt (Add the text to file and press Ctrl + d)
```

- How to output the content in the file?

```
cat < input.txt
```

**_std output_** - represented by 1. The redirection output allows you to control where the output goes.

```
ls -l > output.txt
ls
less output.txt
```

**_std error_** - represented by 2. Allows you to specify that the error should be written to file.

```
2> - to print error
2>&1 - to print both std output and error
```

```
Note:
< input.txt >output.txt 2>error.txt
```

```
Example:
ls -l /bin/usr > error.txt

ls -l /bin/usr 2> error.txt
less error.txt

ls -l /bin/usr > error_output.txt 2>&1
less error_output.txt
```

## Grep

Global regular expression print.

Used to search across files or folders as well contents in files

grep is case-sensitive

```
Eg: grep sam names.txt
```

To ignore case sensitive

```
Eg: grep -i Sam names.txt
```

To look for exact word example sam

```
grep -w Sam names.txt
```

Search across different directories

```
ls /bin | grep zip
```

# Working with Git

1: Connecting to Github via HTTPS.

- Generate a Personal Access Token.Remember to copy the generated token and make note of it since it will be hidden once leave the page

2: Connecting to Github via SSH.

- Open the terminal
  ```
  ssh-keygen -t ed25519 -C "your@email.com"
  ```
- Keys will be generated on stored in .ssh folder
  ```
  ls ~/.ssh/
  ```
- To get the public key and add them to github
  ```
  cat ~/.ssh/<YOUR KEY>.pub
  ```
- Go to github -> Settings -> SSH and GPG keys -> create new SSH key -> Paste your public key -> Add SSH key.

## **How git works?**

1: Create a repository and clone repository to your machine.

2: Git work flow: **Modified -> staged -> committed**

3: Modified: Adding, removing and updating files in the repository

4: Staged: Git to track files needs to be put in staged area **_(git add)_**

5: Committed: Git will save the files and have a snapshot of the changes.**_(git commit)_**

6: Remote Repository: Files gets pushed to remote repository.**_(git push)_**

7: From remote repository files can be fetched(**_git fetch_**),checked out(**_git checkout_**), merged to working directory(**_git merge_**)

8: To unstage the committed files changed

```
git restore --staged <file>
```

9: Good practice to check git status to confirm there no pending commits.

10: To create a new branch

```
git checkout -B <branch name>
git branch
```

NOTE: **Git branch** -> just creates a branch but **Git checkout** -> moves you from main branch to branch that you created.
NOTE: Git branches exist in isolation.Changes need to be merged back to the main branch.

11: How to add files to new branch and push changes

```
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
  ```
  git pull <remote> <branch>
  ```
- To set tracking information for particular branch can do this:
  ```
  git branch --set-upstream-to=origin/<branch> master
  ```

## Feature workflow

- Feature branching means you create a new branch from the main line and work on this dedicated branch until the task is completed.

  ```
  > git pull
  > git checkout -b feature/<new-branch-name>
  > git add .
  > git add README.md
  > git commit -m 'message'

  > git push -u origin feature/<new-branch-name>
  ```

## HEAD

Its a special pointer which is one of the .git folder.

```
cd .git
cat HEAD
cat /refs/heads/main
```

## DIFF commands

Git status - shows which files were changed
Git diff - shows what changes were made(commits, branches, individual files)

Example

```
ls -la
vim README.md
git diff HEAD README.md
git log --pretty=oneline
git diff <main branch> <another branch>
```

## BLAME

Git blame - is used to look at changes of a specific file and shows the dates, time and users who made the changes.

```
git blame <file name>
git blame -L 5,15 <file name>
git blame -l <file name>
```

=> Message format

- (Coomit ID/Hash -> Author -> Date -> Time -> Line Number -> Content)

```
git log -p <Commit ID>
```

## Forking
To be continued...