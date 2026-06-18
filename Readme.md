# Git and GitHub Complete Beginner Notes

A practical, beginner-friendly guide to Git and GitHub. It covers account creation, laptop configuration, cloning, adding files, committing, pushing, pulling, branching, merging, undoing mistakes, collaboration, and common errors.

Every important command includes:

- What the command does
- What each word or symbol means
- A simple real-life example
- A practical coding example

> These notes focus on the Git commands developers use regularly. Git has many specialized commands, but the commands here cover the complete everyday workflow.

---

## Table of Contents

1. [Git and GitHub in Simple Words](#1-git-and-github-in-simple-words)
2. [Real-Life Git Analogy](#2-real-life-git-analogy)
3. [Important Git Words](#3-important-git-words)
4. [Create a GitHub Account](#4-create-a-github-account)
5. [Install Git](#5-install-git)
6. [Configure Git on Your Laptop](#6-configure-git-on-your-laptop)
7. [Connect Your Laptop to GitHub with SSH](#7-connect-your-laptop-to-github-with-ssh)
8. [Basic Terminal Commands](#8-basic-terminal-commands)
9. [Create a Repository on GitHub](#9-create-a-repository-on-github)
10. [Workflow 1: Upload an Existing Local Project](#10-workflow-1-upload-an-existing-local-project)
11. [Workflow 2: Clone an Existing GitHub Repository](#11-workflow-2-clone-an-existing-github-repository)
12. [The Everyday Git Workflow](#12-the-everyday-git-workflow)
13. [Understand git status](#13-understand-git-status)
14. [Understand git add](#14-understand-git-add)
15. [Understand git commit](#15-understand-git-commit)
16. [Understand git push](#16-understand-git-push)
17. [Understand git pull](#17-understand-git-pull)
18. [Understand git fetch](#18-understand-git-fetch)
19. [Branches](#19-branches)
20. [Switch Between Branches](#20-switch-between-branches)
21. [Merge Branches](#21-merge-branches)
22. [Merge Conflicts](#22-merge-conflicts)
23. [View Changes and History](#23-view-changes-and-history)
24. [Undo Changes Safely](#24-undo-changes-safely)
25. [Git Stash](#25-git-stash)
26. [Delete and Rename Files](#26-delete-and-rename-files)
27. [Remote Repository Commands](#27-remote-repository-commands)
28. [.gitignore](#28-gitignore)
29. [Forks and Pull Requests](#29-forks-and-pull-requests)
30. [Tags and Releases](#30-tags-and-releases)
31. [Rebase in Simple Words](#31-rebase-in-simple-words)
32. [Useful Advanced Commands](#32-useful-advanced-commands)
33. [Common Errors and Solutions](#33-common-errors-and-solutions)
34. [Commands That Need Extra Care](#34-commands-that-need-extra-care)
35. [Complete Practical Workflows](#35-complete-practical-workflows)
36. [Git Command Cheat Sheet](#36-git-command-cheat-sheet)
37. [Git Glossary](#37-git-glossary)
38. [Official References](#38-official-references)

---

# 1. Git and GitHub in Simple Words

## What is Git?

**Git** is a version control system installed on your computer.

It remembers changes made to your project. It lets you:

- Save checkpoints of your work
- See what changed
- Restore an older version
- Create separate branches
- Combine work from different developers
- Keep a complete project history

### Simplest real-life example

Imagine writing an assignment.

Without Git, you may create files like:

```text
assignment-final.docx
assignment-final-2.docx
assignment-final-really-final.docx
assignment-final-last.docx
```

With Git, you keep one project folder. Git records each meaningful version as a **commit**.

---

## What is GitHub?

**GitHub** is an online platform that stores Git repositories.

It helps you:

- Keep an online backup of code
- Share projects
- Work with a team
- Review changes
- Create issues and pull requests
- Show projects on your developer profile

### Simplest real-life example

Git is the notebook on your desk.

GitHub is the secure online locker where you keep a copy of that notebook.

---

## Git vs GitHub

| Git | GitHub |
|---|---|
| A version control tool | An online Git hosting platform |
| Installed on your laptop | Accessed online |
| Tracks local changes | Stores repositories online |
| Works without internet for local actions | Requires internet for online actions |
| Uses commands such as `git add` | Provides repositories, pull requests, issues, and actions |

---

# 2. Real-Life Git Analogy

Imagine that you are writing a book with friends.

| Git concept | Real-life meaning |
|---|---|
| Repository | The complete book project |
| Working directory | Your writing desk |
| File change | Editing a page |
| Staging area | Selecting pages for the next saved edition |
| Commit | Saving a named edition |
| Commit message | A note explaining what changed |
| Remote repository | The online master copy |
| Clone | Taking a complete copy of the book |
| Push | Sending your saved editions to the online copy |
| Pull | Receiving the newest editions from the online copy |
| Branch | Writing an experimental chapter separately |
| Merge | Adding the experimental chapter to the main book |
| Conflict | Two people changed the same sentence differently |
| Stash | Keeping unfinished pages temporarily in a drawer |
| Tag | Placing a permanent bookmark on an important edition |
| Fork | Making your own online copy of another person's book |
| Pull request | Asking the owner to accept your changes |

---

# 3. Important Git Words

## Repository

A **repository**, often called a **repo**, is a project tracked by Git.

It contains:

- Project files
- Commit history
- Branches
- Git configuration
- Remote connection information

---

## Local repository

A repository stored on your laptop.

Example:

```text
/home/tushar/projects/portfolio
```

---

## Remote repository

A repository stored on GitHub or another Git hosting service.

Example:

```text
github.com/username/portfolio
```

---

## Working directory

The project files you currently see and edit.

Real-life example: the papers currently lying on your desk.

---

## Staging area

A temporary area where you select changes for the next commit.

Real-life example: placing selected products into a shopping basket before billing.

---

## Commit

A saved snapshot of staged changes.

Real-life example: taking a photograph of your project at a particular moment.

---

## Branch

A separate line of development.

Real-life example: making a copy of a drawing so you can try a new design without damaging the original.

---

## Main branch

The primary branch of a repository. It is normally named:

```text
main
```

---

## Remote

A saved connection from your local repository to an online repository.

---

## Origin

`origin` is the conventional default name for the remote repository you cloned or connected.

It is only a nickname. You could use another name, but `origin` is the standard.

---

## Upstream

An **upstream branch** is the remote branch connected to your local branch.

Example:

```text
Local branch:  main
Remote branch: origin/main
```

---

## HEAD

`HEAD` points to the branch and commit you currently have checked out.

Real-life example: the page your bookmark currently points to.

---

# 4. Create a GitHub Account

1. Open GitHub.
2. Select **Sign up**.
3. Enter your email address.
4. Create a strong password.
5. Choose a professional username.
6. Complete verification.
7. Verify your email address.
8. Sign in.

A user account is your personal identity on GitHub. Your repositories, issues, commits, and pull requests can be associated with it.

Example username:

```text
Tusharxhub
```

Example profile address:

```text
https://github.com/Tusharxhub
```

## Improve your profile

Add:

- A clear profile photo
- Your full name
- A short developer bio
- Your location
- Portfolio website
- Skills
- Pinned repositories
- A profile README

To create a profile README, create a public repository with exactly the same name as your GitHub username.

Example:

```text
Username: Tusharxhub
Repository: Tusharxhub
```

Then add a `README.md` file inside it.

---

# 5. Install Git

## Fedora Linux

```bash
sudo dnf install git
```

### Every word explained

- `sudo`: run the command with administrator permission
- `dnf`: Fedora's package manager
- `install`: install a package
- `git`: the package to install

### Real-life example

`sudo` is like asking the house owner for permission to install a new machine.

---

## Ubuntu or Debian

```bash
sudo apt update
sudo apt install git
```

### Every word explained

First command:

- `sudo`: administrator permission
- `apt`: Ubuntu or Debian package manager
- `update`: refresh the list of available software

Second command:

- `install`: install software
- `git`: the software name

---

## Arch Linux

```bash
sudo pacman -S git
```

- `pacman`: Arch Linux package manager
- `-S`: synchronize and install a package
- `git`: package name

---

## Windows

Install **Git for Windows**, then use one of these terminals:

- Git Bash
- PowerShell
- Command Prompt
- VS Code terminal

The default installation choices are suitable for most beginners.

---

## macOS

Using Homebrew:

```bash
brew install git
```

Or install Apple's command-line tools:

```bash
xcode-select --install
```

---

## Check the installation

```bash
git --version
```

Example output:

```text
git version 2.52.0
```

### Every word explained

- `git`: run the Git program
- `--version`: display the installed version
- `--`: usually begins a long-form option

---

# 6. Configure Git on Your Laptop

Git adds your name and email to every commit.

## Set your name

```bash
git config --global user.name "Tushar Kanti Dey"
```

### Every word explained

- `git`: run Git
- `config`: read or change Git settings
- `--global`: apply the setting to your user account on this laptop
- `user.name`: the setting that stores the commit author's name
- `"Tushar Kanti Dey"`: the value saved in that setting
- Quotes keep words with spaces together as one value

---

## Set your email

```bash
git config --global user.email "your-email@example.com"
```

Use an email address connected to your GitHub account.

### Every word explained

- `user.email`: the commit author's email setting
- `"your-email@example.com"`: the email value

---

## Set `main` as the default branch name

```bash
git config --global init.defaultBranch main
```

### Meaning

When you run `git init`, Git will name the first branch `main`.

---

## Check all global settings

```bash
git config --global --list
```

### Every word explained

- `--global`: read global settings
- `--list`: display all matching settings

---

## Check one setting

```bash
git config user.name
git config user.email
```

---

## Understand configuration levels

| Level | Command option | Where it applies |
|---|---|---|
| System | `--system` | Every user on the computer |
| Global | `--global` | Your user account |
| Local | `--local` | Only the current repository |

A local setting overrides a global setting.

Example:

```bash
git config --local user.email "college-email@example.com"
```

This email is used only inside the current repository.

---

# 7. Connect Your Laptop to GitHub with SSH

SSH lets your laptop securely authenticate with GitHub.

After setup, you can push and pull without entering your GitHub password for every command.

## Important idea

SSH uses two keys:

| Key | Purpose |
|---|---|
| Private key | Secret key stored only on your laptop |
| Public key | Key added to your GitHub account |

Never share your private key.

Real-life example:

- Public key: a lock that anyone may see
- Private key: the only key that can open that lock

---

## Step 1: Check for existing SSH keys

```bash
ls -al ~/.ssh
```

### Every word and symbol explained

- `ls`: list files and folders
- `-a`: include hidden files
- `-l`: show detailed information
- `-al`: combines `-a` and `-l`
- `~`: your home directory
- `/`: separates directory names
- `.ssh`: hidden folder containing SSH files
- A name beginning with `.` is hidden on Linux and macOS

Look for files such as:

```text
id_ed25519
id_ed25519.pub
```

---

## Step 2: Generate a new SSH key

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

### Every word explained

- `ssh-keygen`: generate an SSH key pair
- `-t`: specify the key type
- `ed25519`: a modern key algorithm
- `-C`: add a comment
- `"your-email@example.com"`: comment used to identify the key

Press Enter to accept the default file location.

You may set a passphrase for extra security.

---

## Step 3: Start the SSH agent

```bash
eval "$(ssh-agent -s)"
```

### Every word and symbol explained

- `ssh-agent`: a program that securely holds unlocked SSH keys
- `-s`: print commands using shell syntax
- `$()`: run the command inside and use its output
- `eval`: execute that generated shell output
- Quotes preserve the output as one expression

---

## Step 4: Add your private key to the agent

```bash
ssh-add ~/.ssh/id_ed25519
```

### Meaning

- `ssh-add`: add a private key to the running SSH agent
- `~/.ssh/id_ed25519`: path to your private key

Do not upload this private key anywhere.

---

## Step 5: Display your public key

```bash
cat ~/.ssh/id_ed25519.pub
```

### Every word explained

- `cat`: print a file's content in the terminal
- `.pub`: indicates the public key file

Copy the complete output.

---

## Step 6: Add the key to GitHub

In GitHub:

1. Open your profile menu.
2. Open **Settings**.
3. Open **SSH and GPG keys**.
4. Select **New SSH key**.
5. Enter a title, such as `Fedora Laptop`.
6. Paste the public key.
7. Save it.

---

## Step 7: Test the connection

```bash
ssh -T git@github.com
```

### Every word and symbol explained

- `ssh`: open an SSH connection
- `-T`: disable a normal interactive shell
- `git`: GitHub's SSH user
- `@`: connects a username to a host
- `github.com`: GitHub's host name

A successful result says that authentication succeeded.

---

## HTTPS alternative

You may clone using an HTTPS URL:

```bash
git clone https://github.com/username/project.git
```

GitHub does not accept your normal account password for Git command authentication. Use a supported authentication method such as:

- Git Credential Manager
- Browser authentication
- GitHub CLI
- Personal access token

SSH is convenient for regular development.

---

# 8. Basic Terminal Commands

Before using Git, understand these basic terminal commands.

## Show the current directory

```bash
pwd
```

- `pwd`: print working directory

Real-life example: asking, “Which room am I currently standing in?”

---

## List files

```bash
ls
```

- `ls`: list directory contents

Detailed list:

```bash
ls -la
```

- `-l`: long, detailed view
- `-a`: include hidden files

---

## Enter a directory

```bash
cd projects
```

- `cd`: change directory
- `projects`: directory to enter

Real-life example: walking into the `projects` room.

---

## Go to the parent directory

```bash
cd ..
```

- `..`: the parent directory, one level above

---

## Go to your home directory

```bash
cd ~
```

- `~`: your home directory

---

## Create a directory

```bash
mkdir my-project
```

- `mkdir`: make directory
- `my-project`: new directory name

---

## Create an empty file

```bash
touch README.md
```

- `touch`: create an empty file, or update its timestamp
- `README.md`: file name
- `.md`: Markdown file extension

---

## Open the current folder in VS Code

```bash
code .
```

- `code`: VS Code command-line program
- `.`: the current directory

Here, `.` means “this folder.”

---

## Clear the terminal

```bash
clear
```

Keyboard shortcut:

```text
Ctrl + L
```

---

# 9. Create a Repository on GitHub

1. Sign in to GitHub.
2. Select the `+` button.
3. Select **New repository**.
4. Enter a repository name.
5. Add an optional description.
6. Choose **Public** or **Private**.
7. Optionally add:
   - README
   - `.gitignore`
   - License
8. Select **Create repository**.

## Public repository

Anyone can view the repository.

## Private repository

Only you and authorized collaborators can view it.

## Naming example

Good:

```text
project-aegis
```

Avoid:

```text
My New Final Project 2026!!!
```

Simple repository names are easier to use in URLs and terminals.

---

# 10. Workflow 1: Upload an Existing Local Project

Use this workflow when a project already exists on your laptop but is not yet tracked by Git.

Assume your project folder is:

```text
portfolio
```

## Step 1: Enter the project

```bash
cd portfolio
```

---

## Step 2: Initialize Git

```bash
git init
```

### Every word explained

- `git`: run Git
- `init`: initialize a new Git repository

Git creates a hidden `.git` directory.

### Real-life example

You already have a notebook. `git init` adds a version-history system to it.

Do not manually edit or delete `.git` unless you understand the effect.

---

## Step 3: Check the repository

```bash
git status
```

Git shows untracked, modified, and staged files.

---

## Step 4: Create `.gitignore` before adding files

Example for Node.js:

```gitignore
node_modules/
.env
.next/
dist/
coverage/
*.log
```

This prevents private or generated files from being committed.

---

## Step 5: Stage the files

```bash
git add .
```

### Every word and symbol explained

- `git`: run Git
- `add`: add changes to the staging area
- `.`: all relevant changes under the current directory

---

## Step 6: Create the first commit

```bash
git commit -m "Initial project setup"
```

### Every word explained

- `commit`: save the staged snapshot
- `-m`: provide the commit message directly
- `"Initial project setup"`: description of the saved change

---

## Step 7: Make sure the branch is named `main`

```bash
git branch -M main
```

### Every word explained

- `branch`: manage branches
- `-M`: rename the branch, even if the target name already exists
- `main`: the new branch name

---

## Step 8: Connect the GitHub repository

Using SSH:

```bash
git remote add origin git@github.com:username/repository.git
```

### Every word explained

- `remote`: manage online repository connections
- `add`: add a new connection
- `origin`: nickname for the connection
- `git@github.com:username/repository.git`: SSH address of the GitHub repository

Using HTTPS:

```bash
git remote add origin https://github.com/username/repository.git
```

---

## Step 9: Verify the remote

```bash
git remote -v
```

### Meaning

- `-v`: verbose, show detailed remote addresses

You normally see one URL for fetching and one for pushing.

---

## Step 10: Push the project

```bash
git push -u origin main
```

### Every word explained

- `push`: upload local commits
- `-u`: set the upstream tracking connection
- `origin`: remote name
- `main`: local branch to push

After the first push, you can normally use:

```bash
git push
```

---

## Complete command sequence

```bash
cd portfolio
git init
git status
git add .
git commit -m "Initial project setup"
git branch -M main
git remote add origin git@github.com:username/repository.git
git push -u origin main
```

---

# 11. Workflow 2: Clone an Existing GitHub Repository

Use cloning when the repository already exists online.

## Clone with SSH

```bash
git clone git@github.com:username/repository.git
```

## Clone with HTTPS

```bash
git clone https://github.com/username/repository.git
```

### Every word explained

- `git`: run Git
- `clone`: create a local copy of a remote repository
- URL: address of the repository

### What clone does

`git clone` normally:

1. Creates a new folder
2. Downloads project files
3. Downloads Git history
4. Creates the `origin` remote
5. Checks out the default branch
6. Connects the local default branch to its remote branch

### Real-life example

Cloning is not downloading only the latest page. It is receiving the book, its current pages, and its saved history.

---

## Clone into a custom folder name

```bash
git clone git@github.com:username/repository.git my-folder
```

- `my-folder`: name of the new local directory

---

## Enter the cloned repository

```bash
cd repository
```

---

## Check its remote

```bash
git remote -v
```

---

## Check its branches

```bash
git branch -a
```

- `-a`: show local and remote-tracking branches

---

# 12. The Everyday Git Workflow

The most common daily sequence is:

```bash
git pull
git status
git add .
git commit -m "Describe the change"
git push
```

## What happens in simple words

1. `git pull`: receive the team's latest saved work
2. `git status`: inspect your current situation
3. Edit project files
4. `git add .`: select your changes
5. `git commit`: save a local checkpoint
6. `git push`: upload your checkpoint

## Real-life example

A shared class notebook:

1. Collect the newest pages from classmates
2. Check your pages
3. Write your section
4. Select the finished pages
5. Save them as an edition
6. send them to the shared notebook

---

# 13. Understand `git status`

```bash
git status
```

Shows:

- Current branch
- Whether your branch is ahead or behind
- Untracked files
- Modified files
- Staged files
- Merge conflicts

### Real-life example

`git status` is like checking a task board before deciding the next action.

---

## Short status

```bash
git status -s
```

- `-s`: short format

Example:

```text
 M src/app.js
A  README.md
?? notes.txt
```

Possible meanings:

| Code | Meaning |
|---|---|
| `??` | Untracked file |
| `M` | Modified file |
| `A` | Added file |
| `D` | Deleted file |
| `R` | Renamed file |
| `U` | Unmerged conflict |

The two columns represent staging-area status and working-directory status.

---

# 14. Understand `git add`

`git add` moves selected changes into the staging area.

## Stage one file

```bash
git add README.md
```

---

## Stage multiple named files

```bash
git add README.md package.json src/app.js
```

Spaces separate command arguments.

---

## Stage all changes under the current directory

```bash
git add .
```

- `.`: current directory

---

## Stage all changes in the repository

```bash
git add -A
```

- `-A`: stage added, modified, and deleted files everywhere in the repository

---

## Stage only tracked modified and deleted files

```bash
git add -u
```

- `-u`: update already tracked files
- New untracked files are not staged

---

## Select parts of a file interactively

```bash
git add -p
```

- `-p`: patch mode

This lets you stage only selected parts of changed files.

---

## Unstage a file

```bash
git restore --staged README.md
```

This removes the file from the staging area but keeps its changes in your working directory.

### Every word explained

- `restore`: restore file content or staging state
- `--staged`: apply the action to the staging area
- `README.md`: target file

---

## Real-life staging example

You changed three files:

```text
login.js
navbar.js
README.md
```

Only the login feature is ready.

Use:

```bash
git add login.js
git commit -m "Add login validation"
```

Do not include unrelated unfinished changes in the same commit.

---

# 15. Understand `git commit`

A commit records staged changes in local history.

## Create a commit

```bash
git commit -m "Add user login validation"
```

### Good commit message

```text
Add user login validation
```

### Weak commit messages

```text
update
changes
final
stuff
fixed
```

A commit message should explain what changed.

---

## Open the editor for a longer commit message

```bash
git commit
```

A detailed commit can contain:

```text
Add user login validation

Validate empty email and password fields.
Display field-level error messages.
Prevent invalid form submission.
```

---

## Commit tracked file changes without a separate `git add`

```bash
git commit -am "Fix navigation spacing"
```

### Every part explained

- `-a`: automatically stage modified and deleted tracked files
- `-m`: provide a message
- `-am`: combines `-a` and `-m`

Important: untracked new files are not included.

---

## Change the most recent commit message

```bash
git commit --amend -m "Correct commit message"
```

- `--amend`: replace the latest commit with an updated commit

Use this carefully if the commit has already been pushed and shared.

---

## Add forgotten staged changes to the latest commit

```bash
git add forgotten-file.js
git commit --amend --no-edit
```

- `--no-edit`: keep the existing commit message

---

## Real-life commit example

A commit is a named checkpoint:

```text
Checkpoint 1: Create login form
Checkpoint 2: Add form validation
Checkpoint 3: Connect login API
```

Small focused commits are easier to understand and undo.

---

# 16. Understand `git push`

`git push` sends local commits to a remote repository.

## Push the current tracked branch

```bash
git push
```

This works when the upstream branch is already configured.

---

## First push of `main`

```bash
git push -u origin main
```

### Every word explained

- `push`: send commits
- `-u`: remember the upstream relationship
- `origin`: remote nickname
- `main`: branch name

---

## Push a new feature branch

```bash
git push -u origin feature/login
```

After that:

```bash
git push
```

---

## Push all tags

```bash
git push origin --tags
```

- `--tags`: push all local tags

---

## Push one tag

```bash
git push origin v1.0.0
```

---

## What `push` does not do

`git push` does not automatically stage or commit your current file changes.

This will not upload an unsaved edit:

```bash
git push
```

You must first:

```bash
git add .
git commit -m "Save the change"
git push
```

---

## Real-life example

- Editing a file: writing a page
- `git add`: selecting the page
- `git commit`: sealing the page in a named package
- `git push`: sending the package to GitHub

---

# 17. Understand `git pull`

`git pull` receives remote changes and integrates them into your current branch.

```bash
git pull
```

In its normal form, pull is approximately:

```bash
git fetch
git merge
```

## Pull from a specific remote branch

```bash
git pull origin main
```

### Every word explained

- `pull`: download and integrate changes
- `origin`: remote name
- `main`: remote branch

---

## Pull using rebase

```bash
git pull --rebase
```

- `--rebase`: replay your local commits after the downloaded remote commits

This can create a cleaner linear history, but beginners should first understand normal pulling and merging.

---

## Real-life example

Your teammate added two pages to the online book. `git pull` downloads those pages and inserts them into your local copy.

---

## Good habit before starting work

```bash
git switch main
git pull
```

Then create your feature branch.

---

# 18. Understand `git fetch`

`git fetch` downloads remote information without changing your current working branch.

```bash
git fetch
```

### Real-life example

`fetch` checks what new parcels arrived at the post office, but does not open or add them to your room.

`pull` checks the parcels and brings their contents into your current project.

---

## Fetch from `origin`

```bash
git fetch origin
```

---

## Fetch all remotes

```bash
git fetch --all
```

---

## Remove stale remote branch references

```bash
git fetch --prune
```

- `--prune`: remove local remote-tracking references for branches deleted on the remote

---

## See commits available remotely

```bash
git log HEAD..origin/main --oneline
```

### Meaning

- `HEAD`: current local commit
- `..`: commit range
- `origin/main`: remote-tracking `main`
- `--oneline`: one compact line per commit

This shows commits present in `origin/main` but not in your current local branch.

---

# 19. Branches

Branches let you work separately without immediately changing `main`.

## List local branches

```bash
git branch
```

The current branch is marked with `*`.

---

## List local and remote branches

```bash
git branch -a
```

- `-a`: all branches

---

## Create a branch

```bash
git branch feature/login
```

This creates the branch but does not switch to it.

### Naming pattern

```text
feature/login
fix/navbar-overflow
docs/git-notes
refactor/auth-service
```

The `/` is part of the name. It visually groups related branches.

---

## Create and switch in one command

```bash
git switch -c feature/login
```

### Every word explained

- `switch`: move to another branch
- `-c`: create a new branch
- `feature/login`: new branch name

Older equivalent:

```bash
git checkout -b feature/login
```

---

## Rename the current branch

```bash
git branch -m new-name
```

- `-m`: move or rename

---

## Delete a merged local branch

```bash
git branch -d feature/login
```

- `-d`: delete safely, Git warns if work is not merged

---

## Force-delete a local branch

```bash
git branch -D feature/login
```

- `-D`: force deletion

Use it only when you are certain the branch is no longer needed.

---

## Delete a remote branch

```bash
git push origin --delete feature/login
```

- `--delete`: ask the remote to delete that branch

---

## Real-life example

`main` is the official assignment.

`feature/login` is a separate photocopy where you experiment with the login page. The official assignment stays stable until the experiment is approved.

---

# 20. Switch Between Branches

## Switch to an existing branch

```bash
git switch main
```

---

## Switch back to the previous branch

```bash
git switch -
```

- `-`: previous branch

---

## Create a local branch from a remote branch

```bash
git switch --track origin/feature/login
```

- `--track`: connect the new local branch to the remote branch
- `origin/feature/login`: remote-tracking branch

A common shorter form may also work:

```bash
git switch feature/login
```

when Git can identify the matching remote branch automatically.

---

## Why switching may fail

Git may stop you if uncommitted changes would be overwritten.

Safe choices:

1. Commit the changes
2. Stash the changes
3. Discard the changes only if they are not needed

---

# 21. Merge Branches

Merge combines another branch into the branch you are currently on.

Assume `feature/login` is complete.

## Step 1: Switch to `main`

```bash
git switch main
```

## Step 2: Update `main`

```bash
git pull
```

## Step 3: Merge the feature branch

```bash
git merge feature/login
```

### Every word explained

- `merge`: combine another branch into the current branch
- `feature/login`: source branch whose changes should be included

Important: Git merges **into your current branch**.

---

## Step 4: Push updated `main`

```bash
git push
```

---

## Fast-forward merge

A fast-forward happens when `main` has not changed since the feature branch was created. Git moves the `main` pointer forward.

---

## Merge commit

When both branches have new commits, Git may create a new merge commit connecting both histories.

---

## Merge without automatic commit

```bash
git merge --no-commit feature/login
```

- `--no-commit`: perform the merge but stop before creating the merge commit

---

## Stop an unfinished merge

```bash
git merge --abort
```

- `--abort`: return to the state before the merge started

---

# 22. Merge Conflicts

A conflict happens when Git cannot safely decide which change to keep.

## Simplest real-life example

Original sentence:

```text
The button is blue.
```

Developer A changes it to:

```text
The button is red.
```

Developer B changes it to:

```text
The button is green.
```

Git cannot choose red or green automatically.

---

## Conflict markers

A conflicted file may contain:

```text
<<<<<<< HEAD
The button is red.
=======
The button is green.
>>>>>>> feature/design
```

### Meaning

- `<<<<<<< HEAD`: beginning of your current branch's version
- `=======`: separator
- `>>>>>>> feature/design`: end of the incoming branch's version

---

## Resolve a conflict

1. Open each conflicted file.
2. Decide which content to keep.
3. Remove all conflict markers.
4. Save the file.
5. Stage the resolved file.
6. Complete the merge.

Commands:

```bash
git status
git add path/to/conflicted-file
git commit
```

If the conflict happened during `git pull`, the same basic process applies.

---

## Abort a merge conflict

```bash
git merge --abort
```

---

## Abort a rebase conflict

```bash
git rebase --abort
```

---

## Continue a rebase after resolving conflicts

```bash
git add path/to/file
git rebase --continue
```

---

# 23. View Changes and History

## View unstaged changes

```bash
git diff
```

Shows changes in the working directory that are not staged.

---

## View staged changes

```bash
git diff --staged
```

- `--staged`: compare the staging area with the latest commit

Equivalent:

```bash
git diff --cached
```

---

## Compare two branches

```bash
git diff main..feature/login
```

- `..`: compare the commit ranges or endpoints

---

## View commit history

```bash
git log
```

Shows commit hash, author, date, and message.

---

## Compact history

```bash
git log --oneline
```

- `--oneline`: display each commit on one line

---

## Visual branch history

```bash
git log --oneline --graph --decorate --all
```

### Every option explained

- `--oneline`: compact commits
- `--graph`: draw branch lines using text
- `--decorate`: show branch and tag names
- `--all`: include all local references

---

## View one commit

```bash
git show abc1234
```

- `show`: display an object, usually a commit
- `abc1234`: shortened commit hash

---

## View the latest commit

```bash
git show HEAD
```

---

## See who changed each line

```bash
git blame README.md
```

Despite its name, `blame` is mainly a history-inspection command. It shows which commit last changed each line.

---

## Search commit messages

```bash
git log --grep="login"
```

- `--grep`: filter commit messages by text

---

## Search history for a changed piece of text

```bash
git log -S "validateUser"
```

- `-S`: find commits that changed the number of occurrences of the specified text

---

# 24. Undo Changes Safely

Different situations require different undo commands.

## Situation 1: Discard unstaged changes in one file

```bash
git restore README.md
```

This replaces the working copy with the latest staged or committed version.

Warning: your current unstaged changes are lost.

---

## Situation 2: Discard all unstaged tracked-file changes

```bash
git restore .
```

Warning: all unstaged edits to tracked files under the current directory are lost.

---

## Situation 3: Unstage a file but keep its edits

```bash
git restore --staged README.md
```

---

## Situation 4: Revert a pushed commit safely

```bash
git revert abc1234
```

### Meaning

`revert` creates a new commit that reverses the selected commit.

This is usually safe for shared history.

### Real-life example

Instead of tearing a page out of the public record, you add a new correction page.

---

## Situation 5: Move the latest local commit back but keep changes staged

```bash
git reset --soft HEAD~1
```

### Every part explained

- `reset`: move the current branch pointer
- `--soft`: keep changes in the staging area
- `HEAD`: current commit
- `~1`: one parent before the current commit

---

## Situation 6: Remove the latest local commit and keep changes unstaged

```bash
git reset HEAD~1
```

The default mode is normally `--mixed`.

---

## Situation 7: Remove the latest commit and its changes

```bash
git reset --hard HEAD~1
```

Warning: this can permanently discard uncommitted work.

---

## `revert` vs `reset`

| Command | Best use |
|---|---|
| `git revert` | Undo a commit in shared or pushed history |
| `git reset` | Rewrite local history before sharing |
| `git restore` | Restore working or staged file content |

---

# 25. Git Stash

Stash temporarily stores unfinished tracked changes.

## Save current unfinished work

```bash
git stash
```

Real-life example: put unfinished papers in a drawer so you can clean the desk and work on something urgent.

---

## Save with a description

```bash
git stash push -m "Incomplete login form"
```

### Every word explained

- `stash`: manage temporary saved changes
- `push`: create a new stash entry
- `-m`: attach a message
- `"Incomplete login form"`: description

---

## Include untracked files

```bash
git stash -u
```

- `-u`: include untracked files

---

## List stashes

```bash
git stash list
```

---

## Apply the newest stash and keep it in the list

```bash
git stash apply
```

---

## Apply the newest stash and remove it from the list

```bash
git stash pop
```

---

## Apply a specific stash

```bash
git stash apply stash@{1}
```

- `stash@{1}`: the second stash entry

---

## Delete a stash

```bash
git stash drop stash@{0}
```

---

## Delete all stashes

```bash
git stash clear
```

Use `clear` carefully because it removes all stash entries.

---

# 26. Delete and Rename Files

## Delete a tracked file

```bash
git rm old-file.txt
```

This deletes the file and stages the deletion.

---

## Stop tracking a file but keep it on your laptop

```bash
git rm --cached .env
```

### Meaning

- `--cached`: remove the file from Git's index, not from the working directory

Then add it to `.gitignore`.

---

## Rename or move a tracked file

```bash
git mv old-name.js new-name.js
```

### Meaning

- `mv`: move or rename
- `old-name.js`: current path
- `new-name.js`: new path

Git can also detect many renames even if you use normal operating-system commands.

---

# 27. Remote Repository Commands

## List remote names

```bash
git remote
```

---

## List remote names and URLs

```bash
git remote -v
```

---

## Add a remote

```bash
git remote add origin git@github.com:username/repository.git
```

---

## Show information about a remote

```bash
git remote show origin
```

---

## Change a remote URL

```bash
git remote set-url origin git@github.com:username/new-repository.git
```

### Every part explained

- `set-url`: replace the saved remote address
- `origin`: target remote
- final value: new URL

---

## Rename a remote

```bash
git remote rename origin upstream
```

---

## Remove a remote

```bash
git remote remove origin
```

This removes only the saved connection. It does not delete the GitHub repository.

---

## Common `origin` and `upstream` setup for a fork

```text
origin   = your fork
upstream = original repository
```

Add upstream:

```bash
git remote add upstream git@github.com:original-owner/repository.git
```

Update from it:

```bash
git fetch upstream
git switch main
git merge upstream/main
git push origin main
```

---

# 28. `.gitignore`

A `.gitignore` file tells Git which untracked files or paths it should ignore.

## Common Node.js example

```gitignore
# Dependencies
node_modules/

# Environment secrets
.env
.env.local
.env.*.local

# Build output
.next/
dist/
build/

# Test output
coverage/

# Logs
*.log
npm-debug.log*
yarn-debug.log*
pnpm-debug.log*

# Editor and operating-system files
.vscode/
.idea/
.DS_Store
```

---

## Pattern meanings

| Pattern | Meaning |
|---|---|
| `node_modules/` | Ignore that directory |
| `*.log` | Ignore every file ending in `.log` |
| `.env` | Ignore a file named `.env` |
| `temp*` | Ignore names beginning with `temp` |
| `!important.log` | Do not ignore this matching file |
| `docs/*.pdf` | Ignore PDFs directly inside `docs` |
| `**/cache/` | Ignore `cache` directories at any depth |

---

## Important limitation

`.gitignore` does not automatically stop tracking a file that was already committed.

Use:

```bash
git rm --cached .env
git commit -m "Stop tracking environment file"
git push
```

If the file contained a secret, rotate or revoke that secret. Removing the current file does not automatically remove it from old Git history.

---

# 29. Forks and Pull Requests

## Fork

A fork is your GitHub-hosted copy of someone else's repository.

Use a fork when:

- You do not have write access
- You want to contribute to an open-source project
- You want your own online copy

---

## Pull request

A pull request, or PR, asks repository maintainers to review and merge your branch.

Important: a pull request is a GitHub collaboration feature, not the same thing as `git pull`.

### Real-life example

You edited your copy of a chapter. A pull request says:

> I made these changes. Please review them and add them to the official book.

---

## Basic pull request workflow

```bash
git clone git@github.com:your-username/project.git
cd project
git switch -c fix/navbar-overflow
```

Make changes, then:

```bash
git status
git add .
git commit -m "Fix navbar overflow on mobile"
git push -u origin fix/navbar-overflow
```

Then open GitHub and create a pull request.

---

## Keep a fork updated

Add the original repository:

```bash
git remote add upstream git@github.com:original-owner/project.git
```

Fetch updates:

```bash
git fetch upstream
```

Update local `main`:

```bash
git switch main
git merge upstream/main
```

Update your fork:

```bash
git push origin main
```

---

# 30. Tags and Releases

A tag gives a permanent name to an important commit.

Real-life example: placing a label saying “Version 1.0” on a completed product.

## Create a lightweight tag

```bash
git tag v1.0.0
```

---

## Create an annotated tag

```bash
git tag -a v1.0.0 -m "First stable release"
```

### Every word explained

- `tag`: manage tags
- `-a`: create an annotated tag
- `v1.0.0`: tag name
- `-m`: tag message
- `"First stable release"`: description

Annotated tags contain extra metadata.

---

## List tags

```bash
git tag
```

---

## Show a tag

```bash
git show v1.0.0
```

---

## Push one tag

```bash
git push origin v1.0.0
```

---

## Push all tags

```bash
git push origin --tags
```

---

## Delete a local tag

```bash
git tag -d v1.0.0
```

---

## Delete a remote tag

```bash
git push origin --delete v1.0.0
```

---

# 31. Rebase in Simple Words

Rebase moves or replays commits onto a new base commit.

Suppose history looks like:

```text
A---B---C main
     \
      D---E feature
```

After rebasing `feature` onto `main`, it can look like:

```text
A---B---C main
         \
          D'---E' feature
```

The feature changes are replayed after the latest `main`.

---

## Rebase a feature branch onto `main`

```bash
git switch feature/login
git fetch origin
git rebase origin/main
```

---

## Continue after resolving a rebase conflict

```bash
git add path/to/file
git rebase --continue
```

---

## Cancel the rebase

```bash
git rebase --abort
```

---

## Important warning

Rebase rewrites commit history.

Avoid rebasing commits that other people are already using, unless your team has agreed on that workflow.

---

## Merge vs rebase

| Merge | Rebase |
|---|---|
| Preserves branch history | Creates a more linear history |
| May create a merge commit | Rewrites commit identities |
| Safer for shared branches | Useful for cleaning a private feature branch |
| Easy for beginners | Requires more care |

---

# 32. Useful Advanced Commands

## Find a command's manual

```bash
git help clone
```

Or:

```bash
git clone --help
```

---

## Show a short command summary

```bash
git clone -h
```

- `-h`: short help

---

## Create a useful history alias

```bash
git config --global alias.lg "log --oneline --graph --decorate --all"
```

Then run:

```bash
git lg
```

---

## Find the commit that introduced a bug

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
```

Git repeatedly checks commits between known good and bad points.

When finished:

```bash
git bisect reset
```

---

## Apply one commit from another branch

```bash
git cherry-pick abc1234
```

- `cherry-pick`: copy the changes from a selected commit onto the current branch

Use it carefully because it creates a new commit identity.

---

## Clean untracked files safely

Preview first:

```bash
git clean -n
```

- `-n`: dry run, show what would be deleted

Delete untracked files:

```bash
git clean -f
```

- `-f`: force

Delete untracked files and directories:

```bash
git clean -fd
```

This can permanently delete files, so always preview first.

---

## Check tracked files

```bash
git ls-files
```

---

## Check which ignore rule matches a file

```bash
git check-ignore -v .env
```

- `-v`: show the matching ignore pattern and source file

---

## Show repository root

```bash
git rev-parse --show-toplevel
```

Useful when you are unsure which repository contains the current directory.

---

# 33. Common Errors and Solutions

## Error: `fatal: not a git repository`

### Cause

You are outside a Git repository, or the repository has no `.git` directory.

### Check

```bash
pwd
ls -la
```

### Fix

Enter the correct project:

```bash
cd path/to/project
```

Or initialize it:

```bash
git init
```

---

## Error: `remote origin already exists`

### Cause

A remote named `origin` is already configured.

### Check

```bash
git remote -v
```

### Change its URL

```bash
git remote set-url origin NEW_URL
```

Or remove and add it again:

```bash
git remote remove origin
git remote add origin NEW_URL
```

---

## Error: `src refspec main does not match any`

### Common causes

- You have not created a commit
- Your branch has a different name
- The repository is empty

### Check

```bash
git status
git branch
git log --oneline
```

### Common fix

```bash
git add .
git commit -m "Initial commit"
git branch -M main
git push -u origin main
```

---

## Error: push rejected because remote contains work

Example message:

```text
rejected
fetch first
non-fast-forward
```

### Cause

The remote branch contains commits missing from your local branch.

### Fix

```bash
git pull
```

Resolve conflicts if required, then:

```bash
git push
```

In some team workflows:

```bash
git pull --rebase
git push
```

Do not solve this automatically with a force push.

---

## Error: `Permission denied (publickey)`

### Cause

GitHub cannot authenticate your SSH key.

### Check

```bash
ssh -T git@github.com
```

Also check:

```bash
ls -la ~/.ssh
ssh-add -l
```

Add the key if necessary:

```bash
ssh-add ~/.ssh/id_ed25519
```

Confirm that the matching public key is saved in your GitHub account.

---

## Error: `Author identity unknown`

### Cause

Git does not know your author name or email.

### Fix

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

## Error: `nothing to commit, working tree clean`

This is normally not an error.

It means:

- No tracked file has changed
- No staged changes are waiting
- Your latest local changes are already committed

---

## Error: `Your local changes would be overwritten`

Git is protecting your uncommitted work.

Choose one:

### Commit

```bash
git add .
git commit -m "Save current work"
```

### Stash

```bash
git stash
```

### Discard, only when not needed

```bash
git restore .
```

---

## Accidentally committed `.env`

First, stop tracking it:

```bash
git rm --cached .env
```

Add it to `.gitignore`:

```gitignore
.env
```

Commit:

```bash
git add .gitignore
git commit -m "Stop tracking environment secrets"
git push
```

Then rotate all exposed keys or passwords.

The secret may still exist in older history. For complete history removal, use an appropriate history-rewriting tool and coordinate with collaborators.

---

## Wrong branch was used

Check:

```bash
git branch
git status
```

If changes are not committed, create and switch to a new branch while keeping them:

```bash
git switch -c correct-branch
```

If commits were made on the wrong private branch, options include `cherry-pick`, branch reset, or merge. Choose carefully based on whether the commits were pushed.

---

## Large file rejected

GitHub may reject files above its normal Git size limits.

Possible actions:

- Remove generated files
- Add them to `.gitignore`
- Use Git LFS for suitable large assets
- Store releases or external assets outside normal source history

---

# 34. Commands That Need Extra Care

## Hard reset

```bash
git reset --hard
```

Can permanently discard uncommitted tracked changes.

---

## Clean

```bash
git clean -fd
```

Can permanently delete untracked files and folders.

Preview first:

```bash
git clean -n
```

---

## Force push

```bash
git push --force
```

Can overwrite remote history and remove teammates' commits.

A safer alternative is:

```bash
git push --force-with-lease
```

`--force-with-lease` refuses to overwrite the remote branch when it has unexpected updates. It is still a history-rewriting action and must be used carefully.

---

## Delete branch forcefully

```bash
git branch -D branch-name
```

Can remove unmerged local work.

---

## Remove the `.git` directory

```bash
rm -rf .git
```

This removes the repository's local Git history and configuration.

It does not delete ordinary project files, but the folder stops being a Git repository. Never run this casually.

---

# 35. Complete Practical Workflows

## Workflow A: Start a brand-new project locally

```bash
mkdir todo-app
cd todo-app
git init
touch README.md
git status
git add README.md
git commit -m "Add initial README"
git branch -M main
git remote add origin git@github.com:username/todo-app.git
git push -u origin main
```

### Story

1. Create a project folder
2. Enter it
3. Enable Git tracking
4. Create a README
5. Inspect changes
6. Select the README
7. Save the first checkpoint
8. Name the main branch
9. connect GitHub
10. Upload the commit

---

## Workflow B: Clone and update your own project

```bash
git clone git@github.com:username/todo-app.git
cd todo-app
git status
```

Edit files, then:

```bash
git add .
git commit -m "Add task deletion"
git push
```

---

## Workflow C: Start a feature safely

```bash
git switch main
git pull
git switch -c feature/dark-mode
```

Make changes:

```bash
git status
git add .
git commit -m "Add dark mode theme"
git push -u origin feature/dark-mode
```

Create a pull request on GitHub.

---

## Workflow D: Update a feature branch with the latest `main`

Merge method:

```bash
git switch main
git pull
git switch feature/dark-mode
git merge main
```

Or rebase method:

```bash
git fetch origin
git switch feature/dark-mode
git rebase origin/main
```

Use the workflow preferred by your team.

---

## Workflow E: Fix a production bug

```bash
git switch main
git pull
git switch -c fix/login-crash
```

Make and test the fix:

```bash
git add .
git commit -m "Fix crash when login response is empty"
git push -u origin fix/login-crash
```

Open a pull request.

---

## Workflow F: Save unfinished work before an urgent switch

```bash
git stash push -m "Incomplete profile form"
git switch main
git pull
git switch -c fix/urgent-navbar
```

After completing the urgent work, return:

```bash
git switch feature/profile
git stash pop
```

---

## Workflow G: Undo a bad pushed commit

Find it:

```bash
git log --oneline
```

Create a reversing commit:

```bash
git revert BAD_COMMIT_HASH
git push
```

This keeps shared history understandable.

---

## Workflow H: Collaborate on an open-source repository

1. Fork the repository on GitHub.
2. Clone your fork:

```bash
git clone git@github.com:your-username/project.git
cd project
```

3. Add the original repository:

```bash
git remote add upstream git@github.com:original-owner/project.git
```

4. Create a branch:

```bash
git switch -c docs/improve-installation
```

5. Commit and push:

```bash
git add .
git commit -m "Improve installation documentation"
git push -u origin docs/improve-installation
```

6. Create a pull request to the original repository.

---

# 36. Git Command Cheat Sheet

## Setup

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --global --list
```

## Create or download a repository

```bash
git init
git clone REPOSITORY_URL
```

## Inspect

```bash
git status
git status -s
git diff
git diff --staged
git log
git log --oneline
git log --oneline --graph --decorate --all
git show COMMIT_HASH
```

## Stage and commit

```bash
git add FILE
git add .
git add -A
git restore --staged FILE
git commit -m "Message"
git commit --amend
```

## Remote

```bash
git remote
git remote -v
git remote add origin URL
git remote set-url origin URL
git remote show origin
git remote remove origin
```

## Synchronize

```bash
git fetch
git fetch --all
git pull
git pull --rebase
git push
git push -u origin BRANCH
```

## Branches

```bash
git branch
git branch -a
git switch BRANCH
git switch -c NEW_BRANCH
git switch -
git branch -m NEW_NAME
git branch -d BRANCH
git branch -D BRANCH
git push origin --delete BRANCH
```

## Merge and rebase

```bash
git merge BRANCH
git merge --abort
git rebase BRANCH
git rebase --continue
git rebase --abort
```

## Undo

```bash
git restore FILE
git restore .
git restore --staged FILE
git revert COMMIT_HASH
git reset --soft HEAD~1
git reset HEAD~1
git reset --hard HEAD~1
```

## Stash

```bash
git stash
git stash -u
git stash list
git stash apply
git stash pop
git stash drop stash@{0}
git stash clear
```

## Files

```bash
git rm FILE
git rm --cached FILE
git mv OLD_NAME NEW_NAME
git clean -n
git clean -fd
```

## Tags

```bash
git tag
git tag v1.0.0
git tag -a v1.0.0 -m "Release message"
git push origin v1.0.0
git push origin --tags
git tag -d v1.0.0
```

## Help

```bash
git help COMMAND
git COMMAND --help
git COMMAND -h
```

---

# 37. Git Glossary

| Word | Simplest meaning |
|---|---|
| Git | Tool that tracks project versions |
| GitHub | Online service for Git repositories |
| Repository | A Git-tracked project |
| Local | On your laptop |
| Remote | On an online server |
| Working directory | Files you currently edit |
| Index | Another name for the staging area |
| Staging area | Changes selected for the next commit |
| Untracked | File Git has never recorded |
| Tracked | File Git knows about |
| Modified | Tracked file changed after the last commit |
| Staged | Change selected for the next commit |
| Commit | Saved project snapshot |
| Commit hash | Unique ID of a commit |
| Branch | Separate development line |
| `main` | Usual primary branch |
| `HEAD` | Pointer to your current checked-out commit |
| Clone | Download a full repository and history |
| Push | Upload commits |
| Pull | Download and integrate commits |
| Fetch | Download remote information only |
| Merge | Combine branch histories |
| Rebase | Replay commits on a new base |
| Conflict | Changes Git cannot combine automatically |
| Remote | Named connection to another repository |
| `origin` | Conventional name of the main remote |
| Upstream branch | Remote branch tracked by a local branch |
| Fork | Your online copy of another repository |
| Pull request | Request to review and merge changes |
| Stash | Temporary storage for unfinished changes |
| Tag | Permanent name for an important commit |
| Release | Published version based on a tag |
| Revert | New commit that reverses an old commit |
| Reset | Move a branch pointer and possibly change files |
| Restore | Restore working or staged file content |
| Fast-forward | Move a branch pointer directly forward |
| Detached HEAD | HEAD points directly to a commit, not a branch |
| `.git` | Hidden folder containing repository data |
| `.gitignore` | Rules for untracked files Git should ignore |
| `README.md` | Main project documentation file |
| Markdown | Simple text formatting language used in README files |
| SSH | Secure protocol used to authenticate and connect |
| Public key | Key safe to add to GitHub |
| Private key | Secret key that must remain on your laptop |
| URL | Address of a repository |
| CLI | Command-line interface |
| Flag or option | Extra command setting, such as `--global` |
| Argument | Value given to a command, such as a file name |
| `.` | Current directory |
| `..` | Parent directory |
| `~` | Home directory |
| `/` | Directory separator on Linux and macOS |
| `-m` | Common short option meaning message |
| `-u` in push | Set the upstream tracking branch |
| `--global` | Apply a Git setting to your user account |
| `--force` | Perform an action despite safety checks |
| `--dry-run` or `-n` | Preview without applying the action |

---

# 38. Official References

These notes are based on the official Git and GitHub documentation:

- Git reference: <https://git-scm.com/docs>
- Git everyday commands: <https://git-scm.com/docs/everyday>
- Git cheat sheet: <https://git-scm.com/cheat-sheet>
- Git clone documentation: <https://git-scm.com/docs/git-clone>
- Git pull documentation: <https://git-scm.com/docs/git-pull>
- Git push documentation: <https://git-scm.com/docs/git-push>
- Git config documentation: <https://git-scm.com/docs/git-config>
- GitHub repository quickstart: <https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories>
- GitHub SSH setup: <https://docs.github.com/en/authentication/connecting-to-github-with-ssh>
- GitHub remote repository guide: <https://docs.github.com/en/get-started/git-basics/managing-remote-repositories>
- Adding local code to GitHub: <https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github>

---

# Final Memory Trick

Remember this sequence:

```text
PULL  -> receive the newest team work
EDIT  -> change your files
STATUS -> check what changed
ADD   -> select changes
COMMIT -> save a named checkpoint
PUSH  -> upload the checkpoint
```

Command form:

```bash
git pull
# Edit files
git status
git add .
git commit -m "Explain what changed"
git push
```

The simplest way to remember Git:

```text
Working directory -> Staging area -> Local repository -> GitHub
       edit             git add       git commit       git push
```