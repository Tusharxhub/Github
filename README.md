#  Git and GitHub Notes

> A beginner-friendly, comprehensive handbook covering every Git and GitHub concept, command, workflow, and best practice — from installing Git to contributing to open-source projects.

---

## Beginner Roadmap

Before diving into commands and concepts, here is a simple overview of the journey ahead:

```text
Create GitHub Account
        ↓
Install Git
        ↓
Configure Git
        ↓
Connect Git to GitHub (HTTPS or SSH)
        ↓
Create or Clone a Repository
        ↓
Add Changes to the Staging Area
        ↓
Commit Changes Locally
        ↓
Push to GitHub
        ↓
Pull Updates from GitHub
        ↓
Branches and Pull Requests
```

By the end of this guide you will be able to:

- Track changes to any project using Git
- Publish and share code on GitHub
- Collaborate with other developers safely
- Undo mistakes without losing work
- Contribute to open-source projects
- Understand every important Git command, flag, and concept

---

## Table of Contents

- [1. What is Version Control?](#1-what-is-version-control)
- [2. What is Git?](#2-what-is-git)
- [3. What is GitHub?](#3-what-is-github)
- [4. Git Terminology](#4-git-terminology)
- [5. Create a GitHub Account](#5-create-a-github-account)
- [6. Install Git](#6-install-git)
- [7. Configure Git](#7-configure-git)
- [8. Connect Git to GitHub](#8-connect-git-to-github)
  - [HTTPS Authentication](#https-authentication)
  - [SSH Authentication](#ssh-authentication)
- [9. Create a Repository](#9-create-a-repository)
- [10. Clone a Repository](#10-clone-a-repository)
- [11. The File Lifecycle](#11-the-file-lifecycle)
- [12. Status and Diff](#12-status-and-diff)
- [13. Staging Changes](#13-staging-changes)
- [14. Committing Changes](#14-committing-changes)
- [15. Viewing Git History](#15-viewing-git-history)
- [16. Working with Remotes](#16-working-with-remotes)
- [17. Pushing Changes](#17-pushing-changes)
- [18. Pulling and Fetching](#18-pulling-and-fetching)
- [19. Branches](#19-branches)
- [20. Merging](#20-merging)
- [21. Resolving Merge Conflicts](#21-resolving-merge-conflicts)
- [22. Undoing Mistakes](#22-undoing-mistakes)
- [23. Stashing Changes](#23-stashing-changes)
- [24. Rebasing](#24-rebasing)
- [25. The .gitignore File](#25-the-gitignore-file)
- [26. Tags and Releases](#26-tags-and-releases)
- [27. Fork and Open-Source Contribution](#27-fork-and-open-source-contribution)
- [28. Pull Requests](#28-pull-requests)
- [29. Issues and Discussions](#29-issues-and-discussions)
- [30. GitHub Actions](#30-github-actions)
- [31. Removing Files from Git History](#31-removing-files-from-git-history)
- [32. GitHub CLI](#32-github-cli)
- [33. Common Git Errors and Solutions](#33-common-git-errors-and-solutions)
- [34. Practical Workflows](#34-practical-workflows)
- [35. Git Command Anatomy](#35-git-command-anatomy)
- [36. Terminal Symbols and Special Characters](#36-terminal-symbols-and-special-characters)
- [37. Best Practices](#37-best-practices)
- [38. Git Cheat Sheet](#38-git-cheat-sheet)
- [39. Interview Questions](#39-interview-questions)
- [40. Practice Exercises](#40-practice-exercises)
- [41. Contribution Guidelines](#41-contribution-guidelines)

---

## 1. What is Version Control?

Version control is a system that records changes to files over time so you can recall any specific version later. Think of it like a detailed undo history for your entire project — not just the last action, but every change ever made, who made it, when, and why.

**Real-life analogy:** Imagine writing a long essay in Google Docs. Every time you save, Google Docs quietly records the document's history, and you can go back to any earlier version at any time. Version control does exactly this for code — but with far more power, precision, and collaboration features.

Without version control, developers often:

- Overwrite each other's work accidentally
- Have no record of why a change was made
- Cannot easily revert a broken feature
- Resort to confusing copies like `project_v2_FINAL_v3.zip`

Version control solves all of these problems.

---

## 2. What is Git?

Git is a **distributed version control system** created by Linus Torvalds in 2005. It runs on your local computer and tracks changes to files in a project directory called a repository.

Key facts:

- Git works entirely offline on your laptop
- Every developer has a **full copy** of the entire project history
- Git does **not** require GitHub to work
- Git is free and open source
- Git is the most widely used version control system in the world

**Distributed version control** means that instead of one central server holding the only copy of history, every developer's computer stores a complete, independent copy. You can commit, branch, merge, and review history with no internet connection.

---

## 3. What is GitHub?

GitHub is a cloud-based platform that hosts Git repositories online. It adds a web interface and collaboration features on top of Git, including:

- Remote storage for Git repositories
- **Pull Requests** for reviewing code before merging
- **Issues** for tracking bugs, tasks, and ideas
- **Actions** for automated testing and deployment (CI/CD)
- **Forks** for contributing to other people's projects
- **Organizations** for managing teams
- **GitHub Pages** for hosting static websites

**Git and GitHub are different things.** Git is the tool that runs on your computer and tracks history. GitHub is a website where you can store and share your Git repositories. You can use Git without GitHub, and there are alternative hosting platforms such as GitLab and Bitbucket.

---

## 4. Git Terminology

This section defines every important term you will encounter.

### Repository (Repo)

A directory where Git tracks all changes. It contains your project files and a hidden `.git` folder that stores the entire history. Every project you track with Git has its own repository.

### Local Repository

A repository stored on your own computer. All commits, branches, and history live here. You can work on it completely offline.

### Remote Repository

A repository stored on a server (such as GitHub). You push changes from your local repository to the remote so others can access them and so your work is backed up.

### Working Directory (Working Tree)

The folder on your computer where your actual project files live. When you edit a file in your code editor, you are editing it in the working directory.

### Staging Area (Index)

A preparation zone between the working directory and the local repository. You explicitly add files to the staging area before committing. This lets you choose exactly which changes to include in a single commit, even if several files have changed.

### Tracked File

A file that Git is aware of because it has been added and committed at least once.

### Untracked File

A file that exists in the working directory but that Git does not yet know about. All new files start as untracked.

### Modified File

A tracked file whose content has changed since the last commit but has not yet been staged.

### Commit

A permanent snapshot of the staged changes saved into the local repository. Every commit records exactly what changed, who changed it, when, and why (via the commit message).

### Commit Hash

A unique 40-character identifier (SHA-1) automatically generated for every commit. Example: `a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2`. You can abbreviate it to the first 7 characters in most commands.

### Branch

A lightweight, movable pointer to a commit. Branches let you develop features or fix bugs in isolation without affecting the main codebase. When you make a new commit on a branch, the pointer moves forward automatically.

### Main Branch

The default primary branch of a repository, conventionally named `main` (historically named `master`).

### HEAD

A special pointer that indicates which commit you are currently viewing. In normal operation, HEAD points to the latest commit on your current branch. Moving HEAD moves what is considered "now" in the project.

### Detached HEAD

A state where HEAD points directly to a specific commit instead of to a branch. You can view history in this state, but any new commits you make will not belong to any branch and may be lost unless you create a new branch first.

### Remote

A named reference to a repository hosted on a server. The standard name for the primary remote is `origin`.

### Origin

The conventional name given to the remote repository that a local repository was cloned from. It is just a name — you can rename it or use different names for multiple remotes. It is not a reserved keyword.

### Upstream

In the context of forks: the original repository you forked from. In the context of branches: the remote branch that a local branch is configured to track (for push and pull).

### Clone

Downloading a complete copy of a remote repository — including all commits, branches, tags, and history — to your local computer.

### Fork

A copy of a repository created in your own GitHub account. Forking is a **GitHub feature**, not a Git command. You fork a repository when you want to propose changes to a project you do not have direct write access to.

### Push

Uploading local commits from your computer to a remote repository.

### Pull

Downloading new commits from a remote repository and **integrating** them into your current local branch. `git pull` is equivalent to `git fetch` followed by an integration step.

### Fetch

Downloading commits, branches, tags, and references from a remote repository into your local repository without automatically integrating them into your current branch. After fetching, you can inspect what changed before deciding how to integrate it.

### Merge

Combining the history of two branches into one. Git either moves the branch pointer forward in a straight line (fast-forward merge) or creates a new merge commit that ties two diverged histories together (three-way merge).

### Rebase

Moving or replaying commits from one branch on top of another. Rebase rewrites commit history to produce a cleaner, linear timeline.

### Conflict

A situation where two branches have made incompatible changes to the same part of the same file and Git cannot automatically decide which version to keep. Conflicts must be resolved manually.

### Checkout

An older Git command that can switch branches, restore files, or move HEAD. Modern Git separates these responsibilities into `git switch` (for changing branches) and `git restore` (for restoring files).

### Switch

The modern Git command for changing between branches (`git switch BRANCH_NAME`).

### Restore

The modern Git command for discarding changes in the working directory (`git restore FILE`) or for unstaging files (`git restore --staged FILE`).

### Reset

Moves the current branch pointer backward to an earlier commit. Can optionally also modify the staging area and working directory depending on the flag used (`--soft`, `--mixed`, or `--hard`).

### Revert

Creates a **new commit** that undoes the changes introduced by a previous commit. Safe to use on shared branches because it does not rewrite history.

### Stash

Temporarily saves uncommitted changes to a stack so you can switch to another branch without losing your work. The changes can be reapplied later.

### Tag

A permanent label attached to a specific commit, typically used to mark a release version such as `v1.0.0`.

### Release

A GitHub feature built on top of a Git tag. A release adds a title, release notes, and optional downloadable binary files.

### Pull Request (PR)

A GitHub feature that lets you propose merging changes from one branch into another. Other developers review, comment on, and approve the changes before they are merged.

### Issue

A GitHub feature for tracking bugs, feature requests, tasks, or questions related to a project.

### Contributor

Anyone who has submitted an accepted contribution to a repository.

### Maintainer

The person or team responsible for reviewing and merging contributions and managing the overall direction of a project.

### `.gitignore`

A text file in the root of a repository that tells Git which files and directories to ignore. Ignored files are not tracked, not staged, and not committed.

### `README.md`

A Markdown file in the root of a repository that describes the project. GitHub renders it automatically on the repository's main page.

---

## 5. Create a GitHub Account

1. Open [https://github.com](https://github.com) in your browser.
2. Click **Sign up**.
3. Enter your email address, choose a password, and choose a username.

**Choosing a username:** Use your real name or a professional handle. Avoid names with random numbers or characters. This username appears on every contribution you make publicly, so treat it as a professional identity.

4. Complete the verification step GitHub shows you, then click **Create account**.
5. Verify your email address by clicking the link GitHub sends you. Your account is not fully active until you do this.
6. Visit your GitHub profile and click **Edit profile** to add:
   - A clear profile photo
   - Your full name
   - A short bio describing what you work on
   - Your website or portfolio URL
   - Links to social profiles

7. **Enable Two-Factor Authentication (2FA):** Go to **Settings → Password and authentication → Two-factor authentication** and enable it. 2FA requires a second form of verification when you log in, significantly improving account security.

8. **Store your recovery codes safely:** GitHub generates backup codes during 2FA setup. Store them in a password manager or a secure offline location. Without these codes, you may permanently lose access to your account if you lose your 2FA device.

> [!TIP]
> A complete GitHub profile with a photo, bio, and pinned repositories makes a strong impression on employers and open-source maintainers.

---

## 6. Install Git

### Verify an existing installation

```bash
git --version
```

`git` calls the Git program. `--version` is a flag that tells Git to print its version number and exit. If a version number appears, Git is already installed and you can skip to the next section.

### Fedora

```bash
sudo dnf install git
```

### Ubuntu and Debian

```bash
sudo apt update
sudo apt install git
```

### Arch Linux

```bash
sudo pacman -S git
```

### macOS

Install Homebrew from [https://brew.sh](https://brew.sh) if you have not already, then run:

```bash
brew install git
```

### Windows

1. Download the installer from [https://git-scm.com/download/win](https://git-scm.com/download/win).
2. Run the installer.
3. When asked to choose a default editor, select **Visual Studio Code** if you have it installed.
4. Leave other options at their defaults unless you have a specific reason to change them.
5. After installation, open **Git Bash** and run:

```bash
git --version
```

**Git Bash** is a terminal emulator bundled with Git for Windows. It provides a Unix-like command-line environment on Windows, including commands such as `ls`, `mkdir`, `cat`, and `ssh`. You can also use Windows Terminal or PowerShell once Git is installed.

---

## 7. Configure Git

Before making your first commit, you must tell Git your name and email address. Git attaches this information to every commit you create. Commits made with incorrect information are difficult to correct retroactively.

### Required configuration

```bash
git config --global user.name "Your Name"
git config --global user.email "YOUR_EMAIL"
```

Replace `"Your Name"` with your real name and `YOUR_EMAIL` with the email address you used for your GitHub account.

### Anatomy of the configuration command

| Part            | Meaning                                                      |
| --------------- | ------------------------------------------------------------ |
| `git`           | Runs the Git program                                         |
| `config`        | Reads or changes Git configuration settings                  |
| `--global`      | Applies the setting to all repositories for the current user |
| `user.name`     | The configuration key being set                              |
| `"Your Name"`   | The value assigned to that key                               |

### Recommended additional settings

```bash
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
git config --global color.ui auto
```

| Setting                        | Effect                                                                |
| ------------------------------ | --------------------------------------------------------------------- |
| `init.defaultBranch main`      | Names the first branch `main` when you run `git init`                 |
| `core.editor "code --wait"`    | Opens VS Code to write commit messages; terminal waits until you close the file |
| `color.ui auto`                | Enables colored terminal output for easier reading                    |

### Verify your configuration

```bash
git config --list
git config --global --list
git config --get user.name
git config --get user.email
```

### Configuration levels

Git has three levels of configuration. A more specific level always takes priority over a less specific one.

| Level  | File location                               | Scope                             |
| ------ | ------------------------------------------- | --------------------------------- |
| System | `/etc/gitconfig`                            | All users on the computer         |
| Global | `~/.gitconfig` or `~/.config/git/config`    | All repositories for current user |
| Local  | `.git/config` inside the repository folder  | That specific repository only     |

Priority order:

```text
Local > Global > System
```

A local setting overrides a global setting, which overrides a system setting. Use local settings when a single project requires a different email address (for example, a work project versus a personal project).

---

## 8. Connect Git to GitHub

You need to authenticate with GitHub before you can push to or pull from private repositories. GitHub supports two methods: HTTPS and SSH.

### HTTPS Authentication

With HTTPS, remote URLs begin with `https://github.com/`.

GitHub no longer accepts account passwords for command-line Git operations. Instead it uses **Personal Access Tokens (PATs)**.

A PAT is a secret string that acts like a password specifically for Git and the GitHub API. You generate it once in GitHub settings and use it in place of a password when Git asks for credentials.

#### Generating a Personal Access Token

1. Go to **GitHub → Settings → Developer settings → Personal access tokens**.
2. Choose **Fine-grained tokens** (recommended) or **Tokens (classic)**.
3. Click **Generate new token**.
4. Give the token a descriptive name, set an expiration date, and choose the scopes (permissions) you need. For pushing and pulling code, the `repo` scope is required.
5. Click **Generate token** and copy the token immediately. GitHub will not show it again.

#### Token security

- Store your token in a password manager.
- Never commit a token to a repository.
- Set an expiration date and regenerate regularly.
- Use fine-grained tokens with the minimum necessary permissions.

#### Git Credential Manager

Git for Windows includes **Git Credential Manager (GCM)**, which opens a browser window for GitHub authentication and stores your credentials securely in the system keychain. GCM can also be installed on macOS and Linux. With GCM configured, you may not need to manually enter a token on every push — the manager handles the authentication flow automatically.

> [!NOTE]
> GitHub's authentication screens and options change over time. Always refer to the current documentation at [https://docs.github.com](https://docs.github.com) for the latest instructions.

---

### SSH Authentication

SSH lets you authenticate using a pair of cryptographic keys instead of a token. Once set up, you never need to enter a password or token again.

#### How SSH key pairs work

- **Private key** — Stays on your computer only. Never share it.
- **Public key** — Added to your GitHub account. GitHub uses it to verify your identity when you connect.

#### Step 1: Check for existing SSH keys

```bash
ls -al ~/.ssh
```

If you see files named `id_ed25519` and `id_ed25519.pub`, keys already exist. Skip to Step 3.

#### Step 2: Generate a new SSH key

```bash
ssh-keygen -t ed25519 -C "YOUR_EMAIL"
```

| Part         | Meaning                                                       |
| ------------ | ------------------------------------------------------------- |
| `ssh-keygen` | The program that generates SSH key pairs                      |
| `-t`         | Specifies the key algorithm type                              |
| `ed25519`    | A modern, fast, and secure elliptic-curve algorithm           |
| `-C`         | Adds a comment (label) to the key, usually your email address |

When prompted:

- Press **Enter** to accept the default file location (`~/.ssh/id_ed25519`).
- Enter a **passphrase**, or press Enter to skip. A passphrase adds extra security. If someone steals your private key file, they cannot use it without your passphrase.

#### Step 3: Start the SSH agent and add your key

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

The SSH agent is a background program that holds your decrypted private key in memory so you do not need to type your passphrase on every Git operation.

#### Step 4: Copy your public key

```bash
cat ~/.ssh/id_ed25519.pub
```

`cat` prints the contents of a file to the terminal. The `.pub` extension marks the public key. Copy the entire line starting with `ssh-ed25519`.

#### Step 5: Add the public key to GitHub

1. Go to **GitHub → Settings → SSH and GPG keys**.
2. Click **New SSH key**.
3. Give the key a descriptive title (for example, `Personal Laptop`).
4. Paste the public key into the Key field.
5. Click **Add SSH key**.

#### Step 6: Test the connection

```bash
ssh -T git@github.com
```

Expected response:

```text
Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
```

#### Path and symbol reference

| Symbol / Path      | Meaning                                                            |
| ------------------ | ------------------------------------------------------------------ |
| `~`                | Your home directory (`/home/you` on Linux, `/Users/you` on macOS)  |
| `.ssh`             | A hidden directory inside your home folder for SSH files           |
| `id_ed25519`       | Your **private** key — never share this file with anyone           |
| `id_ed25519.pub`   | Your **public** key — this is the file you add to GitHub           |

> [!WARNING]
> Never share `~/.ssh/id_ed25519` with anyone. Only `~/.ssh/id_ed25519.pub` is safe to add to GitHub. Sharing your private key completely compromises your security.

#### SSH troubleshooting

| Problem                         | Likely Cause                                   | Solution                                                              |
| ------------------------------- | ---------------------------------------------- | --------------------------------------------------------------------- |
| `Permission denied (publickey)` | Key not in SSH agent or not added to GitHub    | Run `ssh-add ~/.ssh/id_ed25519`; verify key in GitHub SSH settings    |
| SSH agent not running           | Agent was not started                          | Run `eval "$(ssh-agent -s)"` then `ssh-add ~/.ssh/id_ed25519`         |
| Key not added to GitHub         | Public key missing from GitHub account         | Copy output of `cat ~/.ssh/id_ed25519.pub` and add it to GitHub       |
| Wrong GitHub account            | Key linked to a different account              | Check which account owns the key in GitHub Settings → SSH keys        |
| Multiple GitHub accounts        | Using personal key for a work account          | Configure `~/.ssh/config` with separate host aliases for each account |
| Incorrect remote URL            | Remote set to HTTPS but SSH key is configured  | Run `git remote set-url origin git@github.com:USERNAME/REPOSITORY.git` |

---

## 9. Create a Repository

### Create a repository on GitHub

1. Log in to GitHub and click the **+** icon → **New repository**.
2. Enter a repository name, choose public or private.
3. Click **Create repository**. Leave it empty if you already have local commits.

### Create a local repository from scratch

```bash
mkdir my-project
cd my-project
git init
touch README.md
git status
git add README.md
git commit -m "docs: add initial README"
```

| Command                        | Meaning                                                    |
| ------------------------------ | ---------------------------------------------------------- |
| `mkdir my-project`             | Creates a new directory named `my-project`                 |
| `cd my-project`                | Moves the terminal into the `my-project` directory         |
| `git init`                     | Initializes a new Git repository in the current directory  |
| `touch README.md`              | Creates an empty file named `README.md`                    |
| `git status`                   | Shows the current state of the working directory           |
| `git add README.md`            | Stages `README.md` for the next commit                     |
| `git commit -m "..."`          | Creates a snapshot of staged changes with a message        |

#### What `git init` creates

`git init` creates a hidden `.git` directory inside your project folder. This directory contains:

- `config` — local repository settings
- `HEAD` — pointer to the current branch
- `objects/` — all commits, trees, and file content snapshots
- `refs/` — branch and tag references

> [!WARNING]
> If you delete the `.git` directory, you permanently erase the entire local Git history for that repository. Your project files remain on disk, but all commit history, branches, and tracking information are gone and cannot be recovered.

### Push a new local project to GitHub

After creating an **empty** repository on GitHub:

```bash
cd my-project
git init
git add .
git commit -m "chore: initial commit"
git branch -M main
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git push -u origin main
```

If you use HTTPS instead of SSH, replace the `git remote add` line with:

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

| Command                          | Meaning                                                            |
| -------------------------------- | ------------------------------------------------------------------ |
| `git add .`                      | Stages all files in the current directory and its subdirectories   |
| `git branch -M main`             | Renames the current branch to `main` (`-M` forces the rename)     |
| `git remote add origin URL`      | Registers a remote connection named `origin` pointing to the URL   |
| `git push -u origin main`        | Pushes commits and sets `origin/main` as the upstream branch       |

> [!NOTE]
> When you already have local commits, the GitHub repository should normally be created **empty** — without a README, `.gitignore`, or license. If GitHub creates an initial commit and your local repo also has commits, the two histories will be unrelated and Git will refuse to push by default.

---

## 10. Clone a Repository

Cloning downloads a complete copy of a repository — all commits, branches, tags, and files — to your computer.

### Clone via HTTPS

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

### Clone via SSH

```bash
git clone git@github.com:USERNAME/REPOSITORY.git
```

### Clone into a custom folder name

```bash
git clone URL custom-folder-name
```

### Clone a specific branch

```bash
git clone --branch BRANCH_NAME URL
```

### Shallow clone (download only the latest snapshot)

```bash
git clone --depth 1 URL
```

A shallow clone is faster and uses less disk space. Use it when you only need the current state of the code and do not need the full history. This is common in CI/CD pipelines.

#### What happens when you clone

- A new directory is created with the repository name (or your custom name).
- All files are downloaded into that directory.
- A `.git` directory is created containing the full history.
- A remote named `origin` is automatically configured pointing to the URL you cloned from.

### Clone vs Fork vs Download ZIP

| Method       | History included     | Linked to original  | Can push changes    | Best use case                               |
| ------------ | -------------------- | ------------------- | ------------------- | ------------------------------------------- |
| Clone        | Yes, full history    | Yes (via `origin`)  | If you have access  | Working on a project you have write access to |
| Fork         | Yes (at fork time)   | Yes (via upstream)  | Via Pull Request    | Contributing to someone else's project       |
| Download ZIP | No                   | No                  | No                  | Quickly viewing files without using Git      |

---

## 11. The File Lifecycle

Every file in a Git repository passes through a series of states.

```text
Untracked  →  Staged  →  Committed  →  Pushed
                ↑
          (modified tracked file)
```

### ASCII diagram: how files move between areas

```text
Working Directory     Staging Area      Local Repository    Remote Repository
      │                    │                   │                   │
      │   git add          │                   │                   │
      ├───────────────────►│                   │                   │
      │                    │   git commit      │                   │
      │                    ├──────────────────►│                   │
      │                    │                   │   git push        │
      │                    │                   ├──────────────────►│
      │                    │                   │                   │
      │  git restore       │                   │   git fetch       │
      │◄───────────────────┤                   │◄──────────────────┤
      │  (discard change)  │                   │                   │
      │                    │  git restore      │   git pull        │
      │◄────────────────── │ ◄──── --staged    │◄──────────────────┤
      │                    │                   │                   │
```

### State descriptions

| State     | Description                                               | Command to move forward        |
| --------- | --------------------------------------------------------- | ------------------------------ |
| Untracked | New file Git does not know about                          | `git add FILE_NAME`            |
| Modified  | Tracked file with unsaved (uncommitted) changes           | `git add FILE_NAME`            |
| Staged    | Change queued for the next commit                         | `git commit -m "message"`      |
| Committed | Snapshot saved in local history                           | `git push`                     |
| Pushed    | Commit uploaded to the remote repository                  | —                              |

---

## 12. Status and Diff

### Check the repository state

```bash
git status
git status --short
```

`git status` shows which files are untracked, modified, and staged in a detailed, human-readable format.

`git status --short` uses a compact two-column format. The **first column** represents the staging area state; the **second column** represents the working tree state.

### Status symbols

| Symbol | Meaning                                   |
| ------ | ----------------------------------------- |
| `M`    | Modified                                  |
| `A`    | Added (newly staged)                      |
| `D`    | Deleted                                   |
| `R`    | Renamed                                   |
| `??`   | Untracked (new file not yet staged)       |
| `UU`   | Unmerged (conflict exists in this file)   |

Example of `git status --short` output:

```text
M  src/index.js      ← staged modification (first column = staging area)
 M src/styles.css    ← unstaged modification (second column = working tree)
?? notes.txt         ← untracked new file
```

### View changes

```bash
git diff
git diff --staged
git diff HEAD
git diff BRANCH_ONE..BRANCH_TWO
git diff COMMIT_ONE COMMIT_TWO
```

| Command                            | Shows                                              |
| ---------------------------------- | -------------------------------------------------- |
| `git diff`                         | Changes in the working tree not yet staged         |
| `git diff --staged`                | Changes staged but not yet committed               |
| `git diff HEAD`                    | All changes since the last commit                  |
| `git diff BRANCH_ONE..BRANCH_TWO`  | Differences between two branches                  |
| `git diff COMMIT_ONE COMMIT_TWO`   | Differences between two commits                   |

> [!TIP]
> Always run `git diff --staged` before committing so you know exactly what you are about to save.

---

## 13. Staging Changes

The staging area lets you choose exactly which changes to include in a commit, even when multiple files have changed.

```bash
git add FILE_NAME
git add DIRECTORY/
git add .
git add -A
git add -u
git add -p
```

### Staging command comparison

| Command      | New files | Modified files | Deleted files | Scope                            |
| ------------ | --------- | -------------- | ------------- | -------------------------------- |
| `git add .`  | Yes       | Yes            | Yes           | Current directory and below      |
| `git add -A` | Yes       | Yes            | Yes           | Entire working tree              |
| `git add -u` | No        | Yes            | Yes           | Only already-tracked files       |

`git add -p` (patch mode) opens an interactive prompt that lets you stage individual chunks within a file. This is useful when a single file contains multiple unrelated changes that belong in separate commits.

> [!TIP]
> Run `git status` after staging to confirm the correct files are queued before committing.

---

## 14. Committing Changes

A commit is a permanent, immutable snapshot of the staged changes. Every commit records:

- The staged file changes
- A unique commit hash (SHA-1)
- The author name and email
- A timestamp
- A commit message describing the change
- A pointer to the parent commit

### Commit commands

```bash
git commit -m "feat: add authentication"
git commit
git commit -am "fix: update navbar alignment"
git commit --amend
git commit --amend --no-edit
```

| Command                          | Meaning                                                                              |
| -------------------------------- | ------------------------------------------------------------------------------------ |
| `git commit -m "..."`            | Creates a commit with an inline message                                              |
| `git commit`                     | Opens the configured editor to write a longer commit message                         |
| `git commit -am "..."`           | Stages all **modified tracked files** and commits in one step                        |
| `git commit --amend`             | Replaces the most recent commit with a new one, including any newly staged changes and a new message |
| `git commit --amend --no-edit`   | Amends the most recent commit without changing the message                           |

> [!WARNING]
> `git commit -am` does **not** stage new untracked files. You must run `git add` for those first.

> [!WARNING]
> Amending a commit that has already been pushed to a shared remote rewrites history and will cause problems for anyone else who has pulled that commit. Only amend commits that exist only on your local machine.

### Why commits should be small and focused

- Easier for reviewers to understand
- Easier to revert if something breaks
- Clearer project history
- Enables clean cherry-picking of individual changes

### Conventional Commits

Using a consistent commit message format makes history readable and enables automated tooling (changelog generators, semantic versioning bots).

| Prefix      | Use for                                              | Example                                         |
| ----------- | ---------------------------------------------------- | ----------------------------------------------- |
| `feat:`     | A new feature                                        | `feat: add user login page`                     |
| `fix:`      | A bug fix                                            | `fix: resolve null pointer exception on logout` |
| `docs:`     | Documentation-only changes                           | `docs: update SSH setup instructions`           |
| `style:`    | Formatting, whitespace, semicolons (no logic change) | `style: format code with Prettier`              |
| `refactor:` | Code change that is neither a fix nor a feature      | `refactor: extract email validation helper`     |
| `test:`     | Adding or correcting tests                           | `test: add unit tests for auth service`         |
| `chore:`    | Build process, dependency updates, config changes    | `chore: upgrade npm dependencies`               |
| `perf:`     | Performance improvements                             | `perf: lazy-load dashboard images`              |
| `build:`    | Changes to the build system or tools                 | `build: add webpack production config`          |
| `ci:`       | Changes to CI/CD configuration files                 | `ci: add caching to GitHub Actions workflow`    |
| `revert:`   | Reverts a previous commit                            | `revert: revert feat: add login page`           |

---

## 15. Viewing Git History

```bash
git log
git log --oneline
git log --oneline --graph --decorate --all
git show
git show COMMIT_HASH
git show --stat COMMIT_HASH
git blame FILE_NAME
git reflog
```

| Command                                      | Shows                                                            |
| -------------------------------------------- | ---------------------------------------------------------------- |
| `git log`                                    | Full commit history with author, date, hash, and message         |
| `git log --oneline`                          | One compact line per commit                                      |
| `git log --oneline --graph --decorate --all` | ASCII graph of all branches and their merge points               |
| `git show COMMIT_HASH`                       | The full diff introduced by a specific commit                    |
| `git show --stat COMMIT_HASH`                | A summary of files changed in a specific commit                  |
| `git blame FILE_NAME`                        | Shows which commit and author last modified each line of a file  |
| `git reflog`                                 | Records every local HEAD movement, including resets and rebases  |

> [!TIP]
> Press `q` to exit `git log` or any pager view in the terminal.

### Reading log output

```text
commit a1b2c3d (HEAD -> main, origin/main)
Author: Your Name <YOUR_EMAIL>
Date:   Fri Jun 19 10:00:00 2026 +0530

    feat: add authentication
```

| Label          | Meaning                                                   |
| -------------- | --------------------------------------------------------- |
| `HEAD -> main` | Your current branch is `main` and HEAD points to it       |
| `origin/main`  | The last known state of `main` on the remote (GitHub)     |
| Commit hash    | The unique identifier for this specific commit            |

### Recovering with reflog

`git reflog` records every position HEAD has been at locally, even after destructive resets. If you accidentally delete a commit with `git reset --hard`, you can often find and restore it:

```bash
git reflog
git reset --hard COMMIT_HASH
```

---

## 16. Working with Remotes

```bash
git remote
git remote -v
git remote add origin URL
git remote get-url origin
git remote set-url origin NEW_URL
git remote rename origin old-origin
git remote remove origin
git ls-remote origin
```

| Command                           | Meaning                                             |
| --------------------------------- | --------------------------------------------------- |
| `git remote`                      | Lists the names of all configured remotes           |
| `git remote -v`                   | Lists remotes with their full URLs                  |
| `git remote add origin URL`       | Adds a remote named `origin` pointing to the URL    |
| `git remote get-url origin`       | Prints the URL of `origin`                          |
| `git remote set-url origin URL`   | Changes the URL of an existing remote               |
| `git remote rename origin NAME`   | Renames a remote                                    |
| `git remote remove origin`        | Removes a remote configuration entirely             |
| `git ls-remote origin`            | Lists all branches and tags on the remote           |

> [!NOTE]
> `origin` is a convention, not a reserved keyword. You can name a remote anything. Teams working with multiple remotes sometimes name them `upstream`, `backup`, or `staging`.

---

## 17. Pushing Changes

```bash
git push
git push origin main
git push -u origin main
git push --all origin
git push --tags
git push origin --delete BRANCH_NAME
git push --force-with-lease
```

### Branch tracking explained

| Term                     | Meaning                                                                   |
| ------------------------ | ------------------------------------------------------------------------- |
| Local branch             | A branch that exists only on your computer                                |
| Remote branch            | A branch that exists on the remote server (GitHub)                        |
| Remote-tracking branch   | A local reference (such as `origin/main`) that mirrors the remote's state |
| Upstream tracking branch | The remote branch your local branch is configured to sync with            |

The first time you push a new branch, use `-u` to set the upstream:

```bash
git push -u origin feature/login
```

After that, `git push` and `git pull` work without typing the remote name and branch name each time.

> [!WARNING]
> `git push --force` overwrites the remote branch history without checking whether others have pushed commits since you last pulled. It can permanently destroy commits that other developers have already pulled. Never force push to a shared branch such as `main`.

> [!TIP]
> If you genuinely need to rewrite already-pushed history (for example, after an interactive rebase), prefer:
>
> ```bash
> git push --force-with-lease
> ```
>
> This checks that nobody else has pushed to the branch since you last fetched. If they have, the push is rejected, protecting their work.

---

## 18. Pulling and Fetching

```bash
git fetch
git fetch origin
git fetch --all
git fetch --prune
git pull
git pull origin main
git pull --rebase
git pull --rebase origin main
```

### Key relationship

```text
git pull = git fetch + integration (merge or rebase)
```

### Comparison

| Operation           | Downloads | Auto-integrates | Modifies working files | Safe at any time |
| ------------------- | --------- | --------------- | ---------------------- | ---------------- |
| `git fetch`         | Yes       | No              | No                     | Yes              |
| `git pull`          | Yes       | Yes (merge)     | Yes                    | Mostly           |
| `git pull --rebase` | Yes       | Yes (rebase)    | Yes                    | Mostly           |

**`git fetch`** downloads all new commits, branches, and tags from the remote without touching your working directory or current branch. Use it to inspect what changed before deciding how to integrate it.

**`git pull`** fetches and then merges the downloaded commits into your current branch. It may create a merge commit if your local branch and the remote branch have diverged.

**`git pull --rebase`** fetches and then replays your local commits on top of the remote commits instead of merging. This produces a cleaner, linear history and is often preferred in teams that value a tidy commit log.

**`git fetch --prune`** removes remote-tracking branches that no longer exist on the remote — for example, branches deleted from GitHub after merging.

---

## 19. Branches

Branches let you work on features, fixes, or experiments in isolation without affecting the main codebase.

```bash
git branch
git branch -a
git branch -r
git branch feature/login
git switch feature/login
git switch -c feature/login
git checkout feature/login
git checkout -b feature/login
git branch -m NEW_NAME
git branch -d BRANCH_NAME
git branch -D BRANCH_NAME
git push origin --delete BRANCH_NAME
```

### Branch command reference

| Command                          | Meaning                                                              |
| -------------------------------- | -------------------------------------------------------------------- |
| `git branch`                     | Lists all local branches                                             |
| `git branch -a`                  | Lists all local and remote-tracking branches                         |
| `git branch -r`                  | Lists remote-tracking branches only                                  |
| `git branch BRANCH_NAME`         | Creates a new branch without switching to it                         |
| `git switch BRANCH_NAME`         | Switches to an existing branch                                       |
| `git switch -c BRANCH_NAME`      | Creates a new branch and switches to it                              |
| `git checkout BRANCH_NAME`       | Older syntax: switches to an existing branch                         |
| `git checkout -b BRANCH_NAME`    | Older syntax: creates and switches to a new branch                   |
| `git branch -m NEW_NAME`         | Renames the current branch                                           |
| `git branch -d BRANCH_NAME`      | Safely deletes a branch (only if its commits are merged elsewhere)   |
| `git branch -D BRANCH_NAME`      | Force-deletes a branch regardless of merge status                    |
| `git push origin --delete BRANCH` | Deletes a branch on the remote                                      |

### `git switch` vs `git checkout`

`git switch` and `git restore` were introduced in Git 2.23 to replace the overloaded `git checkout` command with two focused commands.

| Task                        | Modern command              | Older equivalent             |
| --------------------------- | --------------------------- | ----------------------------- |
| Switch to a branch          | `git switch BRANCH_NAME`    | `git checkout BRANCH_NAME`    |
| Create and switch           | `git switch -c BRANCH_NAME` | `git checkout -b BRANCH_NAME` |
| Discard file changes        | `git restore FILE_NAME`     | `git checkout -- FILE_NAME`   |

> [!TIP]
> Prefer `git switch` and `git restore` in new projects. The older `git checkout` syntax still works in all Git versions, so you will encounter it frequently in older tutorials and repositories.

### Safe deletion vs forced deletion

`git branch -d` refuses to delete a branch whose commits have not been merged into another branch. This protects you from accidentally losing work.

`git branch -D` deletes the branch regardless. Use it only when you are certain the commits are no longer needed.

---

## 20. Merging

Merging combines the history of two branches.

### Basic merge workflow

```bash
git switch main
git pull origin main
git merge feature/login
git push origin main
```

### Merge strategies

**Fast-forward merge:** If the target branch has not diverged from the source branch (there are no new commits on `main` since the feature branch was created), Git simply moves the branch pointer forward. No new merge commit is created. The history is linear.

**Three-way merge:** If both branches have new commits since they diverged, Git finds their common ancestor and combines both sets of changes into a new **merge commit** that has two parent commits. The history shows where branches diverged and rejoined.

**Squash merge:** Collapses all commits from the source branch into a single set of staged changes, which you then commit manually. The feature branch's individual commits do not appear in the target branch's history.

**Rebase and merge:** Replays the feature branch's commits on top of the target branch before merging, resulting in a linear history without a merge commit.

### Merge commands

```bash
git merge feature/login
git merge --no-ff feature/login
git merge --squash feature/login
git merge --abort
```

| Command                     | Meaning                                                           |
| --------------------------- | ----------------------------------------------------------------- |
| `git merge feature/login`   | Merges the branch, using a fast-forward if possible               |
| `git merge --no-ff`         | Forces a merge commit even when a fast-forward is possible        |
| `git merge --squash`        | Stages all feature commits as one unit for a manual commit        |
| `git merge --abort`         | Cancels a merge in progress before conflicts are resolved         |

---

## 21. Resolving Merge Conflicts

A conflict occurs when Git cannot automatically merge changes because two branches modified the same lines differently.

### Conflict markers explained

When a conflict occurs, Git adds markers into the affected file:

```text
<<<<<<< HEAD
Current branch content (your version)
=======
Incoming branch content (the other branch's version)
>>>>>>> feature/login
```

| Marker                  | Meaning                                                  |
| ----------------------- | -------------------------------------------------------- |
| `<<<<<<< HEAD`          | Marks the start of your current branch's version         |
| `=======`               | Divides the two conflicting versions                     |
| `>>>>>>> feature/login` | Marks the end of the incoming branch's version           |

### Resolution workflow

```bash
git status
```

Open each conflicting file in your editor. Decide which content to keep (or write a combination of both). Remove all three conflict markers completely. The file must be clean — no marker lines — before you stage it.

```bash
git add CONFLICTED_FILE
git commit
git push
```

### Resolving conflicts in VS Code

VS Code detects conflict markers and displays buttons: **Accept Current Change**, **Accept Incoming Change**, **Accept Both Changes**, and **Compare Changes**. Click the option that produces the correct result, then save the file.

### Aborting in-progress operations

```bash
git merge --abort
git rebase --abort
```

### Continuing a rebase after resolving conflicts

After resolving each conflicted file during a rebase:

```bash
git add CONFLICTED_FILE
git rebase --continue
```

To skip the current commit entirely:

```bash
git rebase --skip
```

---

## 22. Undoing Mistakes

Choose the right command based on your situation.

### Decision table

| Situation                                         | Command                              | Risk           |
| ------------------------------------------------- | ------------------------------------ | -------------- |
| Discard unstaged changes to a file                | `git restore FILE_NAME`              | Destructive    |
| Discard all unstaged changes in the project       | `git restore .`                      | Destructive    |
| Unstage a file (keep changes in working directory) | `git restore --staged FILE_NAME`    | Safe           |
| Recover an older version of a file                | `git restore --source=HEAD~1 FILE`   | Use carefully  |
| Undo the last local commit, keep changes staged   | `git reset --soft HEAD~1`            | Use carefully  |
| Undo the last local commit, unstage changes       | `git reset --mixed HEAD~1`           | Use carefully  |
| Undo a commit already pushed to a shared branch   | `git revert COMMIT_HASH`             | Safe           |
| Preview untracked files that would be removed     | `git clean -n`                       | Safe           |
| Remove untracked files and directories            | `git clean -fd`                      | Destructive    |

### Commands

```bash
git restore FILE_NAME
git restore .
git restore --staged FILE_NAME
git restore --source=HEAD~1 FILE_NAME
git revert COMMIT_HASH
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
git clean -n
git clean -fd
```

### `git reset` mode comparison

| Flag      | Moves branch pointer | Clears staging area | Clears working directory |
| --------- | -------------------- | ------------------- | ------------------------ |
| `--soft`  | Yes                  | No                  | No                       |
| `--mixed` | Yes                  | Yes                 | No                       |
| `--hard`  | Yes                  | Yes                 | Yes                      |

> [!WARNING]
> `git reset --hard` permanently discards all uncommitted changes in both the staging area and the working directory. These changes cannot be recovered. Always run `git status` and `git diff` to verify what you are about to lose before using this command.

> [!WARNING]
> Never use `git reset` to undo commits that have already been pushed to a shared branch. Use `git revert` instead. Revert creates a new undoing commit without rewriting history, which is safe for all collaborators.

---

## 23. Stashing Changes

Stash saves uncommitted work to a temporary stack so you can switch tasks without losing your changes.

```bash
git stash
git stash push -m "unfinished login page"
git stash list
git stash show
git stash show -p
git stash apply
git stash apply stash@{0}
git stash pop
git stash drop stash@{0}
git stash clear
git stash -u
```

### Stash command reference

| Command                       | Meaning                                                             |
| ----------------------------- | ------------------------------------------------------------------- |
| `git stash`                   | Saves tracked modified files to the stash stack                     |
| `git stash push -m "..."`     | Saves with a descriptive label                                      |
| `git stash list`              | Lists all stash entries                                             |
| `git stash show`              | Shows a summary of the most recent stash                            |
| `git stash show -p`           | Shows the full diff of the most recent stash                        |
| `git stash apply`             | Reapplies the most recent stash without removing it from the stack  |
| `git stash apply stash@{0}`   | Reapplies a specific stash entry by its index                       |
| `git stash pop`               | Reapplies the most recent stash and removes it from the stack       |
| `git stash drop stash@{0}`    | Removes a specific stash entry                                      |
| `git stash clear`             | Removes all stash entries permanently                               |
| `git stash -u`                | Also stashes untracked (new) files                                  |

### Apply vs Pop

- `git stash apply` reapplies the stash but keeps the entry on the stack. Useful when you need to apply the same stash to multiple branches.
- `git stash pop` reapplies and removes the entry from the stack. Use this for a one-time reapplication.

> [!NOTE]
> By default, `git stash` only saves changes to **tracked** files. New untracked files are not included unless you use `git stash -u`.

> [!TIP]
> Stash is designed for short-term, temporary storage. For longer-lived work in progress, commit to a dedicated feature branch instead.

---

## 24. Rebasing

Rebase replays your commits on top of another branch, creating a linear history.

### Rebase a feature branch onto main

```bash
git switch feature/login
git fetch origin
git rebase origin/main
```

This replays every commit from `feature/login` on top of the latest `origin/main`, as if the feature branch started from the current tip of `main`.

### Interactive rebase

Interactive rebase lets you edit, reorder, squash, or remove commits before pushing.

```bash
git rebase -i HEAD~3
```

This opens an editor showing the last three commits:

```text
pick a1b2c3d feat: add login form
pick b4c5d6e fix: correct email validation
pick c7d8e9f docs: update comments
```

Change the word at the start of each line to apply an action:

| Action   | Meaning                                                     |
| -------- | ----------------------------------------------------------- |
| `pick`   | Keep the commit exactly as-is                               |
| `reword` | Keep the commit but change the commit message               |
| `edit`   | Pause after this commit to allow manual changes             |
| `squash` | Combine this commit into the previous one; merge messages   |
| `fixup`  | Combine this commit into the previous one; discard its message |
| `drop`   | Remove this commit entirely                                 |

### Handling conflicts during rebase

After resolving each conflicted file:

```bash
git add CONFLICTED_FILE
git rebase --continue
```

To skip the problematic commit entirely:

```bash
git rebase --skip
```

To abandon the rebase and return to the original state:

```bash
git rebase --abort
```

> [!WARNING]
> Rebase rewrites commit hashes. If you rebase commits that have already been pushed to a shared remote branch, other developers' histories will conflict with yours. Only rebase **local** commits, or personal feature branches that have not been shared with anyone else. Always coordinate with your team before rebasing shared history.

---

## 25. The `.gitignore` File

The `.gitignore` file tells Git which files and directories to leave untracked. Create it in the root of your repository.

### Example for Node.js and Next.js projects

```gitignore
# Dependencies
node_modules/

# Next.js build output
.next/

# General build outputs
dist/
build/

# Test coverage reports
coverage/

# Environment variables (may contain secrets)
.env
.env.local
.env.*.local

# Log files
*.log

# macOS system files
.DS_Store

# Editor configuration directories
.vscode/
.idea/
```

### Pattern explanations

| Pattern         | Meaning                                                    |
| --------------- | ---------------------------------------------------------- |
| `node_modules/` | Ignores the entire `node_modules` directory                |
| `.next/`        | Ignores the Next.js build output directory                 |
| `dist/`         | Ignores the general distribution build folder              |
| `.env`          | Ignores the environment variable file containing secrets   |
| `.env.*.local`  | Ignores all files matching that pattern (e.g. `.env.test.local`) |
| `*.log`         | Ignores every file ending in `.log`                        |
| `.DS_Store`     | Ignores the macOS Finder metadata file                     |

### Important rules

`.gitignore` only affects **untracked** files. If a file was already committed, adding it to `.gitignore` will not stop Git from tracking it. You must explicitly stop tracking it:

```bash
git rm --cached .env
git rm -r --cached node_modules
git commit -m "chore: stop tracking sensitive file"
```

To understand why a specific file is or is not being ignored:

```bash
git check-ignore -v FILE_NAME
```

> [!WARNING]
> Removing a secret from the **latest** commit does not remove it from Git history. Anyone with access to the repository can still retrieve it from earlier commits by checking out an old version.

> [!WARNING]
> If you accidentally commit a secret (API key, token, password, private key), revoke and replace it **immediately** — before you finish rewriting history. Treat the credential as fully compromised from the moment it was pushed.

> [!TIP]
> GitHub maintains a collection of ready-to-use `.gitignore` templates for dozens of languages and frameworks at [https://github.com/github/gitignore](https://github.com/github/gitignore).

---

## 26. Tags and Releases

Tags create a permanent, named label on a specific commit. They are most commonly used to record version releases.

```bash
git tag
git tag v1.0.0
git tag -a v1.0.0 -m "First stable release"
git show v1.0.0
git push origin v1.0.0
git push origin --tags
git tag -d v1.0.0
git push origin --delete v1.0.0
```

### Lightweight vs annotated tags

| Type        | Command                              | Stored metadata                       |
| ----------- | ------------------------------------ | ------------------------------------- |
| Lightweight | `git tag v1.0.0`                     | Only a pointer to a commit            |
| Annotated   | `git tag -a v1.0.0 -m "message"`    | Author, date, message, optional GPG signature |

Use annotated tags for official releases. Use lightweight tags for personal bookmarks.

### Semantic Versioning

```text
v MAJOR . MINOR . PATCH

v 1 . 2 . 3
  │   │   └── Patch: backward-compatible bug fix
  │   └────── Minor: backward-compatible new feature
  └────────── Major: breaking change incompatible with previous versions
```

### Git tag vs GitHub Release

A **Git tag** is a reference stored inside the `.git` directory pointing to a specific commit. A **GitHub Release** is a GitHub feature built on top of a tag. Releases add a title, formatted release notes, and optional downloadable binary files (compiled executables, archives) through the GitHub web interface.

---

## 27. Fork and Open-Source Contribution

### What is a Fork?

A fork is a copy of a repository created in your own GitHub account. It is a **GitHub feature**, not a Git command. Forking lets you propose changes to a project you do not have direct write access to.

### Complete contribution workflow

**1. Fork the repository** on GitHub by clicking the **Fork** button on the original repository page.

**2. Clone your fork to your computer:**

```bash
git clone git@github.com:YOUR_USERNAME/REPOSITORY.git
cd REPOSITORY
```

**3. Add the original repository as `upstream`:**

```bash
git remote add upstream git@github.com:ORIGINAL_OWNER/REPOSITORY.git
git remote -v
```

**4. Sync with the original before starting work:**

```bash
git fetch upstream
git switch main
git rebase upstream/main
```

**5. Create a descriptive feature branch:**

```bash
git switch -c docs/improve-readme
```

**6. Make your changes and commit:**

```bash
git add .
git commit -m "docs: improve Git explanations"
```

**7. Push the branch to your fork:**

```bash
git push -u origin docs/improve-readme
```

**8. Open a Pull Request** on GitHub from your branch to the original repository's `main` branch.

### Key terms in a fork workflow

| Term        | Meaning                                                      |
| ----------- | ------------------------------------------------------------ |
| Fork        | Your copy of the repository on GitHub                        |
| Clone       | Your local copy of the repository on your computer           |
| Origin      | Points to your fork on GitHub                                |
| Upstream    | Points to the original repository you forked from            |
| Contributor | Anyone who submits an accepted Pull Request                  |
| Maintainer  | The person or team responsible for the original repository   |

### Keeping your fork synchronized with upstream

```bash
git fetch upstream
git switch main
git rebase upstream/main
git push origin main
```

Run this regularly to minimize merge conflicts when you open a Pull Request.

---

## 28. Pull Requests

A Pull Request (PR) is a proposal to merge changes from one branch into another, with an included code review step.

### Pull Request workflow

1. Create a branch from `main`.
2. Make your changes and commit them.
3. Review your own changes with `git diff` and `git status`.
4. Push the branch to GitHub.
5. On GitHub, click **Compare & pull request**.
6. Write a clear, descriptive title and body.
7. Link the related issue (`Closes #42`).
8. Request specific reviewers.
9. Address reviewer feedback by pushing additional commits to the same branch.
10. Once approved, the maintainer merges the PR.
11. Delete the branch after it is merged.

### Professional Pull Request template

Create `.github/PULL_REQUEST_TEMPLATE.md` in your repository:

```markdown
## Description

Describe what was changed and why.

## Type of Change

- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Refactoring
- [ ] Breaking change

## Testing

Explain how the changes were tested.

## Checklist

- [ ] I reviewed my own changes before submitting
- [ ] Tests pass locally
- [ ] Documentation is updated
- [ ] No secrets or credentials are included

## Related Issue

Closes #ISSUE_NUMBER
```

---

## 29. Issues and Discussions

### Issues

GitHub Issues track bugs, feature requests, tasks, and questions related to a repository.

**Creating an issue:**

1. Go to the repository on GitHub.
2. Click **Issues → New issue**.
3. Write a clear title and detailed description.
4. Add a label, assignee, and milestone if available.
5. Click **Submit new issue**.

**Common issue types:**

| Type             | Purpose                                 |
| ---------------- | --------------------------------------- |
| Bug report       | Reporting something that is not working |
| Feature request  | Suggesting a new capability             |
| Task             | Tracking a unit of planned work         |
| Documentation    | Requesting or improving docs            |

### Linking Pull Requests to issues

Including these keywords in a PR description or commit message automatically closes the linked issue when the PR is merged into the default branch:

```text
Closes #42
Fixes #42
Resolves #42
```

### Labels, Milestones, and Assignees

- **Labels** categorize and filter issues (examples: `bug`, `enhancement`, `good first issue`, `help wanted`).
- **Milestones** group related issues into a target version or date (example: `v2.0.0`).
- **Assignees** identify who is responsible for resolving an issue.

### Discussions

GitHub Discussions is a forum for open-ended conversations that do not fit as bug reports or feature requests — questions, announcements, ideas, polls, or general community conversation.

---

## 30. GitHub Actions

GitHub Actions automates workflows triggered by repository events such as pushes, pull requests, and scheduled times.

### Complete Node.js CI workflow

Create `.github/workflows/ci.yml`:

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 22
          cache: npm

      - name: Install dependencies
        run: npm ci

      - name: Run tests
        run: npm test
```

### Workflow file explanation

| Property                    | Meaning                                                               |
| --------------------------- | --------------------------------------------------------------------- |
| `name: CI`                  | The workflow name displayed on the Actions tab in GitHub              |
| `on: push`                  | Triggers the workflow when commits are pushed                         |
| `branches: [main]`          | Restricts the trigger to pushes targeting `main`                      |
| `on: pull_request`          | Also triggers when a Pull Request targets `main`                      |
| `jobs:`                     | Defines the independent jobs in this workflow                         |
| `test:`                     | The job's identifier name                                             |
| `runs-on: ubuntu-latest`    | The type of virtual machine to run the job on                         |
| `steps:`                    | The ordered list of tasks within the job                              |
| `uses: actions/checkout@v4` | Runs a prebuilt action that checks out the repository code            |
| `uses: actions/setup-node@v4` | Runs a prebuilt action that installs Node.js                        |
| `node-version: 22`          | Specifies which Node.js version to install                            |
| `cache: npm`                | Caches `node_modules` to speed up future workflow runs                |
| `run: npm ci`               | Installs exact dependency versions from `package-lock.json`           |
| `run: npm test`             | Runs the project's test suite                                         |

---

## 31. Removing Files from Git History

### Remove a file from the repository entirely

```bash
git rm FILE_NAME
git commit -m "chore: remove FILE_NAME"
git push
```

### Stop tracking a file but keep it locally

```bash
git rm --cached FILE_NAME
git commit -m "chore: stop tracking FILE_NAME"
git push
```

This removes the file from future commits but leaves your local copy intact. Use this after adding a file to `.gitignore` that was accidentally committed.

### Why deleting a file does not remove it from history

When you delete a file and commit, Git records a deletion event. The file still exists in every **earlier** commit. Anyone who checks out an older commit or clones the repository can still access the deleted file by browsing the history. This is why accidentally committed secrets must be revoked immediately, not just deleted.

### Removing a secret from the entire Git history

> [!WARNING]
> Before rewriting history, **revoke and replace the exposed secret immediately**. Do not wait until after the cleanup. The secret is already compromised the moment it was pushed.

The recommended tool for rewriting history is `git filter-repo`:

```bash
pip install git-filter-repo
git filter-repo --path SECRET_FILE --invert-paths
```

After rewriting history, every commit hash changes. This affects everyone who has a copy of the repository:

- All collaborators must delete their local clones and re-clone.
- All open Pull Requests will reference commits that no longer exist.
- GitHub may require a force push to update the remote.

> [!WARNING]
> Coordinate history rewriting with your entire team. Ask all collaborators to re-clone after the rewrite is complete. Avoid rewriting shared history unless it is genuinely necessary.

---

## 32. GitHub CLI

The GitHub CLI (`gh`) lets you interact with GitHub directly from the terminal, without opening a browser.

### Installation

Download from [https://cli.github.com](https://cli.github.com) and follow the installation instructions for your operating system.

### Authentication

```bash
gh auth login
gh auth status
```

`gh auth login` opens an interactive flow to authenticate with your GitHub account. `gh auth status` shows which account is currently authenticated.

### Repository commands

```bash
gh repo create
gh repo clone OWNER/REPOSITORY
gh repo view --web
```

| Command                     | Meaning                                                   |
| --------------------------- | --------------------------------------------------------- |
| `gh repo create`            | Creates a new GitHub repository interactively             |
| `gh repo clone OWNER/REPO`  | Clones a GitHub repository                                |
| `gh repo view --web`        | Opens the current repository's GitHub page in the browser |

### Issue commands

```bash
gh issue list
gh issue create
```

### Pull Request commands

```bash
gh pr create
gh pr list
gh pr checkout PR_NUMBER
gh pr view
gh pr merge
```

| Command                    | Meaning                                                  |
| -------------------------- | -------------------------------------------------------- |
| `gh pr create`             | Creates a new Pull Request interactively                 |
| `gh pr list`               | Lists all open Pull Requests                             |
| `gh pr checkout PR_NUMBER` | Checks out the branch associated with a specific PR      |
| `gh pr view`               | Shows the PR for the current branch                      |
| `gh pr merge`              | Merges the current branch's Pull Request                 |

---

## 33. Common Git Errors and Solutions

### `fatal: not a git repository`

**Meaning:** You ran a Git command in a directory that has no `.git` folder.

**Solution:** Navigate to the correct project directory with `cd`, or initialize a new repository with `git init`.

---

### `remote origin already exists`

**Meaning:** You ran `git remote add origin URL` but a remote named `origin` is already configured.

**Solution:**

```bash
git remote set-url origin NEW_URL
```

---

### `repository not found`

**Meaning:** The URL does not point to a repository that exists and is accessible to you.

**Why it happens:** A typo in the URL, a private repository you are not authorized for, or you are authenticated as the wrong GitHub account.

**Solution:** Verify the URL with `git remote -v`. Check that you are authenticated with the correct account.

---

### `Permission denied (publickey)`

**Meaning:** SSH authentication failed.

**Solution:**

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
ssh -T git@github.com
```

Ensure the public key (`~/.ssh/id_ed25519.pub`) is added to your GitHub account in **Settings → SSH and GPG keys**.

---

### `Authentication failed`

**Meaning:** HTTPS authentication failed.

**Why it happens:** Your Personal Access Token is incorrect, expired, or does not have the required permissions.

**Solution:** Generate a new PAT in **GitHub → Settings → Developer settings → Personal access tokens** and update your credentials in Git Credential Manager.

---

### `src refspec main does not match any`

**Meaning:** You tried to push `main` but there are no commits on that branch yet.

**Solution:** Make at least one commit before pushing.

```bash
git add .
git commit -m "chore: initial commit"
git push -u origin main
```

---

### `failed to push some refs`

**Meaning:** Your local branch is behind the remote. The remote has commits your local copy does not have.

**Solution:**

```bash
git pull --rebase origin main
git push
```

---

### `refusing to merge unrelated histories`

**Meaning:** Git refuses to merge two branches that share no common ancestor.

**Why it happens:** You created commits locally and also created separate commits on GitHub (for example, by initializing the remote with a README while your local repo also had an initial commit).

**Solution:**

```bash
git pull origin main --allow-unrelated-histories
```

Resolve any conflicts that arise, then push.

---

### Local changes would be overwritten by pull

**Meaning:** Git refuses to pull because the operation would overwrite uncommitted local changes.

**Solution:** Stash or commit your local changes first.

```bash
git stash
git pull
git stash pop
```

---

### Detached HEAD state

**Meaning:** HEAD points directly to a commit instead of to a branch.

**Why it happens:** You ran `git checkout COMMIT_HASH`.

**Solution:** Create a branch to preserve any new commits, or switch back to an existing branch.

```bash
git switch -c new-branch-name
```

---

### Branch has no upstream branch

**Meaning:** Your local branch is not linked to any remote-tracking branch.

**Solution:**

```bash
git push -u origin BRANCH_NAME
```

---

### Accidentally committed `.env`

**Solution:**

```bash
git rm --cached .env
echo ".env" >> .gitignore
git add .gitignore
git commit -m "chore: stop tracking .env and add to gitignore"
git push
```

Revoke any secrets that were in the file and replace them.

---

### Accidentally pushed an API key

1. Immediately revoke the API key in the service that issued it.
2. Generate a replacement key.
3. Remove the key from your codebase.
4. If the repository is public, use `git filter-repo` to remove the key from history.
5. Notify your team.

---

### Accidentally committed a large file

If not yet pushed:

```bash
git reset --soft HEAD~1
git rm --cached LARGE_FILE
echo "LARGE_FILE" >> .gitignore
git add .
git commit -m "chore: remove large file and add to gitignore"
```

If already pushed, use `git filter-repo` to remove the file from all historical commits.

---

### Wrong Git email on a commit

Fix the email on the most recent local commit (only if not yet pushed):

```bash
git config --global user.email "CORRECT_EMAIL"
git commit --amend --reset-author --no-edit
```

---

### Repeated username and password prompts

Configure Git Credential Manager for secure credential storage, or switch to SSH authentication to eliminate password prompts entirely.

---

## 34. Practical Workflows

### Workflow A: Create a new project and push to GitHub

**Starting situation:** You have a new project folder and an empty repository on GitHub.

```bash
cd my-project
git init
git add .
git commit -m "chore: initial commit"
git branch -M main
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git push -u origin main
```

**Expected result:** Your local project history is now on GitHub.

**Common mistake:** Initializing the GitHub repository with a README when your local repo already has commits. This creates two unrelated histories that conflict.

---

### Workflow B: Clone an existing repository

**Starting situation:** You want to work on a project hosted on GitHub.

```bash
git clone git@github.com:USERNAME/REPOSITORY.git
cd REPOSITORY
```

**Expected result:** All files and history are on your computer and `origin` points to GitHub automatically.

---

### Workflow C: Make changes and push them

**Starting situation:** You are inside a cloned repository and want to add new work.

```bash
git switch main
git pull origin main
git status
git diff
git add .
git diff --staged
git commit -m "feat: add contact form"
git push origin main
```

**Common mistake:** Skipping `git pull` before pushing, which causes a rejection because the remote has newer commits.

---

### Workflow D: Create and merge a feature branch

**Starting situation:** You want to add a feature without touching `main` directly.

```bash
git switch main
git pull origin main
git switch -c feature/search-bar
git add .
git commit -m "feat: add search bar component"
git push -u origin feature/search-bar
```

Open a Pull Request on GitHub. After approval and merge:

```bash
git switch main
git pull origin main
git branch -d feature/search-bar
git push origin --delete feature/search-bar
```

---

### Workflow E: Resolve a merge conflict

**Starting situation:** A merge or pull resulted in conflicts.

```bash
git status
```

Open each conflicting file, review the conflict markers, decide what the final content should be, and remove all markers.

```bash
git add CONFLICTED_FILE
git commit
git push
```

---

### Workflow F: Undo the last local commit but keep changes

**Starting situation:** You committed too early and want to revise the changes before recommitting.

```bash
git reset --soft HEAD~1
```

Your changes are now back in the staging area, ready to be modified and recommitted.

---

### Workflow G: Undo an already-pushed commit safely

**Starting situation:** You pushed a commit that introduced a problem and need to undo it on a shared branch.

```bash
git revert COMMIT_HASH
git push
```

This creates a new commit that undoes the previous one. History is preserved. All collaborators can pull normally.

---

### Workflow H: Update a fork from the original repository

**Starting situation:** The original repository has new commits since you forked it.

```bash
git fetch upstream
git switch main
git rebase upstream/main
git push origin main
```

---

### Workflow I: Remove an accidentally committed `.env` file

**Starting situation:** You committed and pushed a `.env` file containing credentials.

```bash
git rm --cached .env
echo ".env" >> .gitignore
git add .gitignore
git commit -m "chore: stop tracking .env, add to gitignore"
git push
```

Revoke all credentials that were in the file and generate new ones immediately.

---

### Workflow J: Change a remote URL from HTTPS to SSH

**Starting situation:** You set up a remote with HTTPS and want to switch to SSH authentication.

```bash
git remote -v
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
git remote -v
```

---

### Workflow K: Recover a lost commit using reflog

**Starting situation:** You ran `git reset --hard` and lost commits you need to recover.

```bash
git reflog
```

Find the commit hash of the lost commit in the reflog output, then:

```bash
git reset --hard COMMIT_HASH
```

---

## 35. Git Command Anatomy

Every Git command follows this pattern:

```text
git <command> [options] [arguments]
```

### `git push -u origin main`

| Part      | Meaning                                              |
| --------- | ---------------------------------------------------- |
| `git`     | Runs the Git program                                 |
| `push`    | Uploads local commits to the remote repository       |
| `-u`      | Sets the upstream tracking relationship              |
| `origin`  | The name of the remote to push to                    |
| `main`    | The name of the local branch being pushed            |

### `git clone URL`

| Part    | Meaning                                                    |
| ------- | ---------------------------------------------------------- |
| `git`   | Runs the Git program                                       |
| `clone` | Downloads a complete repository copy to the local computer |
| `URL`   | The address of the repository (HTTPS or SSH)               |

### `git add .`

| Part  | Meaning                                                |
| ----- | ------------------------------------------------------ |
| `git` | Runs the Git program                                   |
| `add` | Stages changes for the next commit                     |
| `.`   | The current directory and all subdirectories within it |

### `git commit -m "message"`

| Part        | Meaning                                          |
| ----------- | ------------------------------------------------ |
| `git`       | Runs the Git program                             |
| `commit`    | Saves staged changes as a permanent snapshot     |
| `-m`        | Accepts the commit message as an inline argument |
| `"message"` | The commit message describing the change         |

### `git pull --rebase origin main`

| Part        | Meaning                                                            |
| ----------- | ------------------------------------------------------------------ |
| `git`       | Runs the Git program                                               |
| `pull`      | Downloads remote changes and integrates them                       |
| `--rebase`  | Integrates by replaying local commits on top of remote commits     |
| `origin`    | The remote to pull from                                            |
| `main`      | The branch on the remote to pull from                              |

### `git switch -c feature/login`

| Part            | Meaning                                                   |
| --------------- | --------------------------------------------------------- |
| `git`           | Runs the Git program                                      |
| `switch`        | Manages branch switching                                  |
| `-c`            | Creates the branch if it does not exist, then switches    |
| `feature/login` | The name of the new branch                                |

### `git remote add origin URL`

| Part     | Meaning                                            |
| -------- | -------------------------------------------------- |
| `git`    | Runs the Git program                               |
| `remote` | Manages remote repository connections              |
| `add`    | Adds a new remote connection                       |
| `origin` | The name given to the new remote                   |
| `URL`    | The URL of the remote repository                   |

### `git restore --staged FILE_NAME`

| Part         | Meaning                                           |
| ------------ | ------------------------------------------------- |
| `git`        | Runs the Git program                              |
| `restore`    | Restores a file to a previous state               |
| `--staged`   | Targets the staged version (removes it from staging, keeps working-directory changes) |
| `FILE_NAME`  | The specific file to unstage                      |

### `git reset --soft HEAD~1`

| Part      | Meaning                                             |
| --------- | --------------------------------------------------- |
| `git`     | Runs the Git program                                |
| `reset`   | Moves the current branch pointer to a different commit |
| `--soft`  | Keeps staged changes and working directory intact   |
| `HEAD~1`  | The commit one step before the current HEAD         |

### `git push --force-with-lease`

| Part                  | Meaning                                                              |
| --------------------- | -------------------------------------------------------------------- |
| `git`                 | Runs the Git program                                                 |
| `push`                | Uploads local commits to the remote                                  |
| `--force-with-lease`  | Forces the push only if no new commits exist on the remote branch since your last fetch |

---

## 36. Terminal Symbols and Special Characters

| Symbol        | Meaning                                                      | Example                                      |
| ------------- | ------------------------------------------------------------ | -------------------------------------------- |
| `.`           | The current directory                                        | `git add .` stages everything in current dir |
| `..`          | The parent directory                                         | `cd ..` moves up one level                   |
| `~`           | Your home directory                                          | `cd ~` goes to `/home/username`              |
| `/`           | Directory separator; also the root directory on Unix         | `/etc/gitconfig`                             |
| `-`           | Short flag (single character)                                | `git commit -m "msg"`                        |
| `--`          | Long flag (full word)                                        | `git commit --amend`                         |
| `>`           | Redirect output to a file (overwrites existing content)      | `echo "text" > file.txt`                     |
| `>>`          | Append output to a file (does not overwrite)                 | `echo ".env" >> .gitignore`                  |
| `&&`          | Runs the next command only if the previous one succeeded     | `git add . && git commit -m "msg"`           |
| `*`           | Wildcard that matches any string                             | `*.log` matches all `.log` files             |
| `" "`         | Quotes group characters into a single argument               | `git commit -m "My commit message"`          |
| `HEAD`        | Pointer to the current commit                                | `git diff HEAD`                              |
| `HEAD~1`      | One commit before HEAD (the parent commit)                   | `git reset --soft HEAD~1`                    |
| `HEAD^`       | Equivalent to `HEAD~1`                                       | `git diff HEAD^`                             |
| `stash@{0}`   | The most recent stash entry (index 0)                        | `git stash apply stash@{0}`                  |
| `branch@{upstream}` | The upstream tracking branch for a given branch        | `git diff branch@{upstream}`                 |

### Relative vs absolute paths

- **Relative path:** Relative to the current directory. Example: `src/index.js` refers to the file `index.js` inside the `src` folder within the current directory.
- **Absolute path:** The full path from the root of the file system. Example: `/home/you/projects/my-app/src/index.js`.

### Environment variables

Environment variables store configuration values in the shell session. They are accessed with a `$` prefix. For example, `$HOME` contains your home directory path, `$PATH` lists directories to search for programs. Git uses variables like `GIT_EDITOR` to configure its behavior.

---

## 37. Best Practices

- **Check `git status` frequently.** Understand the state of your repository before every significant operation.
- **Review `git diff` before staging.** Verify the exact changes before adding them to the staging area.
- **Review `git diff --staged` before committing.** Confirm exactly what will be saved in the commit.
- **Pull or fetch before starting new work.** Avoid working on an outdated codebase that diverges from teammates' changes.
- **Use feature branches.** Work on every new feature or bug fix in its own branch. Keep `main` stable and deployable.
- **Keep commits small and focused.** Each commit should represent one logical change. This makes reviews, reverts, and understanding history much easier.
- **Write clear, descriptive commit messages.** Future collaborators — and your future self — depend on these messages to understand the project.
- **Never commit secrets.** No API keys, tokens, passwords, or private keys should ever appear in any committed file.
- **Use Pull Requests.** Even for solo projects, a PR creates a review opportunity and a record of intent.
- **Protect the default branch.** In team projects, use GitHub branch protection rules to require reviews before merging.
- **Avoid direct pushes to `main`** in shared repositories.
- **Prefer `--force-with-lease`** over `--force` if force pushing is unavoidable.
- **Run tests and linters before pushing.** Do not push code that breaks the build or fails tests.
- **Keep documentation updated** alongside code changes.
- **Delete merged branches** to keep the branch list clean.
- **Add a `LICENSE` file** so others know how they may use your code.
- **Add a `CONTRIBUTING.md`** to explain how to contribute to the project.
- **Add a code of conduct** for community-facing projects.
- **Keep your fork synchronized** with upstream regularly to reduce merge conflicts.
- **Use `.gitignore` from the very start** of every project.

---

## 38. Git Cheat Sheet

### Setup

| Task                | Command                  | Risk |
| ------------------- | ------------------------ | ---- |
| Check Git version   | `git --version`          | Safe |
| Install on Ubuntu   | `sudo apt install git`   | Safe |
| Install on Fedora   | `sudo dnf install git`   | Safe |

### Configuration

| Task                         | Command                                           | Risk |
| ---------------------------- | ------------------------------------------------- | ---- |
| Set name                     | `git config --global user.name "Your Name"`       | Safe |
| Set email                    | `git config --global user.email "YOUR_EMAIL"`     | Safe |
| Set default branch name      | `git config --global init.defaultBranch main`     | Safe |
| Set editor to VS Code        | `git config --global core.editor "code --wait"`   | Safe |
| List all config settings     | `git config --list`                               | Safe |
| Get a specific setting       | `git config --get user.name`                      | Safe |

### Create Repository

| Task                      | Command                                | Risk |
| ------------------------- | -------------------------------------- | ---- |
| Initialize a repository   | `git init`                             | Safe |
| Add a remote              | `git remote add origin URL`            | Safe |

### Clone

| Task                     | Command                                        | Risk |
| ------------------------ | ---------------------------------------------- | ---- |
| Clone via SSH            | `git clone git@github.com:USERNAME/REPO.git`   | Safe |
| Clone via HTTPS          | `git clone https://github.com/USERNAME/REPO.git` | Safe |
| Clone to custom folder   | `git clone URL folder-name`                    | Safe |
| Shallow clone            | `git clone --depth 1 URL`                      | Safe |

### Status

| Task          | Command              | Risk |
| ------------- | -------------------- | ---- |
| Full status   | `git status`         | Safe |
| Short status  | `git status --short` | Safe |

### Diff

| Task                       | Command               | Risk |
| -------------------------- | --------------------- | ---- |
| Unstaged changes           | `git diff`            | Safe |
| Staged changes             | `git diff --staged`   | Safe |
| All changes since HEAD     | `git diff HEAD`       | Safe |
| Between two branches       | `git diff B1..B2`     | Safe |

### Stage

| Task                     | Command            | Risk |
| ------------------------ | ------------------ | ---- |
| Stage a specific file    | `git add FILE`     | Safe |
| Stage everything         | `git add .`        | Safe |
| Stage tracked files only | `git add -u`       | Safe |
| Interactive staging      | `git add -p`       | Safe |

### Commit

| Task                        | Command                       | Risk           |
| --------------------------- | ----------------------------- | -------------- |
| Commit with inline message  | `git commit -m "message"`     | Safe           |
| Stage tracked + commit      | `git commit -am "message"`    | Safe           |
| Amend last commit           | `git commit --amend`          | Use carefully  |

### History

| Task                        | Command                                        | Risk |
| --------------------------- | ---------------------------------------------- | ---- |
| Full log                    | `git log`                                      | Safe |
| Compact one-line log        | `git log --oneline`                            | Safe |
| Graph of all branches       | `git log --oneline --graph --decorate --all`   | Safe |
| Show a specific commit      | `git show COMMIT_HASH`                         | Safe |
| Line-by-line attribution    | `git blame FILE`                               | Safe |
| Local HEAD history          | `git reflog`                                   | Safe |

### Remote

| Task                   | Command                              | Risk           |
| ---------------------- | ------------------------------------ | -------------- |
| List remotes           | `git remote -v`                      | Safe           |
| Change remote URL      | `git remote set-url origin URL`      | Use carefully  |
| Remove a remote        | `git remote remove origin`           | Use carefully  |

### Push

| Task                       | Command                              | Risk           |
| -------------------------- | ------------------------------------ | -------------- |
| Push with upstream setup   | `git push -u origin main`            | Safe           |
| Push current branch        | `git push`                           | Safe           |
| Delete a remote branch     | `git push origin --delete BRANCH`    | Use carefully  |
| Safe force push            | `git push --force-with-lease`        | Use carefully  |
| Force push (dangerous)     | `git push --force`                   | Destructive    |

### Pull / Fetch

| Task                   | Command                          | Risk |
| ---------------------- | -------------------------------- | ---- |
| Fetch all remotes      | `git fetch --all --prune`        | Safe |
| Pull with merge        | `git pull`                       | Safe |
| Pull with rebase       | `git pull --rebase`              | Safe |

### Branch

| Task                    | Command                          | Risk           |
| ----------------------- | -------------------------------- | -------------- |
| List all branches       | `git branch -a`                  | Safe           |
| Create and switch       | `git switch -c BRANCH`           | Safe           |
| Switch to branch        | `git switch BRANCH`              | Safe           |
| Rename current branch   | `git branch -m NEW_NAME`         | Use carefully  |
| Delete merged branch    | `git branch -d BRANCH`           | Safe           |
| Force delete branch     | `git branch -D BRANCH`           | Destructive    |

### Merge

| Task                      | Command                      | Risk |
| ------------------------- | ---------------------------- | ---- |
| Merge a branch            | `git merge BRANCH`           | Safe |
| Merge with commit always  | `git merge --no-ff BRANCH`   | Safe |
| Abort merge in progress   | `git merge --abort`          | Safe |

### Conflict

| Task                      | Command                | Risk |
| ------------------------- | ---------------------- | ---- |
| Check conflict status     | `git status`           | Safe |
| Stage resolved file       | `git add FILE`         | Safe |

### Rebase

| Task                        | Command                       | Risk           |
| --------------------------- | ----------------------------- | -------------- |
| Rebase onto origin/main     | `git rebase origin/main`      | Use carefully  |
| Interactive rebase          | `git rebase -i HEAD~3`        | Use carefully  |
| Continue after conflict     | `git rebase --continue`       | Safe           |
| Abort rebase                | `git rebase --abort`          | Safe           |

### Stash

| Task                    | Command                          | Risk           |
| ----------------------- | -------------------------------- | -------------- |
| Stash changes           | `git stash`                      | Safe           |
| Stash with label        | `git stash push -m "label"`      | Safe           |
| List stashes            | `git stash list`                 | Safe           |
| Apply and keep stash    | `git stash apply`                | Safe           |
| Apply and remove stash  | `git stash pop`                  | Safe           |
| Drop a stash entry      | `git stash drop stash@{0}`       | Use carefully  |

### Restore

| Task                           | Command                              | Risk           |
| ------------------------------ | ------------------------------------ | -------------- |
| Discard working directory changes | `git restore FILE`                | Destructive    |
| Unstage a file                 | `git restore --staged FILE`          | Safe           |
| Restore from a specific commit | `git restore --source=HEAD~1 FILE`   | Use carefully  |

### Reset

| Task                               | Command                       | Risk           |
| ---------------------------------- | ----------------------------- | -------------- |
| Undo commit, keep staged changes   | `git reset --soft HEAD~1`     | Use carefully  |
| Undo commit, unstage changes       | `git reset --mixed HEAD~1`    | Use carefully  |
| Undo commit and discard all changes | `git reset --hard HEAD~1`    | Destructive    |

### Revert

| Task                    | Command                          | Risk |
| ----------------------- | -------------------------------- | ---- |
| Safely undo a commit    | `git revert COMMIT_HASH`         | Safe |

### Tags

| Task                     | Command                                | Risk           |
| ------------------------ | -------------------------------------- | -------------- |
| List all tags            | `git tag`                              | Safe           |
| Create annotated tag     | `git tag -a v1.0.0 -m "message"`      | Safe           |
| Push a tag               | `git push origin v1.0.0`              | Safe           |
| Delete a local tag       | `git tag -d v1.0.0`                   | Use carefully  |
| Delete a remote tag      | `git push origin --delete v1.0.0`     | Use carefully  |

### Cleanup

| Task                              | Command           | Risk        |
| --------------------------------- | ----------------- | ----------- |
| Preview untracked files to remove | `git clean -n`    | Safe        |
| Remove untracked files            | `git clean -fd`   | Destructive |

### GitHub CLI

| Task                  | Command                         | Risk |
| --------------------- | ------------------------------- | ---- |
| Authenticate          | `gh auth login`                 | Safe |
| Create repository     | `gh repo create`                | Safe |
| Create Pull Request   | `gh pr create`                  | Safe |
| List Pull Requests    | `gh pr list`                    | Safe |
| Create issue          | `gh issue create`               | Safe |

---

## 39. Interview Questions

**1. What is the difference between Git and GitHub?**
Git is a local version control system that runs on your computer and tracks file history. GitHub is a cloud platform that hosts Git repositories and adds collaboration features such as Pull Requests, Issues, and Actions.

**2. What is the difference between `git clone` and forking?**
Cloning downloads a repository to your local computer. Forking creates a copy of a repository in your own GitHub account. Forking is a GitHub feature, not a Git command.

**3. What is the difference between `git push` and `git pull`?**
Push uploads your local commits to a remote repository. Pull downloads new commits from the remote and integrates them into your current branch.

**4. What is the difference between `git pull` and `git fetch`?**
Fetch downloads remote changes into your local repository without integrating them into any branch. Pull fetches and then automatically integrates the changes into your current branch.

**5. What is the difference between `git merge` and `git rebase`?**
Merge combines two branches and may create a merge commit, preserving the full history of both branches. Rebase replays commits from one branch on top of another, rewriting history to produce a linear timeline.

**6. What is the difference between `git reset` and `git revert`?**
Reset moves the branch pointer backward, which rewrites history. Revert creates a new commit that undoes a previous commit without rewriting history. Use `git revert` on shared branches; use `git reset` only for local changes.

**7. What is the working tree?**
The directory on your computer where your actual project files live. Edits you make in your code editor happen in the working tree.

**8. What is the staging area?**
A preparation zone between the working tree and the local repository. You explicitly add changes to the staging area with `git add` before committing. Also called the index.

**9. What is HEAD?**
HEAD is a pointer indicating which commit you are currently viewing. In normal use, it points to the latest commit on your current branch.

**10. What is a detached HEAD state?**
HEAD points directly to a specific commit instead of to a branch name. New commits made in this state do not belong to any branch and may be lost unless you create a new branch first.

**11. What is a commit hash?**
A unique 40-character SHA-1 identifier automatically generated for every commit. It is derived from the commit's content and metadata. It is often abbreviated to 7 characters in commands and output.

**12. What is a remote in Git?**
A named reference to a repository hosted on a server. The primary remote is conventionally named `origin`.

**13. What is `origin`?**
The conventional name given to the remote repository that a local repository was cloned from. It is a name, not a special keyword, and can be renamed.

**14. What is upstream in the context of a fork?**
The original repository that you forked from. It is added as a remote so you can pull in the latest changes from the project maintainer.

**15. What is a tracking branch?**
A local branch configured to follow a specific remote branch. This lets `git push` and `git pull` know which remote branch to sync with without requiring the full remote and branch name each time.

**16. What is a fast-forward merge?**
When one branch has not diverged from another, Git simply moves the branch pointer forward to the latest commit without creating a merge commit. The history remains linear.

**17. What causes a merge conflict?**
A conflict occurs when two branches have made different changes to the same lines of the same file and Git cannot automatically determine which version to keep.

**18. What does `.gitignore` do?**
It tells Git which files and directories to exclude from tracking. Ignored files are never staged, committed, or pushed. It only affects files that are not already tracked.

**19. What is a stash?**
A temporary storage area for uncommitted changes. You stash changes to clean the working directory, do other work, and reapply the stash later.

**20. What is the difference between a lightweight tag and an annotated tag?**
A lightweight tag is simply a pointer to a commit with no extra metadata. An annotated tag stores the tagger's name, email, date, and a message. Use annotated tags for official releases.

**21. What is a Pull Request?**
A Pull Request is a GitHub feature that proposes merging changes from one branch into another. It provides a code review step before the merge happens.

**22. What is GitHub Actions?**
A CI/CD platform integrated into GitHub that runs automated workflows (tests, builds, deployments) triggered by repository events like pushes and pull requests.

**23. What is the reflog?**
A local log recording every position HEAD has occupied. It can be used to recover commits that were lost after a destructive reset.

**24. Why is `git push --force` dangerous?**
It overwrites the remote branch history without checking whether anyone has pushed new commits since you last pulled. It can permanently delete collaborators' commits.

**25. What is a squash merge?**
Squashing collapses all commits from a feature branch into a single staged change, which is then committed as one new commit. The individual feature branch commits do not appear in the target branch history.

**26. What does `git diff --staged` show?**
Changes that have been added to the staging area but not yet committed. These are the changes that will be included in the next `git commit`.

**27. How do you undo the last local commit without losing the changes?**
`git reset --soft HEAD~1` moves the branch pointer back one commit and keeps all changes in the staging area.

**28. How do you safely undo a commit that was already pushed to a shared branch?**
`git revert COMMIT_HASH` creates a new commit that undoes the specified commit without rewriting history. All collaborators can pull this change normally.

**29. How do you stop tracking a file that was already committed?**
Run `git rm --cached FILE_NAME` to remove it from tracking, add it to `.gitignore`, then commit the change. The file remains on your local disk.

**30. What is semantic versioning?**
A versioning convention in the format `MAJOR.MINOR.PATCH`. The MAJOR number increments on breaking changes, MINOR on new backward-compatible features, and PATCH on backward-compatible bug fixes.

**31. What is the difference between `git switch` and `git checkout`?**
Both can switch branches. `git switch` was introduced in Git 2.23 as a dedicated, clearer command for branch switching, separating it from the file-restoring behavior that `git checkout` also provided.

**32. How do you delete a branch on the remote?**
`git push origin --delete BRANCH_NAME`

---

## 40. Practice Exercises

### Exercise 1 — Install and configure Git

Install Git on your operating system and configure your name, email address, and default branch name. Verify all three settings.

<details>
<summary>Show hint</summary>

```bash
git config --global user.name "Your Name"
git config --global user.email "YOUR_EMAIL"
git config --global init.defaultBranch main
git config --list
```

</details>

---

### Exercise 2 — Create a local repository

Create a new directory, initialize a Git repository inside it, and verify that the hidden `.git` folder was created.

<details>
<summary>Show hint</summary>

```bash
mkdir practice-repo
cd practice-repo
git init
ls -la
```

</details>

---

### Exercise 3 — Add and commit a file

Create a `README.md` file, add it to the staging area, and make your first commit with a Conventional Commit message.

<details>
<summary>Show hint</summary>

```bash
touch README.md
git add README.md
git status
git commit -m "docs: add initial README"
```

</details>

---

### Exercise 4 — Create three separate commits

Create three different files (`file1.txt`, `file2.txt`, `file3.txt`) and commit each one individually with a meaningful message. Then view the history.

<details>
<summary>Show hint</summary>

Repeat for each file:

```bash
touch file1.txt
git add file1.txt
git commit -m "chore: add file1"
```

Then check history with `git log --oneline`.

</details>

---

### Exercise 5 — Add a remote

Create an empty repository on GitHub (no README, no `.gitignore`). Connect your local repository to it.

<details>
<summary>Show hint</summary>

```bash
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git remote -v
```

</details>

---

### Exercise 6 — Push to GitHub

Push your local commits to the remote repository on GitHub and verify they appear there.

<details>
<summary>Show hint</summary>

```bash
git push -u origin main
```

</details>

---

### Exercise 7 — Clone a repository

Clone any public GitHub repository using SSH to a new directory on your computer. Inspect the `.git` folder and the `origin` remote.

<details>
<summary>Show hint</summary>

```bash
git clone git@github.com:USERNAME/REPOSITORY.git
cd REPOSITORY
git remote -v
ls -la
```

</details>

---

### Exercise 8 — Create a branch

Create a new branch named `feature/about-page` and switch to it. Verify that you are on the new branch.

<details>
<summary>Show hint</summary>

```bash
git switch -c feature/about-page
git branch
```

</details>

---

### Exercise 9 — Make changes on a branch

On your `feature/about-page` branch, create a new file, commit it, and push the branch to GitHub.

<details>
<summary>Show hint</summary>

```bash
touch about.html
git add about.html
git commit -m "feat: add about page"
git push -u origin feature/about-page
```

</details>

---

### Exercise 10 — Merge a branch

Switch back to `main`, pull the latest changes, and merge your `feature/about-page` branch. Push the result.

<details>
<summary>Show hint</summary>

```bash
git switch main
git pull origin main
git merge feature/about-page
git push origin main
```

</details>

---

### Exercise 11 — Create a merge conflict

On `main`, edit the first line of `README.md` and commit. Create a new branch, edit the same line differently, and commit. Then try to merge the new branch into `main` and observe the conflict.

<details>
<summary>Show hint</summary>

```bash
git switch main
# Edit line 1 of README.md, then:
git add README.md
git commit -m "docs: update README title on main"

git switch -c conflict-branch
# Edit line 1 of README.md differently, then:
git add README.md
git commit -m "docs: update README title on branch"

git switch main
git merge conflict-branch
```

Git will report a conflict.

</details>

---

### Exercise 12 — Resolve a merge conflict

Open the conflicting file, review the markers, decide which version to keep (or combine both), remove all three marker lines, stage the file, and commit.

<details>
<summary>Show hint</summary>

```bash
git status
# Open README.md, edit out the conflict markers, save the file
git add README.md
git commit -m "fix: resolve README merge conflict"
```

</details>

---

### Exercise 13 — Stash and restore changes

Make changes to a file without staging them. Stash the changes. Switch to `main`. Switch back to your branch. Restore your stash.

<details>
<summary>Show hint</summary>

```bash
git stash push -m "work in progress"
git switch main
git switch feature/about-page
git stash pop
```

</details>

---

### Exercise 14 — Discard a file's changes

Edit a file, then decide you do not want those changes. Discard them using `git restore`.

<details>
<summary>Show hint</summary>

```bash
git restore FILE_NAME
git status
```

</details>

---

### Exercise 15 — Create an annotated tag

After merging a feature, create an annotated tag for version `v1.0.0` and push it to GitHub.

<details>
<summary>Show hint</summary>

```bash
git tag -a v1.0.0 -m "First stable release"
git push origin v1.0.0
```

</details>

---

### Exercise 16 — Open a Pull Request

Push a feature branch to GitHub and open a Pull Request. Write a description that includes `Closes #1` to link it to an issue. Request a reviewer.

<details>
<summary>Show hint</summary>

Push the branch, then navigate to the repository on GitHub. Click **Compare & pull request**, fill in the title and description including `Closes #1`, and click **Create pull request**.

</details>

---

## 41. Contribution Guidelines

This repository is open to contributions from everyone. Whether you are fixing a typo, improving an explanation, or adding an entirely new section — your help is welcomed and appreciated.

### How to report an issue

If you find an error, an outdated command, or something confusing:

1. Search the existing issues to check if it has already been reported.
2. Open a new issue with a clear, specific title.
3. In the body, include the section heading, describe what is incorrect or missing, and suggest an improvement if you have one.

### How to suggest an improvement

1. Open a new issue with the `enhancement` label.
2. Describe the improvement clearly and explain why it helps beginners.

### How to contribute content

1. Fork the repository on GitHub.
2. Clone your fork locally.
3. Create a branch using one of these naming patterns:

```text
docs/improve-installation
fix/incorrect-command
feat/add-git-lfs-section
chore/update-links
```

4. Make your changes.
5. Write commit messages following Conventional Commits:

```text
docs: improve SSH setup instructions
fix: correct fetch explanation
feat: add Git LFS section
chore: update broken links
```

6. Push your branch and open a Pull Request targeting `main`.
7. In the PR description, explain what you changed and why.

### Commit message rules

- Use the Conventional Commits format: `type: description`.
- Begin with a lowercase prefix: `feat:`, `fix:`, `docs:`, `chore:`, etc.
- Keep the subject line under 72 characters.
- Use the commit body for additional context when the subject line is not enough.

### Pull Request expectations

- Target the `main` branch.
- Describe what changed and why.
- Reference any related issue with `Closes #NUMBER`.
- Keep changes focused — one topic per PR.
- Do not include generated files, build outputs, or editor configuration.

### Documentation standards

- Write for complete beginners. Avoid assuming prior knowledge.
- Define technical terms the first time they appear.
- Use short paragraphs.
- Prefer tables and code blocks over long prose when describing commands.
- Test every command before including it.

### What not to include

- Generated files (no `node_modules/`, build outputs, or log files).
- Secrets, tokens, API keys, or passwords in any file.
- Tools or workflows not relevant to the core Git and GitHub experience.

### Code of conduct

Be respectful, patient, and constructive in all interactions. Everyone was a beginner at some point. Contributions of all sizes are welcome.

---

*Thank you for reading this guide. If it helped you, consider starring the repository and sharing it with others who are learning Git and GitHub.*