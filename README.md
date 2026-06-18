# Complete Git and GitHub Notes: From Beginner to Advanced

> A comprehensive, beginner-friendly guide to mastering Git and GitHub. Written for developers using **Fedora Linux**, **VS Code**, **GitHub**, and **Bash** — with notes for Windows and macOS included.

---

## Table of Contents

- [1. Introduction to Version Control](#1-introduction-to-version-control)
- [2. Git vs GitHub](#2-git-vs-github)
- [3. Important Git Terminology](#3-important-git-terminology)
- [4. Creating a GitHub Account](#4-creating-a-github-account)
- [5. Installing Git](#5-installing-git)
- [6. Configuring Git on a Laptop](#6-configuring-git-on-a-laptop)
- [7. Connecting GitHub with a Laptop](#7-connecting-github-with-a-laptop)
- [8. Creating a New Local Git Repository](#8-creating-a-new-local-git-repository)
- [9. Creating a GitHub Repository and Pushing a Local Project](#9-creating-a-github-repository-and-pushing-a-local-project)
- [10. Cloning an Existing Repository](#10-cloning-an-existing-repository)
- [11. Daily Git Workflow](#11-daily-git-workflow)
- [12. Understanding the Git File Lifecycle](#12-understanding-the-git-file-lifecycle)
- [13. Checking Repository Status and Differences](#13-checking-repository-status-and-differences)
- [14. Adding Files to the Staging Area](#14-adding-files-to-the-staging-area)
- [15. Creating Commits](#15-creating-commits)
- [16. Viewing Commit History](#16-viewing-commit-history)
- [17. Working with Remote Repositories](#17-working-with-remote-repositories)
- [18. Push Commands](#18-push-commands)
- [19. Pull and Fetch Commands](#19-pull-and-fetch-commands)
- [20. Branching](#20-branching)
- [21. Merging Branches](#21-merging-branches)
- [22. Merge Conflicts](#22-merge-conflicts)
- [23. Undoing Changes Safely](#23-undoing-changes-safely)
- [24. Stashing Changes](#24-stashing-changes)
- [25. Rebasing](#25-rebasing)
- [26. .gitignore](#26-gitignore)
- [27. Git Tags and GitHub Releases](#27-git-tags-and-github-releases)
- [28. Forking and Open-Source Contribution](#28-forking-and-open-source-contribution)
- [29. Pull Requests](#29-pull-requests)
- [30. GitHub Issues and Discussions](#30-github-issues-and-discussions)
- [31. GitHub Actions](#31-github-actions)
- [32. Removing Files from Git History](#32-removing-files-from-git-history)
- [33. GitHub CLI](#33-github-cli)
- [34. Useful Inspection Commands](#34-useful-inspection-commands)
- [35. Common Errors and Solutions](#35-common-errors-and-solutions)
- [36. Complete Practical Workflows](#36-complete-practical-workflows)
- [37. Git Command Anatomy](#37-git-command-anatomy)
- [38. Symbols and Terminal Syntax](#38-symbols-and-terminal-syntax)
- [39. Git Best Practices](#39-git-best-practices)
- [40. Final Cheat Sheet](#40-final-cheat-sheet)
- [41. Practice Exercises](#41-practice-exercises)
- [42. Quick Interview Questions](#42-quick-interview-questions)

---

## 1. Introduction to Version Control

### What Is Version Control?

**Version control** is a system that records changes to files over time so that you can recall specific versions later. Think of it as a detailed save-game system for your code. Every time you save a meaningful change, the version control system remembers exactly what changed, when it changed, and who changed it.

### Why Developers Use Version Control

- **Track every change**: You can see the complete history of your project — every addition, deletion, and modification.
- **Undo mistakes safely**: If something breaks, you can go back to a previous working version.
- **Collaborate without chaos**: Multiple people can work on the same project simultaneously without overwriting each other's work.
- **Branching and experimentation**: You can create separate lines of development to try new features without affecting the stable version.
- **Accountability**: Every change is attributed to a specific person with a timestamp.
- **Backup**: Your code history is stored safely and can be recovered.

### Problems Git Solves

Without Git, developers often face:

- Naming files like `project_v1.zip`, `project_v2_final.zip`, `project_v2_final_REALLY_FINAL.zip`
- Emailing code back and forth between team members
- Accidentally overwriting a colleague's work
- Losing code because of a hard drive failure
- Not knowing who made a specific change or why
- Being unable to undo a change made weeks ago

### Local Version Control vs Remote Collaboration

- **Local version control**: All history is stored only on your own computer. If your hard drive fails, everything is lost.
- **Remote collaboration**: Your history is also stored on a remote server (like GitHub). Multiple people can access, contribute, and back up the project.

Git supports both. You work locally (fast, offline-capable) and synchronize with a remote server when ready.

### A Real-Life Analogy for Git

Imagine writing a book using Google Docs:

- You can see the full edit history (version control)
- You can revert to any previous version (undo)
- Multiple authors can write different chapters simultaneously (branching)
- You merge all chapters into one final book (merging)
- If two authors edit the same paragraph differently, you need to decide which version to keep (conflict resolution)

Git does exactly this — but for code, and with much more power and precision.

---

## 2. Git vs GitHub

Git and GitHub are **not the same thing**. This is one of the most common misconceptions for beginners.

- **Git** is a **tool** (software) that you install on your computer to track changes in your code.
- **GitHub** is a **website** (service) that hosts Git repositories online and adds collaboration features.

You can use Git without GitHub. You cannot use GitHub without Git (behind the scenes).

### Comparison Table

| Feature | Git | GitHub |
|---|---|---|
| **What is it?** | A version control tool (software) | A cloud platform (website/service) |
| **Installed on** | Your local computer | Runs on GitHub's servers (accessed via browser) |
| **Internet required?** | No — works entirely offline | Yes — it is a web service |
| **Where are repositories?** | On your local machine | On GitHub's servers (remote) |
| **Collaboration** | Does not provide collaboration tools by itself | Provides pull requests, issues, code review, etc. |
| **Who owns it?** | Open-source, maintained by the community | Owned by Microsoft |
| **Main purpose** | Track file changes locally | Host repositories, collaborate, share code |
| **Alternatives** | None for Git itself (it is the standard) | GitLab, Bitbucket, Codeberg, Gitea |

### Key Takeaway

> Git is the **engine**. GitHub is the **garage where you park and share your car**.

---

## 3. Important Git Terminology

Before learning commands, you need to understand the vocabulary. Every term below will appear repeatedly throughout this guide.

| Term | Simple Explanation |
|---|---|
| **Git** | A free, open-source version control system that tracks changes in files on your local computer. |
| **GitHub** | A website that hosts Git repositories online and provides collaboration tools like pull requests and issues. |
| **Repository (repo)** | A project folder that Git is tracking. It contains your files and the complete history of changes. |
| **Local repository** | A repository stored on your own computer. You work here directly. |
| **Remote repository** | A repository stored on a server like GitHub. Used for backup and collaboration. |
| **Working directory** | The folder on your computer where your project files live. This is where you edit files. Also called the **working tree**. |
| **Working tree** | Another name for the working directory — the actual files you can see and edit. |
| **Staging area** | A preparation zone where you place files before committing them. Think of it as a "ready to save" list. Also called the **index**. |
| **Index** | Another name for the staging area. It is the list of changes that will be included in the next commit. |
| **Commit** | A saved snapshot of the staged changes. Each commit has a unique ID, a message, an author, and a timestamp. |
| **Commit hash** | A unique 40-character identifier (like `a1b2c3d4e5...`) generated for every commit. Used to reference specific commits. |
| **Branch** | An independent line of development. Think of it as a parallel copy of your project where you can make changes without affecting the main version. |
| **Main branch** | The primary branch of a repository. By convention, it is named `main` (older repos may use `master`). |
| **HEAD** | A pointer that tells Git which branch and commit you are currently on. It usually points to the latest commit of your current branch. |
| **Remote** | A reference to a repository hosted on another server (e.g., on GitHub). |
| **Origin** | The default name given to the remote repository when you clone a project or add a remote for the first time. It is just a conventional name — you can rename it. |
| **Upstream** | Typically refers to the original repository that a fork was created from. In tracking context, it refers to the remote branch your local branch is linked to. |
| **Clone** | Creating a full copy of a remote repository on your local machine, including all files, branches, and history. |
| **Fork** | Creating your own copy of someone else's repository on GitHub (server-side copy), so you can modify it independently. |
| **Push** | Uploading your local commits to a remote repository (e.g., from your laptop to GitHub). |
| **Pull** | Downloading changes from a remote repository and integrating them into your local branch. Essentially `fetch` + `merge`. |
| **Fetch** | Downloading changes from a remote repository **without** integrating them. You can inspect the changes before merging. |
| **Merge** | Combining changes from one branch into another. For example, merging a feature branch into the main branch. |
| **Rebase** | Moving or replaying your commits on top of another branch's latest commit. This rewrites commit history to create a linear timeline. |
| **Conflict** | Occurs when two branches have changed the same part of the same file differently. Git cannot decide which version to keep, so you must resolve it manually. |
| **Checkout** | An older Git command used to switch branches or restore files. Modern replacements are `git switch` (for branches) and `git restore` (for files). |
| **Switch** | A modern Git command specifically for changing branches. Clearer and safer than `checkout` for this purpose. |
| **Restore** | A modern Git command specifically for restoring file contents. Replaces the file-restoring use of `checkout`. |
| **Reset** | A command that moves the current branch pointer backward, potentially removing commits from history. Can affect the staging area and working directory depending on the mode used. |
| **Revert** | A command that creates a **new** commit that undoes the changes of a previous commit. Unlike reset, it does not remove history — it adds to it. |
| **Stash** | A command that temporarily saves uncommitted changes so you can work on something else, then come back later. Like a clipboard for code changes. |
| **Tag** | A label attached to a specific commit, usually used to mark release versions (e.g., `v1.0.0`). Tags do not move like branches. |
| **Release** | A GitHub feature that packages a tagged version of your code with release notes, changelogs, and downloadable assets. |
| **Pull request (PR)** | A GitHub feature where you propose changes from one branch to another. Team members can review, discuss, and approve the changes before merging. |
| **Issue** | A GitHub feature for tracking bugs, feature requests, tasks, or questions related to a project. |
| **Contributor** | A person who contributes code or other changes to a project they do not own. |
| **Maintainer** | A person who owns or manages a project and has permission to merge pull requests and manage the repository. |
| **`.gitignore`** | A special file that tells Git which files and folders to ignore (not track). Used to exclude things like `node_modules/`, `.env`, and build outputs. |
| **`README.md`** | A Markdown file placed at the root of a repository that describes the project — its purpose, how to install it, how to use it, etc. GitHub displays it automatically on the repository page. |



---

## 4. Creating a GitHub Account

GitHub is the platform where you will host your remote repositories, collaborate with others, and showcase your work.

### Step-by-Step Guide

1. **Open GitHub**: Go to [https://github.com](https://github.com) in your web browser.

2. **Click "Sign up"**: You will see a sign-up button on the top-right corner of the page.

3. **Enter your email address**: Use a personal email you check regularly. This email will be used for notifications and account recovery.

4. **Create a password**: Use a strong, unique password. Consider using a password manager.

5. **Choose a username**: This will be your public identity on GitHub (e.g., `tushardevx01`). Choose carefully — it appears in all your repository URLs (`github.com/USERNAME/REPO`). Tips:
   - Keep it professional
   - Make it easy to remember
   - Avoid special characters
   - It can be changed later, but old links will break

6. **Solve the verification puzzle**: GitHub will ask you to complete a CAPTCHA to prove you are human.

7. **Verify your email**: GitHub will send a verification code to your email. Enter the code to confirm your account.

8. **Skip or complete the onboarding survey**: GitHub may ask about your experience level and intended use. You can skip this.

### Setting Up Your Profile

Once your account is created:

1. **Click your profile icon** (top-right corner) → **Settings**

2. **Add a profile photo**: A real photo or professional avatar helps others recognize you.

3. **Add a bio**: Write a short description of yourself. Example: *"Full-stack developer | Open-source contributor | Building cool things with code"*

4. **Add your portfolio link**: If you have a personal website or portfolio, add the URL in the "Website" field.

5. **Add social links**: GitHub allows you to add links to platforms like Twitter/X, LinkedIn, etc.

6. **Make your profile public**: Go to **Settings → Profile** and ensure your profile visibility is set to public if you want others to find you.

### Enabling Two-Factor Authentication (2FA)

Two-factor authentication adds an extra layer of security. Even if someone steals your password, they cannot access your account without the second factor.

1. Go to **Settings → Password and authentication**
2. Click **Enable two-factor authentication**
3. Choose your method:
   - **Authenticator app** (recommended): Use apps like Google Authenticator, Authy, or Microsoft Authenticator
   - **SMS**: Less secure but works as a backup
4. Scan the QR code with your authenticator app
5. Enter the verification code to confirm

### Recovery Codes

> ⚠️ **WARNING**: When you enable 2FA, GitHub gives you **recovery codes**. These are your only way back into your account if you lose access to your authenticator app. **Save them in a safe place** — a password manager, encrypted file, or printed copy stored securely. Do NOT store them in a public repository.

---

## 5. Installing Git

Git must be installed on your computer before you can use it. The installation process differs by operating system.

### Fedora Linux

Fedora uses `dnf` as its package manager:

```bash
sudo dnf install git
```

- `sudo` — Runs the command with administrator (root) privileges. Required because installing software affects the entire system.
- `dnf` — Fedora's package manager. It downloads and installs software from Fedora's repositories.
- `install` — Tells `dnf` to install a package.
- `git` — The name of the package to install.

### Ubuntu or Debian

```bash
sudo apt update
sudo apt install git
```

- `apt update` — Refreshes the list of available packages and their versions.
- `apt install git` — Installs Git.

### Arch Linux

```bash
sudo pacman -S git
```

- `pacman` — Arch Linux's package manager.
- `-S` — Synchronize (install) a package.

### macOS

If you have Homebrew installed:

```bash
brew install git
```

- `brew` — The Homebrew package manager for macOS.

Alternatively, running `git --version` on macOS for the first time will prompt you to install Apple's Command Line Tools, which includes Git.

### Windows

1. Go to [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Download the installer
3. Run the installer — the defaults are fine for most users
4. During installation, select **"Git Bash"** as the terminal emulator (it provides a Unix-like terminal on Windows)
5. Select **"Use Visual Studio Code as Git's default editor"** if you use VS Code
6. Complete the installation

After installation, open **Git Bash** (Windows) or your terminal (Linux/macOS).

### Verifying the Installation

```bash
git --version
```

- `git` — Calls the Git program.
- `--version` — A flag (option) that tells Git to print its version number instead of running a normal command.

Expected output (version may differ):

```text
git version 2.47.1
```

If you see a version number, Git is installed correctly. If you see `command not found`, Git is not installed or not in your system's PATH.

---

## 6. Configuring Git on a Laptop

After installing Git, you need to configure it with your identity. Git attaches your name and email to every commit you make, so collaborators know who made each change.

### Setting Your Name

```bash
git config --global user.name "Tushar Kanti Dey"
```

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `config` | Tells Git you want to read or write configuration settings |
| `--global` | Applies this setting to **all** Git repositories on your computer for your user account |
| `user.name` | The configuration key — identifies which setting you are changing (your name) |
| `"Tushar Kanti Dey"` | The value to set — your full name, in quotes because it contains a space |

### Setting Your Email

```bash
git config --global user.email "your-email@example.com"
```

Use the same email address you used for your GitHub account. This links your local commits to your GitHub profile.

### Setting the Default Branch Name

```bash
git config --global init.defaultBranch main
```

When you create a new repository with `git init`, Git creates an initial branch. This command sets that default branch name to `main`.

> **Note**: Older versions of Git defaulted to `master`. The industry standard has shifted to `main`.

### Setting VS Code as the Default Editor

```bash
git config --global core.editor "code --wait"
```

- `core.editor` — The setting that controls which text editor Git opens when it needs you to write a message (e.g., for commits, merges, or rebases).
- `"code --wait"` — Opens VS Code. The `--wait` flag tells Git to wait until you close the VS Code tab before continuing.

### Enabling Colored Output

```bash
git config --global color.ui auto
```

This makes Git output more readable by using colors — green for additions, red for deletions, etc.

### Viewing Your Configuration

```bash
# View ALL configuration (system + global + local)
git config --list

# View only GLOBAL configuration
git config --global --list

# View a specific setting
git config --get user.name
git config --get user.email
```

### Configuration Levels

Git has three levels of configuration. Each level overrides the one above it:

| Level | Flag | Applies To | Config File Location |
|---|---|---|---|
| **System** | `--system` | All users on the computer | `/etc/gitconfig` |
| **Global** | `--global` | All repositories for your user account | `~/.gitconfig` or `~/.config/git/config` |
| **Local** | `--local` | Only the current repository | `.git/config` inside the repo |

**Priority order**: Local > Global > System

If you set `user.name` globally but set a different `user.name` locally in one repository, the local value is used for that repository.

```bash
# System-wide config (rarely used, needs sudo)
git config --system setting.key value

# Global config (most common for personal settings)
git config --global setting.key value

# Local config (per-repository overrides)
git config --local setting.key value
```

---

## 7. Connecting GitHub with a Laptop

To push code to GitHub or pull code from private repositories, your computer needs to prove its identity to GitHub. This is called **authentication**.

There are two main methods: **HTTPS** and **SSH**.

### HTTPS Authentication

#### Why Passwords Don't Work Directly

GitHub removed support for password-based authentication for Git operations in August 2021. You can still log into the GitHub website with your password, but you **cannot** use that same password to push or pull code from the command line.

#### What Is a Personal Access Token (PAT)?

A Personal Access Token is a long, randomly generated string that acts as a password substitute for Git operations over HTTPS.

**How to create one:**

1. Go to GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)** or **Fine-grained tokens**
2. Click **"Generate new token"**
3. Give it a descriptive name (e.g., "Fedora laptop")
4. Set an expiration date (90 days is common for security)
5. Select scopes/permissions:
   - `repo` — Full control of private repositories (most common)
   - `workflow` — If you use GitHub Actions
6. Click **"Generate token"**
7. **Copy the token immediately** — you will not see it again

> ⚠️ **WARNING**: Treat your Personal Access Token like a password. Never commit it to a repository, share it publicly, or store it in plain text.

#### Git Credential Manager

Git Credential Manager (GCM) securely stores your credentials so you don't have to enter your token every time.

- **Linux**: You can use `git-credential-libsecret` or `git-credential-store` (less secure, stores in plain text)
- **macOS**: Uses the macOS Keychain automatically
- **Windows**: Git for Windows includes GCM by default

To cache credentials in memory temporarily (Linux):

```bash
git config --global credential.helper cache
```

To store credentials permanently (less secure):

```bash
git config --global credential.helper store
```

> **Note**: With `store`, credentials are saved in `~/.git-credentials` as plain text. Use this only on personal machines you trust.

### SSH Authentication (Recommended)

SSH authentication uses a **key pair** — a private key (stays on your computer) and a public key (added to GitHub). This is more secure and convenient than HTTPS tokens.

#### Step 1: Check for Existing SSH Keys

```bash
ls -al ~/.ssh
```

- `ls` — Lists files and directories.
- `-al` — `-a` shows hidden files, `-l` shows detailed information.
- `~/.ssh` — The hidden `.ssh` directory in your home folder (`~` means your home directory). This is where SSH keys are stored.

If you see files like `id_ed25519` and `id_ed25519.pub`, you already have SSH keys. You can use them or create new ones.

#### Step 2: Generate a New SSH Key

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

| Part | Meaning |
|---|---|
| `ssh-keygen` | A program that generates SSH key pairs |
| `-t` | Flag to specify the **type** (algorithm) of key to create |
| `ed25519` | A modern, secure, and fast cryptographic algorithm. Preferred over the older `rsa` algorithm |
| `-C` | Flag to add a **comment** to the key (typically your email, for identification) |
| `"your-email@example.com"` | The comment — helps you identify which key belongs to which account |

When prompted:
- **File location**: Press Enter to accept the default (`~/.ssh/id_ed25519`)
- **Passphrase**: Enter a strong passphrase (recommended) or press Enter for no passphrase. A passphrase adds extra security — even if someone steals your key file, they can't use it without the passphrase.

This creates two files:
- `~/.ssh/id_ed25519` — Your **private key** (SECRET — never share this)
- `~/.ssh/id_ed25519.pub` — Your **public key** (safe to share — add this to GitHub)

> 🔴 **CRITICAL WARNING**: **NEVER share, upload, commit, or expose your private key file:**
> ```text
> ~/.ssh/id_ed25519
> ```
> Only the `.pub` (public) key should be added to GitHub. If your private key is ever compromised, delete it from GitHub immediately and generate a new key pair.

#### Step 3: Start the SSH Agent

```bash
eval "$(ssh-agent -s)"
```

- `ssh-agent` — A background program that holds your private keys in memory so you don't have to type your passphrase every time.
- `-s` — Outputs shell commands to set up environment variables.
- `eval "$(...)"` — Executes the output of `ssh-agent -s` in your current shell, setting up the connection to the agent.

Expected output:

```text
Agent pid 12345
```

#### Step 4: Add Your Private Key to the SSH Agent

```bash
ssh-add ~/.ssh/id_ed25519
```

- `ssh-add` — Adds a private key to the SSH agent's memory.
- `~/.ssh/id_ed25519` — The path to your private key.

If you set a passphrase, you will be asked to enter it here (once).

#### Step 5: Copy Your Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

- `cat` — A command that displays the contents of a file in the terminal.
- `~/.ssh/id_ed25519.pub` — Your public key file.

Copy the entire output (it starts with `ssh-ed25519` and ends with your email).

#### Step 6: Add the Public Key to GitHub

1. Go to GitHub → **Settings** → **SSH and GPG keys**
2. Click **"New SSH key"**
3. **Title**: Give it a descriptive name (e.g., "Fedora Laptop")
4. **Key type**: Select "Authentication Key"
5. **Key**: Paste your public key
6. Click **"Add SSH key"**

#### Step 7: Test the Connection

```bash
ssh -T git@github.com
```

- `ssh` — The SSH client program.
- `-T` — Disables interactive terminal allocation (we just want to test, not open a shell session).
- `git@github.com` — Connect as the user `git` to GitHub's server.

Expected output:

```text
Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
```

This confirms your SSH connection to GitHub is working.

### SSH Troubleshooting

#### "Permission denied (publickey)"

This means GitHub rejected your SSH key. Common causes and fixes:

1. **SSH agent not running**: Run `eval "$(ssh-agent -s)"` and `ssh-add ~/.ssh/id_ed25519`
2. **Key not added to GitHub**: Verify your public key is added at GitHub → Settings → SSH and GPG keys
3. **Wrong key being used**: Run `ssh-add -l` to list keys loaded in the agent
4. **Using HTTPS URL instead of SSH**: Your remote should start with `git@github.com:` not `https://github.com/`

#### SSH Agent Not Running

```bash
# Start the agent
eval "$(ssh-agent -s)"

# Add your key
ssh-add ~/.ssh/id_ed25519
```

To auto-start the SSH agent, add these lines to your `~/.bashrc`:

```bash
# Auto-start SSH agent
if [ -z "$SSH_AUTH_SOCK" ]; then
   eval "$(ssh-agent -s)" > /dev/null
   ssh-add ~/.ssh/id_ed25519 2>/dev/null
fi
```

#### Wrong GitHub Account

If you have multiple GitHub accounts, check which account is being used:

```bash
ssh -T git@github.com
```

For multiple accounts, you can create an SSH config file:

```bash
nano ~/.ssh/config
```

Add:

```text
# Personal GitHub account
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519

# Work GitHub account
Host github-work
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_work
```

Then clone work repos using `git clone git@github-work:OWNER/REPO.git`.

#### Existing SSH Keys

If you already have keys and want to use them, simply add them to the agent:

```bash
ssh-add ~/.ssh/id_ed25519
```

If you want to start fresh, generate a new key (the old one will not be overwritten unless you use the same filename).

---

## 8. Creating a New Local Git Repository

A **repository** (repo) is a folder that Git is tracking. Let's create one from scratch.

### Step-by-Step

```bash
mkdir my-project
```

- `mkdir` — **M**ake **d**irectory. Creates a new folder.

```bash
cd my-project
```

- `cd` — **C**hange **d**irectory. Moves your terminal into the folder.

```bash
git init
```

- `git init` — **Init**ializes a new Git repository in the current directory. This creates a hidden `.git` folder that stores all of Git's tracking data.

Output:

```text
Initialized empty Git repository in /home/user/my-project/.git/
```

### What Happens After `git init`?

A hidden directory called `.git` is created inside your project folder. This directory contains:

| Contents | Purpose |
|---|---|
| `HEAD` | Points to the current branch |
| `config` | Local repository configuration |
| `objects/` | Stores all commits, files, and trees (Git's database) |
| `refs/` | Stores branch and tag pointers |
| `hooks/` | Scripts that can run automatically on certain Git events |
| `index` | The staging area data |

> ⚠️ **WARNING**: Never manually edit or delete the `.git` directory unless you know exactly what you are doing. Deleting it removes all Git history for the project.

### Creating and Tracking Your First File

```bash
touch README.md
```

- `touch` — Creates an empty file (or updates the timestamp of an existing file).

```bash
git status
```

Output shows `README.md` as **untracked** — Git sees the file but is not tracking changes to it.

```bash
git add README.md
```

- `git add` — Moves the file to the **staging area** (index), preparing it for the next commit.

```bash
git commit -m "docs: add initial README"
```

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `commit` | Creates a new commit (a saved snapshot of staged changes) |
| `-m` | Inline message flag |
| `"docs: add initial README"` | The commit message |

---

## 9. Creating a GitHub Repository and Pushing a Local Project

### Step 1: Create an Empty Repository on GitHub

1. Go to [https://github.com](https://github.com) and sign in
2. Click the **"+"** icon (top-right) → **"New repository"**
3. Fill in: **Repository name**, **Description** (optional), **Visibility** (Public/Private)
4. **IMPORTANT**: Do **NOT** check any of these boxes:
   - ❌ Add a README file
   - ❌ Add .gitignore
   - ❌ Choose a license
5. Click **"Create repository"**

> ⚠️ **WARNING**: If you initialize the GitHub repository with a README, `.gitignore`, or license, the remote will have its own commit. Your local project also has commits. Git will refuse to push because the histories are unrelated.

### Step 2: Push Your Local Project (SSH)

```bash
git init
git add .
git commit -m "chore: initial commit"
git branch -M main
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git push -u origin main
```

| Command | Meaning |
|---|---|
| `git add .` | Stage all files (`.` = current directory and everything inside) |
| `git branch -M main` | Force rename current branch to `main` (`-M` = `--move --force`) |
| `git remote add origin URL` | Connect local repo to GitHub. `origin` is the conventional remote name |
| `git push -u origin main` | Push `main` to `origin` and set upstream tracking (`-u`) |

### HTTPS Version

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

When pushing, Git will ask for your username and Personal Access Token.

---

## 10. Cloning an Existing Repository

**Cloning** creates a complete copy of a remote repository on your local machine — all files, branches, and the entire commit history.

### Clone Commands

```bash
# Clone via HTTPS
git clone https://github.com/USERNAME/REPOSITORY.git

# Clone via SSH (recommended)
git clone git@github.com:USERNAME/REPOSITORY.git

# Clone into a custom folder name
git clone URL custom-folder-name

# Clone a specific branch
git clone --branch branch-name URL

# Shallow clone (only latest commit — saves space and time)
git clone --depth 1 URL
```

### Clone vs Fork vs Download ZIP

| Action | Git History? | Remote Connection? | Where? |
|---|---|---|---|
| **Clone** | ✅ Full history | ✅ `origin` set up automatically | Local machine |
| **Fork** | ✅ Full history | ❌ Must set up remotes manually | GitHub (server) |
| **Download ZIP** | ❌ No history | ❌ No Git connection | Local machine |

### Why the Remote Is Named `origin`

When you clone, Git automatically creates a remote called `origin` pointing to the source URL. The name `origin` is just a convention — it means "the original source." You can rename it, but there's rarely a reason to.

---

## 11. Daily Git Workflow

### Basic Daily Workflow

```bash
# 1. Check the current state of your repository
git status

# 2. Pull the latest changes from the remote
git pull

# 3. Create a new branch for your work
git switch -c feature/login-page

# 4. Make your changes (edit files, write code)

# 5. Stage all changes
git add .

# 6. Commit with a descriptive message
git commit -m "feat: add login page"

# 7. Push your branch to GitHub
git push -u origin feature/login-page
```

| Step | Command | Why |
|---|---|---|
| 1 | `git status` | See which files are modified, staged, or untracked |
| 2 | `git pull` | Get the latest code from your team |
| 3 | `git switch -c feature/login-page` | Create a separate branch so your work doesn't affect `main` |
| 5 | `git add .` | Mark all changes as ready to be committed |
| 6 | `git commit -m "..."` | Save a snapshot of your changes |
| 7 | `git push -u origin feature/login-page` | Upload your branch to GitHub |

### Safer Workflow (Recommended for Teams)

```bash
git fetch origin
git status
git pull --rebase origin main
```

- `git fetch origin` downloads changes but does **not** modify your files.
- `git pull --rebase origin main` replays your local commits on top of the latest remote changes, creating a cleaner, linear history.

---

## 12. Understanding the Git File Lifecycle

### File States

| State | Meaning |
|---|---|
| **Untracked** | Git doesn't know about this file |
| **Modified** | Tracked file changed since last commit, but not staged |
| **Staged** | Changes added to the staging area, ready to commit |
| **Committed** | Changes saved in a commit in the local repository |
| **Pushed** | Commit uploaded to the remote repository |

### ASCII Flow Diagram

```text
 Working Directory          Staging Area           Local Repository        Remote Repository
 (your files)               (index)                (.git database)         (GitHub)
       |                        |                        |                       |
       |   git add              |                        |                       |
       |----------------------->|                        |                       |
       |                        |   git commit           |                       |
       |                        |----------------------->|                       |
       |                        |                        |   git push            |
       |                        |                        |---------------------->|
       |                        |                        |                       |
       |                        |                        |   git fetch           |
       |                        |                        |<----------------------|
       |                        |                        |                       |
       |   git pull (fetch + merge)                      |                       |
       |<------------------------------------------------|                       |
       |                        |                        |                       |
       |   git restore          |                        |                       |
       |<-----------------------|                        |                       |
```

### The Four Areas

1. **Working Directory** — The actual folder with real files you can see and edit.
2. **Staging Area (Index)** — Where you collect changes before committing. Like a shopping cart before checkout.
3. **Local Repository** — The `.git` directory storing all commits, branches, and history on your computer.
4. **Remote Repository** — A server copy (like GitHub) for backup and collaboration.

---

## 13. Checking Repository Status and Differences

```bash
git status              # Full status of working directory and staging area
git status --short      # Compact version with symbols
git diff                # Unstaged changes (working dir vs staging area)
git diff --staged       # Staged changes (staging area vs last commit)
git diff HEAD           # All changes (working dir vs last commit)
git diff branch-one..branch-two   # Differences between two branches
git diff commit-one commit-two    # Differences between two commits
```

### Status Symbols

| Symbol | Meaning |
|---|---|
| `M` | Modified |
| `A` | Added (new file staged) |
| `D` | Deleted |
| `R` | Renamed |
| `??` | Untracked |
| `UU` | Both sides modified (merge conflict) |

---

## 14. Adding Files to the Staging Area

```bash
git add filename       # Stage a specific file
git add folder/        # Stage an entire folder
git add .              # Stage all changes in current directory
git add -A             # Stage all changes in entire repository
git add -u             # Stage only modified/deleted tracked files (not new)
git add -p             # Interactively choose hunks to stage
```

| Command | New Files | Modified | Deleted |
|---|---|---|---|
| `git add filename` | ✅ | ✅ | ✅ |
| `git add .` | ✅ | ✅ | ✅ |
| `git add -A` | ✅ | ✅ | ✅ |
| `git add -u` | ❌ | ✅ | ✅ |
| `git add -p` | ❌ | ✅ (interactive) | ❌ |

> ⚠️ **WARNING**: `git add .` may stage unintended files if `.gitignore` is not configured properly. Always run `git status` after staging to verify.

---

## 15. Creating Commits

### What a Commit Contains

| Component | Description |
|---|---|
| **Commit hash** | Unique 40-character SHA-1 identifier |
| **Author** | Name and email |
| **Timestamp** | When the commit was created |
| **Message** | Description of what changed |
| **Parent commit(s)** | Reference to the previous commit(s) |
| **Snapshot** | Complete state of all tracked files |

### Commands

```bash
git commit -m "feat: add authentication"      # Commit with inline message
git commit                                      # Open editor for message
git commit -am "fix: correct navbar alignment"  # Stage tracked + commit
git commit --amend                              # Modify last commit
git commit --amend --no-edit                    # Add to last commit silently
```

> ⚠️ `git commit -am` does **NOT** include new untracked files. You must `git add` new files first.

> ⚠️ `--amend` rewrites the last commit. If already pushed, you'll need `git push --force-with-lease`. Only amend unpushed commits.

### Conventional Commits

| Type | Use When |
|---|---|
| `feat:` | Adding a new feature |
| `fix:` | Fixing a bug |
| `docs:` | Documentation changes only |
| `style:` | Code formatting (not CSS styling) |
| `refactor:` | Restructuring code without changing behavior |
| `test:` | Adding or updating tests |
| `chore:` | Maintenance tasks, dependencies, config |
| `perf:` | Performance improvements |
| `build:` | Build system or dependency changes |
| `ci:` | CI/CD configuration changes |
| `revert:` | Reverting a previous commit |

---

## 16. Viewing Commit History

```bash
git log                                    # Full commit log
git log --oneline                          # One line per commit
git log --oneline --graph --decorate --all # Visual branch graph
git show                                   # Details of latest commit
git show COMMIT_HASH                       # Details of specific commit
git show --stat COMMIT_HASH                # Files changed in a commit
git blame filename                         # Who changed each line
```

To exit `git log`, press `q`.

### Understanding Log Output

```text
commit a1b2c3d (HEAD -> main, origin/main, tag: v1.0.0)
```

- `HEAD -> main` — You are on the `main` branch
- `origin/main` — The remote is at the same commit (in sync)
- `tag: v1.0.0` — This commit is tagged

---

## 17. Working with Remote Repositories

A **remote** is a reference to a repository on another server (like GitHub).

```bash
git remote                          # List remote names
git remote -v                       # List remotes with URLs
git remote add origin URL           # Add a new remote
git remote get-url origin           # View a remote's URL
git remote set-url origin NEW_URL   # Change a remote's URL
git remote rename origin old-origin # Rename a remote
git remote remove origin            # Remove a remote
git ls-remote origin                # List all references on a remote
```

`origin` is not a Git keyword — it's a convention (the "original" source). You can name remotes anything.

---

## 18. Push Commands

```bash
git push                              # Push to tracked remote branch
git push origin main                  # Push specific branch to remote
git push -u origin main               # Push and set upstream tracking
git push --all origin                 # Push all local branches
git push --tags                       # Push all tags
git push origin --delete branch-name  # Delete a remote branch
git push --force-with-lease           # Safer force push
```

### Understanding Tracking

| Term | Meaning |
|---|---|
| **Local branch** | A branch on your computer |
| **Remote branch** | A branch on the remote server |
| **Remote-tracking branch** | Local read-only reference tracking a remote branch (e.g., `origin/main`) |
| **Upstream tracking** | The link between local and remote branches, set with `-u` |

> 🔴 **CRITICAL WARNING**: **Force pushing rewrites remote history**. Never force push shared branches. Always prefer `--force-with-lease` over `--force`. Force pushing is acceptable only on your own feature branches.

---

## 19. Pull and Fetch Commands

```bash
git fetch                         # Fetch from default remote
git fetch origin                  # Fetch from specific remote
git fetch --all                   # Fetch from all remotes
git fetch --prune                 # Fetch and remove stale refs
git pull                          # Fetch + merge
git pull origin main              # Pull from specific remote/branch
git pull --rebase                 # Fetch + rebase
git pull --rebase origin main     # Rebase from specific remote/branch
```

```text
git pull = git fetch + git merge (by default)
```

| Method | What It Does | History | Best For |
|---|---|---|---|
| `git fetch` | Downloads only, no merge | No change | Inspecting before integrating |
| `git pull` (merge) | Fetches + merges | Non-linear | Preserving exact history |
| `git pull --rebase` | Fetches + replays commits | Linear, clean | Clean history before PR |

---

## 20. Branching

A **branch** is a lightweight, movable pointer to a commit — an independent line of development.

```bash
git branch                           # List local branches
git branch -a                        # List all branches (local + remote)
git branch -r                        # List remote-tracking branches only
git branch feature/login             # Create a new branch
git switch feature/login             # Switch to a branch
git switch -c feature/login          # Create AND switch
git checkout feature/login           # Switch (older command)
git checkout -b feature/login        # Create AND switch (older)
git branch -m new-name               # Rename current branch
git branch -d branch-name            # Delete (safe — refuses if not merged)
git branch -D branch-name            # Delete (forced)
git push origin --delete branch-name # Delete a remote branch
```

### `switch` vs `checkout`

`git switch` (Git 2.23+) is specifically for changing branches. `git checkout` was overloaded — it switched branches AND restored files. Use `git switch` for branches and `git restore` for files.

### Branch Types

| Type | Example | Description |
|---|---|---|
| **Local branch** | `feature/login` | On your machine, you can commit to it |
| **Remote branch** | `main` on GitHub | On the server |
| **Remote-tracking branch** | `origin/main` | Local read-only copy tracking a remote branch |

---

## 21. Merging Branches

```bash
git switch main
git pull origin main
git merge feature/login
git push origin main
```

### Merge Strategies

| Strategy | When | Creates Merge Commit? |
|---|---|---|
| **Fast-forward** | Target has no new commits | ❌ (pointer moves forward) |
| **Three-way merge** | Both branches have diverged | ✅ |
| **`--no-ff`** | Force a merge commit | ✅ (always) |
| **Squash** | Flatten messy commits | ❌ (one new commit needed) |

```bash
git merge --no-ff feature/login   # Force merge commit
git merge --squash feature/login  # Squash all commits into one
git merge --abort                 # Cancel in-progress merge
```

---

## 22. Merge Conflicts

A **merge conflict** occurs when two branches changed the **same part of the same file** differently.

### Conflict Markers

```text
<<<<<<< HEAD
Current branch content
=======
Incoming branch content
>>>>>>> feature/login
```

| Marker | Meaning |
|---|---|
| `<<<<<<< HEAD` | Start of current branch's version |
| `=======` | Separator |
| `>>>>>>> feature/login` | End of incoming branch's version |

### Resolution Workflow

```bash
git status                  # See which files have conflicts
# Edit conflicted files — remove markers, keep correct content
git add conflicted-file     # Stage the resolved file
git commit                  # Complete the merge
git push                    # Push the result
```

### Aborting

```bash
git merge --abort           # Cancel a merge
git rebase --abort          # Cancel a rebase
git rebase --continue       # Continue rebase after resolving conflict
```

### VS Code Conflict Resolution

VS Code shows buttons above each conflict: **Accept Current Change**, **Accept Incoming Change**, **Accept Both Changes**, **Compare Changes**.

---

## 23. Undoing Changes Safely

### Decision Table

| Situation | Command | Risk |
|---|---|---|
| Discard file changes (not staged) | `git restore filename` | ⚠️ Loses unsaved changes |
| Unstage a file (keep changes) | `git restore --staged filename` | Safe |
| Undo last commit (keep staged) | `git reset --soft HEAD~1` | Safe if not pushed |
| Undo last commit (keep unstaged) | `git reset --mixed HEAD~1` | Safe if not pushed |
| Undo last commit (delete changes) | `git reset --hard HEAD~1` | 🔴 Destructive |
| Undo a pushed commit safely | `git revert COMMIT_HASH` | Safe |
| Restore file from previous commit | `git restore --source=HEAD~1 filename` | Overwrites file |
| Delete untracked files | `git clean -fd` | 🔴 Destructive |

```bash
git restore filename                       # Discard working dir changes
git restore .                              # Discard all working dir changes
git restore --staged filename              # Unstage a file
git restore --source=HEAD~1 filename       # Restore from specific commit
git revert COMMIT_HASH                     # Create undo commit (safe)
git reset --soft HEAD~1                    # Undo commit, keep staged
git reset --mixed HEAD~1                   # Undo commit, keep unstaged
git reset --hard HEAD~1                    # Undo commit, delete everything
git clean -n                               # Preview untracked file deletion
git clean -fd                              # Delete untracked files and dirs
```

> 🔴 **WARNING**: `git reset --hard` and `git clean -fd` are **destructive** — they permanently delete changes with no easy recovery.

---

## 24. Stashing Changes

**Stashing** temporarily saves uncommitted changes so you can work on something else.

```bash
git stash                              # Stash tracked changes
git stash push -m "unfinished login"   # Stash with descriptive message
git stash list                         # List all stashes
git stash show                         # Show stash summary
git stash show -p                      # Show full stash diff
git stash apply                        # Apply most recent stash (keep in list)
git stash apply stash@{0}              # Apply specific stash
git stash pop                          # Apply and remove from list
git stash drop stash@{0}              # Delete a specific stash
git stash clear                        # Delete ALL stashes
git stash -u                           # Include untracked files
```

| Command | Applies? | Removes from List? |
|---|---|---|
| `git stash apply` | ✅ | ❌ |
| `git stash pop` | ✅ | ✅ |

> ⚠️ `git stash clear` permanently removes all stashes. Stash is for temporary storage — for long-term work, create a branch and commit instead.

---

## 25. Rebasing

**Rebasing** replays your commits on top of another branch's latest commit, creating a clean linear history.

```text
Before:   main: A --- B --- C        After:   main: A --- B --- C
                     \                                           \
          feature:    D --- E                  feature:            D' --- E'
```

```bash
git switch feature/login
git fetch origin
git rebase origin/main        # Rebase onto latest main
git rebase --continue         # Continue after conflict resolution
git rebase --skip             # Skip current conflicting commit
git rebase --abort            # Cancel rebase
git rebase -i HEAD~3          # Interactive rebase (last 3 commits)
```

### Interactive Rebase Actions

| Action | Meaning |
|---|---|
| `pick` | Keep the commit as is |
| `reword` | Keep but change the message |
| `edit` | Pause to amend this commit |
| `squash` | Combine with previous (keep both messages) |
| `fixup` | Combine with previous (discard this message) |
| `drop` | Delete this commit |

### Merge vs Rebase

| Aspect | Merge | Rebase |
|---|---|---|
| History | Non-linear (merge commits) | Linear (clean) |
| Commit hashes | Preserved | Rewritten |
| Safety | Safe for shared branches | Dangerous if already pushed |

> 🔴 **WARNING**: Never rebase commits that have been pushed to a shared branch. Rebase only your own unpushed, local commits.

---

## 26. .gitignore

A `.gitignore` file tells Git which files to **ignore** (not track).

### Example for Node.js / Next.js

```gitignore
node_modules/
.next/
dist/
build/
.env
.env.local
.env.*.local
coverage/
*.log
.DS_Store
.vscode/
.idea/
```

| Pattern | Ignores |
|---|---|
| `node_modules/` | Dependencies folder |
| `.next/` | Next.js build cache |
| `.env` | Environment variables with secrets |
| `*.log` | All log files |
| `.DS_Store` | macOS system file |

> 🔴 **CRITICAL**: `.env` files contain API keys, passwords, and secrets. Never commit them. If already committed, they remain in Git history even after deletion.

### Untracking Already Tracked Files

```bash
git rm --cached .env                  # Stop tracking .env (keep file locally)
git rm -r --cached node_modules       # Stop tracking directory
git commit -m "chore: stop tracking sensitive file"
git check-ignore -v filename          # Check which rule ignores a file
```

---

## 27. Git Tags and GitHub Releases

A **tag** is a label pointing to a specific commit. Tags don't move like branches.

```bash
git tag                                    # List all tags
git tag v1.0.0                             # Create lightweight tag
git tag -a v1.0.0 -m "First stable release" # Create annotated tag
git show v1.0.0                            # Show tag details
git push origin v1.0.0                     # Push specific tag
git push origin --tags                     # Push all tags
git tag -d v1.0.0                          # Delete local tag
git push origin --delete v1.0.0            # Delete remote tag
```

### Semantic Versioning: `vMAJOR.MINOR.PATCH`

| Part | Increment When |
|---|---|
| **MAJOR** | Breaking changes |
| **MINOR** | New features (backward-compatible) |
| **PATCH** | Bug fixes (backward-compatible) |

### Git Tags vs GitHub Releases

Tags are Git labels. Releases are a GitHub feature built on tags — they include a title, description, changelog, and downloadable assets.

---

## 28. Forking and Open-Source Contribution

**Forking** creates a copy of someone else's repository under your GitHub account.

### Complete Contribution Workflow

```bash
# 1. Fork on GitHub (click "Fork" button)
# 2. Clone YOUR fork
git clone git@github.com:YOUR_USERNAME/PROJECT.git
cd PROJECT

# 3. Add the ORIGINAL repo as "upstream"
git remote add upstream git@github.com:ORIGINAL_OWNER/PROJECT.git
git remote -v

# 4. Fetch latest from original
git fetch upstream

# 5. Update your main
git switch main
git rebase upstream/main

# 6. Create a contribution branch
git switch -c fix/issue-description

# 7. Make changes, commit, push
git add .
git commit -m "fix: resolve issue description"
git push -u origin fix/issue-description

# 8. Open a Pull Request on GitHub
```

| Term | Meaning |
|---|---|
| **Origin** | Your fork (you have write access) |
| **Upstream** | The original repository |
| **Contributor** | You |
| **Maintainer** | The original repo owner |

### Keeping a Fork Updated

```bash
git fetch upstream
git switch main
git rebase upstream/main
git push origin main
```

---

## 29. Pull Requests

A **Pull Request (PR)** proposes changes from one branch to another for review.

### Workflow

1. Create a feature branch and make changes
2. Push: `git push -u origin feature/user-profile`
3. On GitHub, click "Compare & pull request"
4. Write a clear title and description
5. Link issues: `Closes #42`
6. Request review
7. Address feedback (commit and push to the same branch — PR updates automatically)
8. Merge and delete the branch

### PR Template

```markdown
## Description
Brief description of the changes.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## How Has This Been Tested?
Describe tests you ran.

## Checklist
- [ ] Self-reviewed
- [ ] Documentation updated
- [ ] Tests pass locally
- [ ] No new warnings

## Related Issues
Closes #ISSUE_NUMBER
```

---

## 30. GitHub Issues and Discussions

### Issues

Issues track bugs, feature requests, and tasks. They include **labels**, **milestones**, **assignees**, and **projects**.

### Closing Issues Automatically

Include in commit messages or PR descriptions:

```text
Closes #42
Fixes #42
Resolves #42
```

When the commit is pushed to the default branch or the PR is merged, the issue closes automatically.

### Discussions

A forum-like space for Q&A, brainstorming, and announcements. Enable at **Settings → General → Features → Discussions**.

---

## 31. GitHub Actions

GitHub Actions automates tasks (CI/CD) when events happen in your repository.

### Example: Node.js CI Workflow

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

| Section | Meaning |
|---|---|
| `name: CI` | Workflow name |
| `on: push/pull_request` | Events that trigger the workflow |
| `runs-on: ubuntu-latest` | Machine type |
| `uses: actions/checkout@v4` | Clones your repo onto the runner |
| `run: npm ci` | Installs dependencies |
| `run: npm test` | Runs your test suite |

---

## 32. Removing Files from Git History

```bash
git rm filename                        # Delete file and stage removal
git rm --cached filename               # Stop tracking (keep file locally)
git commit -m "chore: stop tracking"
```

> 🔴 Removing a file from the latest version does NOT remove it from older commits. For secrets in history, use `git filter-repo`:

```bash
# Install (Fedora)
sudo dnf install git-filter-repo

# Remove file from ALL history
git filter-repo --invert-paths --path .env
```

> **After rewriting history**: Revoke exposed secrets, force push (`git push --force --all`), ask collaborators to re-clone.

---

## 33. GitHub CLI

```bash
gh auth login                  # Authenticate
gh auth status                 # Check auth status
gh repo create                 # Create a repository
gh repo clone OWNER/REPOSITORY # Clone a repo
gh issue list                  # List issues
gh issue create                # Create an issue
gh pr create                   # Create a pull request
gh pr list                     # List PRs
gh pr checkout PR_NUMBER       # Check out PR locally
gh pr view                     # View PR details
gh pr merge                    # Merge a PR
gh repo view --web             # Open repo in browser
```

Install: `sudo dnf install gh` (Fedora) / `brew install gh` (macOS) / `sudo apt install gh` (Ubuntu).
---

## 34. Useful Inspection Commands

These commands help you inspect and understand the state of your repository.

```bash
# Show the root directory of the repository
git rev-parse --show-toplevel
```

Prints the absolute path to the top-level directory of the repository. Useful when you're deep inside subdirectories and want to know the repo root.

```bash
# Show the full hash of the current commit
git rev-parse HEAD
```

```bash
# Show the name of the current branch
git branch --show-current
```

```bash
# Show repository status
git status
```

```bash
# Show a summary of commits per author
git shortlog
```

Groups commits by author and shows how many each person made.

```bash
# Show repository size information
git count-objects -v
```

Displays the number and size of objects in the Git database.

```bash
# Show a log of all HEAD movements (the reflog)
git reflog
```

The **reflog** records every time `HEAD` changes — commits, checkouts, rebases, resets, etc. This is your safety net for recovering "lost" commits.

```bash
# Check the integrity of the Git database
git fsck
```

Verifies the connectivity and validity of objects in the Git database. Useful for detecting corruption.

### When `git reflog` Saves the Day

If you accidentally run `git reset --hard` and lose commits, the reflog still has a record of where HEAD was. You can recover:

```bash
# View the reflog
git reflog

# Find the commit hash from before the mistake
# Then reset back to it
git reset --hard COMMIT_HASH
```

> **Note**: Reflog entries expire (default: 90 days for reachable, 30 days for unreachable). Act quickly if you need to recover.

---

## 35. Common Errors and Solutions

### 1. `fatal: not a git repository`

**What it means**: You're trying to run a Git command in a directory that is not a Git repository.

**Why it happens**: You haven't run `git init` or you're in the wrong directory.

**Solution**:

```bash
# Navigate to the correct directory, or initialize Git:
git init
```

---

### 2. `remote origin already exists`

**What it means**: You're trying to add a remote named `origin`, but one already exists.

**Why it happens**: You already added a remote or cloned the repo.

**Solution**:

```bash
# Check existing remotes
git remote -v

# Change the existing URL
git remote set-url origin NEW_URL

# Or remove and re-add
git remote remove origin
git remote add origin NEW_URL
```

---

### 3. `repository not found`

**What it means**: Git cannot find the remote repository at the given URL.

**Why it happens**: Typo in URL, repository is private and you don't have access, or the repo was deleted.

**Solution**: Verify the URL, check your access permissions, and ensure the repository exists on GitHub.

---

### 4. `permission denied (publickey)`

**What it means**: SSH authentication failed.

**Why it happens**: SSH key not added to GitHub, SSH agent not running, or wrong key being used.

**Solution**:

```bash
# Check if SSH agent is running
eval "$(ssh-agent -s)"

# Add your key
ssh-add ~/.ssh/id_ed25519

# Test connection
ssh -T git@github.com

# Verify key is on GitHub: Settings → SSH and GPG keys
```

---

### 5. `authentication failed`

**What it means**: Your HTTPS credentials are wrong.

**Why it happens**: Incorrect Personal Access Token, expired token, or using a password instead of a token.

**Solution**: Generate a new Personal Access Token on GitHub and use it as the password. Clear cached credentials if needed:

```bash
git config --global --unset credential.helper
```

---

### 6. `src refspec main does not match any`

**What it means**: You're trying to push to `main` but there is no `main` branch.

**Why it happens**: No commits have been made yet, or the branch has a different name (e.g., `master`).

**Solution**:

```bash
# Make at least one commit first
git add .
git commit -m "chore: initial commit"

# Ensure your branch is named main
git branch -M main
git push -u origin main
```

---

### 7. `failed to push some refs`

**What it means**: The remote has changes you don't have locally.

**Solution**:

```bash
git pull --rebase origin main
git push origin main
```

---

### 8. `updates were rejected because the remote contains work`

Same as above — pull before pushing:

```bash
git pull origin main
# Resolve any conflicts if needed
git push origin main
```

---

### 9. `refusing to merge unrelated histories`

**What it means**: The local and remote repos have no common ancestor (their histories are completely separate).

**Why it happens**: You initialized a GitHub repo with a README and also have local commits.

**Solution**:

```bash
git pull origin main --allow-unrelated-histories
```

> ⚠️ Use carefully. The best prevention is to create empty repos on GitHub when pushing existing local projects.

---

### 10. `your local changes would be overwritten by merge`

**What it means**: You have uncommitted changes that conflict with incoming changes.

**Solution**:

```bash
# Option 1: Stash your changes, pull, then re-apply
git stash
git pull
git stash pop

# Option 2: Commit your changes first
git add .
git commit -m "chore: save work in progress"
git pull
```

---

### 11. `detached HEAD`

**What it means**: You are not on any branch. HEAD points directly to a commit instead of a branch.

**Why it happens**: You checked out a specific commit hash, tag, or remote-tracking branch.

**Solution**:

```bash
# Go back to an existing branch
git switch main

# Or create a new branch from the detached state
git switch -c new-branch-name
```

---

### 12. Merge Conflict

See [Section 22: Merge Conflicts](#22-merge-conflicts) for a complete guide.

---

### 13. Accidentally Committed `.env`

```bash
# 1. Add .env to .gitignore
echo ".env" >> .gitignore

# 2. Remove .env from Git tracking (keep it locally)
git rm --cached .env

# 3. Commit the changes
git commit -m "chore: remove .env from tracking"

# 4. Push
git push
```

> 🔴 If the `.env` was pushed to a public repo, **revoke and regenerate all exposed credentials immediately**.

---

### 14. Accidentally Pushed a Large File

GitHub has a 100 MB file size limit. If you accidentally committed a large file:

```bash
# Remove the file
git rm --cached large-file.zip
git commit -m "chore: remove large file"

# If the file is in history, use git filter-repo
git filter-repo --invert-paths --path large-file.zip
git push --force-with-lease
```

Consider using [Git LFS](https://git-lfs.github.com/) for large files.

---

### 15. Wrong Email Used in Commits

To fix future commits:

```bash
git config --global user.email "correct-email@example.com"
```

To fix the most recent unpushed commit:

```bash
git commit --amend --author="Name <correct-email@example.com>" --no-edit
```

---

### 16. Wrong GitHub Account Selected

```bash
# Check current SSH identity
ssh -T git@github.com

# Check remote URLs
git remote -v

# Update if needed
git remote set-url origin git@github.com:CORRECT_USERNAME/REPO.git
```

---

### 17. `branch has no upstream branch`

```bash
git push -u origin BRANCH_NAME
```

The `-u` flag sets the upstream tracking branch.

---

### 18. Git Asks for Username and Password Repeatedly

Switch to SSH authentication or configure a credential helper:

```bash
# Switch remote to SSH
git remote set-url origin git@github.com:USERNAME/REPO.git

# Or configure credential caching
git config --global credential.helper cache
```

---

## 36. Complete Practical Workflows

### Workflow A: Start a New Project Locally and Push to GitHub

**Starting situation**: You have code on your computer but no GitHub repository.

```bash
# 1. Initialize Git
cd my-project
git init

# 2. Add .gitignore
# Create a .gitignore file with appropriate rules

# 3. Stage all files
git add .

# 4. Create the first commit
git commit -m "chore: initial project setup"

# 5. Create an EMPTY repo on GitHub (no README, no .gitignore)

# 6. Rename branch to main
git branch -M main

# 7. Add remote
git remote add origin git@github.com:USERNAME/REPOSITORY.git

# 8. Push
git push -u origin main
```

**Expected result**: Your code is now on GitHub. Future pushes only need `git push`.

**Common mistake**: Creating the GitHub repo with a README causes unrelated-history errors.

---

### Workflow B: Clone and Contribute

**Starting situation**: You want to contribute to an existing project.

```bash
# 1. Clone the repository
git clone git@github.com:USERNAME/REPOSITORY.git
cd REPOSITORY

# 2. Create a feature branch
git switch -c feature/add-dark-mode

# 3. Make your changes and commit
git add .
git commit -m "feat: add dark mode toggle"

# 4. Push your branch
git push -u origin feature/add-dark-mode

# 5. Create a Pull Request on GitHub
```

**Expected result**: A PR is created for review.

---

### Workflow C: Create and Merge a Feature Branch

```bash
# 1. Start from up-to-date main
git switch main
git pull origin main

# 2. Create feature branch
git switch -c feature/user-dashboard

# 3. Work and commit
git add .
git commit -m "feat: add user dashboard"

# 4. Push
git push -u origin feature/user-dashboard

# 5. Create PR, get it reviewed and approved

# 6. Merge on GitHub or locally:
git switch main
git pull origin main
git merge feature/user-dashboard
git push origin main

# 7. Clean up
git branch -d feature/user-dashboard
git push origin --delete feature/user-dashboard
```

---

### Workflow D: Fix a Merge Conflict

```bash
# 1. Attempt to merge
git switch main
git merge feature/header-redesign
# CONFLICT! Git tells you which files conflict.

# 2. Open the conflicted files and resolve manually
# Remove <<<<<<, =======, >>>>>> markers
# Keep the correct code

# 3. Stage the resolved files
git add resolved-file.js

# 4. Complete the merge
git commit

# 5. Push
git push origin main
```

**Common mistake**: Forgetting to remove all conflict markers before committing.

---

### Workflow E: Undo the Last Local Commit (Keep Changes)

**Starting situation**: You made a commit but it's not pushed yet and you want to undo it.

```bash
# Undo the commit, keep changes staged
git reset --soft HEAD~1

# Or: undo the commit, keep changes unstaged
git reset --mixed HEAD~1
```

**Expected result**: The commit is gone, but your changes are still in your files.

---

### Workflow F: Undo a Pushed Commit (Shared Branch)

**Starting situation**: A commit was pushed to `main` and needs to be undone safely.

```bash
# Create a new commit that reverses the changes
git revert COMMIT_HASH

# Push the revert commit
git push origin main
```

**Expected result**: The changes are undone without rewriting history. Everyone can safely pull.

**Common mistake**: Using `git reset` on a shared branch — this rewrites history and causes problems for others.

---

### Workflow G: Update a Fork

```bash
# 1. Fetch from the original repo
git fetch upstream

# 2. Switch to main
git switch main

# 3. Rebase onto the original's main
git rebase upstream/main

# 4. Push to your fork
git push origin main
```

---

### Workflow H: Accidentally Committed `.env`

```bash
# 1. Immediately add .env to .gitignore
echo ".env" >> .gitignore

# 2. Remove from tracking
git rm --cached .env

# 3. Commit
git commit -m "chore: remove .env from version control"

# 4. Push
git push

# 5. IMMEDIATELY revoke and regenerate all exposed credentials
```

---

### Workflow I: Change Remote URL from HTTPS to SSH

```bash
# Check current remote
git remote -v

# Change to SSH
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git

# Verify
git remote -v
```

---

### Workflow J: Recover a Lost Commit Using Reflog

**Starting situation**: You accidentally ran `git reset --hard` and lost commits.

```bash
# 1. View the reflog to find the lost commit
git reflog

# Output shows something like:
# a1b2c3d HEAD@{0}: reset: moving to HEAD~3
# e4f5g6h HEAD@{1}: commit: feat: add payment system
# ...

# 2. Reset back to the lost commit
git reset --hard e4f5g6h
```

**Expected result**: Your lost commits are restored.

**Common mistake**: Waiting too long — reflog entries expire after 30-90 days.


---

## 37. Git Command Anatomy

Understanding how to read Git commands is a fundamental skill. Every Git command follows a pattern:

```text
git <command> [options/flags] [arguments]
```

### Command Breakdown Examples

#### `git push -u origin main`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `push` | Uploads commits and references to a remote |
| `-u` | Sets the upstream tracking relationship |
| `origin` | The remote repository name |
| `main` | The branch being pushed |

#### `git commit -m "feat: add login"`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `commit` | Saves staged changes as a snapshot |
| `-m` | Inline message flag |
| `"feat: add login"` | The commit message |

#### `git clone --depth 1 git@github.com:USER/REPO.git`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `clone` | Creates a copy of a remote repository |
| `--depth 1` | Only download the latest commit (shallow clone) |
| `git@github.com:USER/REPO.git` | SSH URL of the repository |

#### `git switch -c feature/login`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `switch` | Changes the current branch |
| `-c` | Create a new branch before switching |
| `feature/login` | The name of the new branch |

#### `git log --oneline --graph --all`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `log` | Shows commit history |
| `--oneline` | One line per commit |
| `--graph` | ASCII art branch graph |
| `--all` | Show all branches |

#### `git reset --soft HEAD~1`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `reset` | Moves the branch pointer backward |
| `--soft` | Keep changes in the staging area |
| `HEAD~1` | One commit before current HEAD |

#### `git remote add origin URL`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `remote` | Manage remote connections |
| `add` | Create a new remote |
| `origin` | Name for the remote |
| `URL` | Address of the remote repository |

#### `git stash push -m "message"`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `stash` | Temporary storage for changes |
| `push` | Save current changes to the stash |
| `-m` | Add a descriptive message |
| `"message"` | The stash description |

#### `git diff --staged`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `diff` | Show differences between states |
| `--staged` | Compare staging area vs last commit |

#### `git tag -a v1.0.0 -m "Release"`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `tag` | Create a label for a commit |
| `-a` | Create an annotated tag |
| `v1.0.0` | Tag name |
| `-m` | Tag message flag |
| `"Release"` | The tag message |

#### `git merge --no-ff feature/login`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `merge` | Combine branches |
| `--no-ff` | Force a merge commit (no fast-forward) |
| `feature/login` | Branch to merge from |

#### `git rebase -i HEAD~3`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `rebase` | Replay commits onto a different base |
| `-i` | Interactive mode |
| `HEAD~3` | Rebase the last 3 commits |

#### `git rm --cached .env`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `rm` | Remove files from tracking |
| `--cached` | Remove from index only (keep file on disk) |
| `.env` | The file to stop tracking |

#### `git fetch --prune`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `fetch` | Download data from a remote |
| `--prune` | Remove references to deleted remote branches |

#### `git config --global user.name "Name"`

| Part | Meaning |
|---|---|
| `git` | Runs the Git program |
| `config` | Read or write settings |
| `--global` | Apply to all repositories for this user |
| `user.name` | The setting key |
| `"Name"` | The value |

---

## 38. Symbols and Terminal Syntax

Understanding terminal symbols is essential for reading and writing Git commands.

### Path Symbols

| Symbol | Meaning | Example |
|---|---|---|
| `.` | Current directory | `git add .` (add everything in the current dir) |
| `..` | Parent directory (one level up) | `cd ..` (go up one folder) |
| `~` | Home directory | `~/.ssh` means `/home/username/.ssh` |
| `/` | Directory separator / root directory | `/home/user/project` |

### Flag Symbols

| Symbol | Meaning | Example |
|---|---|---|
| `-` | Short flag (single letter) | `-m` (message), `-u` (upstream), `-a` (all) |
| `--` | Long flag (full word) | `--global`, `--staged`, `--oneline` |

### Shell Operators

| Symbol | Meaning | Example |
|---|---|---|
| `\|` | Pipe — sends output of one command as input to another | `git log --oneline \| head -5` |
| `>` | Redirect — writes output to a file (overwrites) | `echo "hello" > file.txt` |
| `>>` | Append — adds output to the end of a file | `echo ".env" >> .gitignore` |
| `&&` | AND — runs the next command only if the previous succeeded | `git add . && git commit -m "msg"` |
| `*` | Wildcard — matches any characters | `*.log` matches all `.log` files |
| `" "` | Quotes — groups words as a single argument | `git commit -m "my message"` |
| `' '` | Single quotes — same as double quotes but no variable expansion | `echo 'literal $text'` |
| `$VAR` | Environment variable — accesses the value of a variable | `echo $HOME` prints your home directory |

### Path Types

| Type | Description | Example |
|---|---|---|
| **Relative path** | Relative to your current directory | `./src/index.js`, `../package.json` |
| **Absolute path** | Full path from the root of the filesystem | `/home/user/project/src/index.js` |

### Git-Specific References

| Reference | Meaning |
|---|---|
| `HEAD` | Points to the current commit on the current branch |
| `HEAD~1` | One commit before HEAD (parent) |
| `HEAD~2` | Two commits before HEAD (grandparent) |
| `HEAD^` | First parent of HEAD (same as `HEAD~1` for non-merge commits) |
| `HEAD^2` | Second parent of HEAD (used for merge commits, refers to the merged branch) |
| `branch@{upstream}` | The remote-tracking branch that a local branch is set to track |
| `stash@{0}` | The most recent stash entry |
| `stash@{1}` | The second most recent stash entry |

#### Difference Between `~` and `^`

- `~` moves **back** through the first parent chain: `HEAD~3` = three commits back
- `^` selects which **parent** (for merge commits that have multiple parents): `HEAD^2` = the second parent

For non-merge commits, `HEAD~1` and `HEAD^` are identical.


---

## 39. Git Best Practices

### Daily Workflow Practices

1. **Pull before starting work** — Always run `git pull` (or `git fetch` + `git rebase`) at the beginning of each coding session to get the latest changes.

2. **Use feature branches** — Never work directly on `main`. Create a descriptive branch like `feature/user-auth` or `fix/navbar-overflow`.

3. **Keep commits small and focused** — Each commit should represent one logical change. Avoid committing unrelated changes together.

4. **Write meaningful commit messages** — Use Conventional Commits format. Future-you will thank present-you.

5. **Review staged changes before committing** — Run `git diff --staged` to verify exactly what you're about to commit.

6. **Run tests before pushing** — Make sure your code works before sharing it with the team.

### Security Practices

7. **Never commit secrets** — No passwords, API keys, tokens, private keys, or `.env` files. Use `.gitignore` to prevent accidental commits.

8. **Avoid force pushing shared branches** — Force pushing can cause data loss for collaborators. Use `--force-with-lease` if absolutely necessary, and only on your own branches.

9. **Sign commits when required** — For security-critical projects, use GPG or SSH signing to verify commit authorship.

### Collaboration Practices

10. **Protect the main branch** — Enable branch protection rules on GitHub to require pull requests and reviews before merging.

11. **Use pull requests** — Even for your own projects, PRs create a documented review trail.

12. **Delete merged branches** — Keep the repository clean by deleting branches after they're merged.

13. **Keep branches updated** — Regularly rebase or merge `main` into your feature branches to avoid large conflicts.

### Project Setup Practices

14. **Add a good README** — Document what the project does, how to install it, and how to use it.

15. **Add a license** — Without a license, the code is technically copyrighted and others cannot legally use it. Common choices: MIT, Apache 2.0, GPL.

16. **Configure `.gitignore` early** — Set up your `.gitignore` before the first commit to avoid tracking unnecessary files.

17. **Use a consistent branching strategy** — Adopt Git Flow, GitHub Flow, or Trunk-Based Development and stick with it.

---

## 40. Final Cheat Sheet

### Setup

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Install Git (Fedora) | `sudo dnf install git` | Install Git via package manager | Safe |
| Check version | `git --version` | Print installed Git version | Safe |
| Set username | `git config --global user.name "Name"` | Configure your name for commits | Safe |
| Set email | `git config --global user.email "email"` | Configure your email for commits | Safe |
| Set default branch | `git config --global init.defaultBranch main` | New repos use `main` | Safe |
| Set editor | `git config --global core.editor "code --wait"` | Use VS Code for Git messages | Safe |
| View config | `git config --list` | Show all settings | Safe |

### Repository Creation

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Initialize a repo | `git init` | Create a new Git repository | Safe |
| Clone a repo (SSH) | `git clone git@github.com:USER/REPO.git` | Copy a remote repo locally | Safe |
| Clone a repo (HTTPS) | `git clone https://github.com/USER/REPO.git` | Copy a remote repo locally | Safe |
| Shallow clone | `git clone --depth 1 URL` | Clone only latest commit | Safe |

### Status & Differences

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Check status | `git status` | Show file states | Safe |
| Short status | `git status --short` | Compact status output | Safe |
| Unstaged changes | `git diff` | Show working dir vs staging | Safe |
| Staged changes | `git diff --staged` | Show staging vs last commit | Safe |
| All changes | `git diff HEAD` | Show working dir vs last commit | Safe |

### Staging

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Stage a file | `git add filename` | Add file to staging area | Safe |
| Stage all | `git add .` | Stage all changes in current dir | Safe |
| Stage all (entire repo) | `git add -A` | Stage all changes everywhere | Safe |
| Stage tracked only | `git add -u` | Stage modified/deleted tracked files | Safe |
| Interactive staging | `git add -p` | Stage changes hunk by hunk | Safe |

### Commits

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Commit with message | `git commit -m "message"` | Save staged changes | Safe |
| Commit all tracked | `git commit -am "message"` | Stage tracked + commit | Safe |
| Amend last commit | `git commit --amend` | Modify the last commit | Use carefully |
| Amend without edit | `git commit --amend --no-edit` | Add staged changes to last commit | Use carefully |

### History

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Full log | `git log` | Show commit history | Safe |
| Compact log | `git log --oneline` | One line per commit | Safe |
| Graph log | `git log --oneline --graph --all` | Visual branch history | Safe |
| Show commit | `git show COMMIT_HASH` | Show commit details | Safe |
| File blame | `git blame filename` | Show who changed each line | Safe |
| Reflog | `git reflog` | Show all HEAD movements | Safe |

### Remote

| Task | Command | Meaning | Risk |
|---|---|---|---|
| List remotes | `git remote -v` | Show remotes with URLs | Safe |
| Add remote | `git remote add origin URL` | Connect to a remote repo | Safe |
| Change URL | `git remote set-url origin URL` | Update remote URL | Safe |
| Remove remote | `git remote remove origin` | Delete remote connection | Use carefully |

### Push

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Push (tracked) | `git push` | Upload to tracked remote | Safe |
| Push + set upstream | `git push -u origin main` | Push and track | Safe |
| Push all branches | `git push --all origin` | Push every branch | Use carefully |
| Push tags | `git push --tags` | Upload all tags | Safe |
| Delete remote branch | `git push origin --delete branch` | Remove branch from remote | Use carefully |
| Force push (safer) | `git push --force-with-lease` | Force push with safety check | Destructive |

### Pull & Fetch

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Fetch | `git fetch` | Download without merging | Safe |
| Fetch all | `git fetch --all` | Fetch from all remotes | Safe |
| Fetch + prune | `git fetch --prune` | Remove stale remote refs | Safe |
| Pull | `git pull` | Fetch + merge | Safe |
| Pull with rebase | `git pull --rebase` | Fetch + rebase | Safe |

### Branching

| Task | Command | Meaning | Risk |
|---|---|---|---|
| List branches | `git branch` | Show local branches | Safe |
| List all branches | `git branch -a` | Show local + remote branches | Safe |
| Create branch | `git branch name` | Create a new branch | Safe |
| Switch branch | `git switch name` | Change to a branch | Safe |
| Create + switch | `git switch -c name` | Create and switch in one step | Safe |
| Rename branch | `git branch -m new-name` | Rename current branch | Safe |
| Delete branch (safe) | `git branch -d name` | Delete merged branch | Safe |
| Delete branch (force) | `git branch -D name` | Delete any branch | Use carefully |

### Merge

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Merge branch | `git merge branch-name` | Combine branch into current | Safe |
| Merge no fast-forward | `git merge --no-ff branch` | Force merge commit | Safe |
| Squash merge | `git merge --squash branch` | Combine all commits into one | Safe |
| Abort merge | `git merge --abort` | Cancel in-progress merge | Safe |

### Rebase

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Rebase | `git rebase origin/main` | Replay commits on new base | Use carefully |
| Interactive rebase | `git rebase -i HEAD~3` | Edit/squash/reorder commits | Use carefully |
| Continue rebase | `git rebase --continue` | Continue after conflict fix | Safe |
| Abort rebase | `git rebase --abort` | Cancel rebase | Safe |

### Stash

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Stash changes | `git stash` | Save uncommitted work | Safe |
| Stash with message | `git stash push -m "msg"` | Save with description | Safe |
| List stashes | `git stash list` | Show all stashed items | Safe |
| Apply stash | `git stash apply` | Re-apply without removing | Safe |
| Pop stash | `git stash pop` | Apply and remove | Safe |
| Drop stash | `git stash drop stash@{0}` | Delete a specific stash | Use carefully |
| Clear all | `git stash clear` | Delete all stashes | Destructive |
| Include untracked | `git stash -u` | Stash untracked files too | Safe |

### Undo

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Discard file changes | `git restore filename` | Revert file to last commit | Destructive |
| Unstage a file | `git restore --staged filename` | Remove from staging area | Safe |
| Soft reset | `git reset --soft HEAD~1` | Undo commit, keep staged | Use carefully |
| Mixed reset | `git reset --mixed HEAD~1` | Undo commit, keep unstaged | Use carefully |
| Hard reset | `git reset --hard HEAD~1` | Undo commit, delete changes | Destructive |
| Revert a commit | `git revert COMMIT_HASH` | Create undo commit | Safe |
| Clean preview | `git clean -n` | Preview untracked file deletion | Safe |
| Clean (delete) | `git clean -fd` | Delete untracked files/dirs | Destructive |

### Tags

| Task | Command | Meaning | Risk |
|---|---|---|---|
| List tags | `git tag` | Show all tags | Safe |
| Lightweight tag | `git tag v1.0.0` | Create simple tag | Safe |
| Annotated tag | `git tag -a v1.0.0 -m "msg"` | Create detailed tag | Safe |
| Push tag | `git push origin v1.0.0` | Upload tag to remote | Safe |
| Push all tags | `git push origin --tags` | Upload all tags | Safe |
| Delete local tag | `git tag -d v1.0.0` | Remove local tag | Safe |
| Delete remote tag | `git push origin --delete v1.0.0` | Remove tag from remote | Use carefully |

### Cleanup

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Remove tracked file | `git rm filename` | Delete and stage removal | Use carefully |
| Untrack (keep file) | `git rm --cached filename` | Stop tracking, keep local | Safe |
| Delete remote branch | `git push origin --delete branch` | Remove from remote | Use carefully |
| Prune stale refs | `git fetch --prune` | Clean up deleted remote branches | Safe |

### GitHub CLI

| Task | Command | Meaning | Risk |
|---|---|---|---|
| Login | `gh auth login` | Authenticate with GitHub | Safe |
| Create repo | `gh repo create` | Create a new repository | Safe |
| Clone repo | `gh repo clone OWNER/REPO` | Clone a repository | Safe |
| Create issue | `gh issue create` | Open a new issue | Safe |
| List issues | `gh issue list` | Show open issues | Safe |
| Create PR | `gh pr create` | Open a pull request | Safe |
| List PRs | `gh pr list` | Show open PRs | Safe |
| Merge PR | `gh pr merge` | Merge a pull request | Use carefully |


---

## 41. Practice Exercises

### Exercise 1: Create Your First Repository

Create a new directory, initialize Git, add a `README.md` file, and make your first commit.

<details>
<summary>💡 Hints</summary>

Use `mkdir`, `cd`, `git init`, `touch`, `git add`, and `git commit -m`.
</details>

---

### Exercise 2: Track Multiple Files

Create three files (`index.html`, `style.css`, `script.js`), stage them, and commit with a meaningful message.

<details>
<summary>💡 Hints</summary>

Use `touch` to create files, `git add .` or `git add -A` to stage all, and `git commit -m "feat: add project skeleton"`.
</details>

---

### Exercise 3: View Your Commit History

Make three separate commits (each adding or modifying a different file), then view the history using different log formats.

<details>
<summary>💡 Hints</summary>

Try `git log`, `git log --oneline`, and `git log --oneline --graph --decorate --all`.
</details>

---

### Exercise 4: Create and Switch Branches

Create a branch called `feature/about-page`, switch to it, make a commit, then switch back to `main`.

<details>
<summary>💡 Hints</summary>

Use `git switch -c feature/about-page`, make changes, commit, then `git switch main`.
</details>

---

### Exercise 5: Merge a Branch

Merge your `feature/about-page` branch into `main`.

<details>
<summary>💡 Hints</summary>

Switch to `main` with `git switch main`, then run `git merge feature/about-page`.
</details>

---

### Exercise 6: Create a Merge Conflict and Resolve It

Create two branches that modify the same line of the same file. Try to merge and resolve the conflict.

<details>
<summary>💡 Hints</summary>

1. On `main`, edit line 1 of a file and commit.
2. Create `branch-b`, edit the same line 1 differently and commit.
3. Switch back to `main` and run `git merge branch-b`.
4. Open the file, remove conflict markers, choose the correct content.
5. Run `git add` and `git commit`.
</details>

---

### Exercise 7: Use `.gitignore`

Create a `.env` file and a `node_modules/` directory. Configure `.gitignore` so Git ignores them.

<details>
<summary>💡 Hints</summary>

Create a `.gitignore` file with these lines:
```
.env
node_modules/
```
Run `git status` to verify they are ignored.
</details>

---

### Exercise 8: Create and Push a Tag

Create an annotated tag `v1.0.0` and push it to a remote repository.

<details>
<summary>💡 Hints</summary>

Use `git tag -a v1.0.0 -m "First release"` and `git push origin v1.0.0`.
</details>

---

### Exercise 9: Use Git Stash

Start working on a feature, stash the changes, switch to another branch to fix a bug, then come back and apply your stash.

<details>
<summary>💡 Hints</summary>

Use `git stash push -m "wip: feature work"`, switch branches, fix the bug, switch back, and `git stash pop`.
</details>

---

### Exercise 10: Restore a File

Modify a file, then discard the changes using `git restore`.

<details>
<summary>💡 Hints</summary>

Edit a tracked file, then run `git restore filename`. Verify with `git status` that the changes are gone.
</details>

---

### Exercise 11: Undo a Commit (Soft Reset)

Make a commit, then undo it while keeping the changes staged.

<details>
<summary>💡 Hints</summary>

Use `git reset --soft HEAD~1`. Run `git status` to see that changes are still staged.
</details>

---

### Exercise 12: Push a Project to GitHub

Create a local project, create an empty GitHub repository, connect them, and push.

<details>
<summary>💡 Hints</summary>

Follow the workflow: `git init` → `git add .` → `git commit -m "initial commit"` → `git branch -M main` → `git remote add origin URL` → `git push -u origin main`.
</details>

---

### Exercise 13: Fork and Contribute

Fork a public repository, clone your fork, create a feature branch, make a change, and push.

<details>
<summary>💡 Hints</summary>

Fork on GitHub, `git clone` your fork, `git switch -c feature/improvement`, make changes, commit, and `git push -u origin feature/improvement`.
</details>

---

### Exercise 14: Create a Pull Request

Using the branch from Exercise 13, open a pull request on GitHub with a clear title and description.

<details>
<summary>💡 Hints</summary>

Go to your fork on GitHub. Click "Compare & pull request". Fill in the title and description. Submit.
</details>

---

### Exercise 15: Interactive Rebase

Make three commits with messy messages, then use interactive rebase to squash them into one clean commit.

<details>
<summary>💡 Hints</summary>

Run `git rebase -i HEAD~3`. Change `pick` to `squash` for the second and third commits. Save and write a clean combined message.
</details>

---

## 42. Quick Interview Questions

### 1. What is the difference between Git and GitHub?

**Answer**: Git is a distributed version control system (software) that runs locally on your computer to track file changes. GitHub is a cloud-based platform (service) that hosts Git repositories and provides collaboration features like pull requests, issues, and CI/CD.

### 2. What does `git clone` do?

**Answer**: `git clone` creates a complete local copy of a remote repository, including all files, branches, commit history, and tags. It also sets up a remote called `origin` pointing to the source URL.

### 3. What is the difference between clone and fork?

**Answer**: **Clone** copies a repository to your local machine. **Fork** copies a repository to your GitHub account (server-side). Forking is used to contribute to projects you don't have write access to.

### 4. What is the difference between `git pull` and `git fetch`?

**Answer**: `git fetch` downloads changes from the remote but does not modify your working files. `git pull` does `git fetch` + `git merge`, so it downloads AND integrates changes into your current branch.

### 5. What is the difference between merge and rebase?

**Answer**: **Merge** creates a new merge commit that combines two branches, preserving the branch history. **Rebase** replays your commits on top of another branch, creating a linear history but rewriting commit hashes.

### 6. What is the staging area?

**Answer**: The staging area (also called the index) is an intermediate area where you prepare changes before committing. It lets you select exactly which changes to include in the next commit.

### 7. What is HEAD in Git?

**Answer**: HEAD is a pointer to the current commit on the current branch. It usually points to the latest commit of the branch you have checked out.

### 8. What is a detached HEAD?

**Answer**: A detached HEAD occurs when HEAD points directly to a specific commit instead of a branch. This happens when you check out a commit hash, tag, or remote-tracking branch. Any commits made in this state are not on any branch.

### 9. What is `git reset --soft` vs `--mixed` vs `--hard`?

**Answer**:
- `--soft`: Moves HEAD back, keeps changes in the staging area
- `--mixed` (default): Moves HEAD back, keeps changes in the working directory (unstaged)
- `--hard`: Moves HEAD back, discards all changes (destructive)

### 10. What is the difference between `git reset` and `git revert`?

**Answer**: `git reset` moves the branch pointer backward, removing commits from history (rewrites history). `git revert` creates a new commit that undoes a previous commit's changes (preserves history). Use `revert` for shared/pushed commits.

### 11. What is a merge conflict?

**Answer**: A merge conflict occurs when two branches modify the same part of the same file in different ways. Git cannot automatically determine which version to keep, so it marks the conflict and requires manual resolution.

### 12. What is a fast-forward merge?

**Answer**: A fast-forward merge happens when the target branch has no new commits since the source branch was created. Git simply moves the branch pointer forward — no merge commit is needed.

### 13. What is `.gitignore`?

**Answer**: A `.gitignore` file specifies files and directories that Git should not track. It prevents unnecessary or sensitive files (like `node_modules/`, `.env`, build outputs) from being committed.

### 14. What is a commit hash?

**Answer**: A commit hash is a unique 40-character SHA-1 identifier generated for every commit. It uniquely identifies a commit and is used to reference specific commits in commands.

### 15. What is `git stash`?

**Answer**: `git stash` temporarily saves uncommitted changes (both staged and unstaged) so you can work on something else. You can later restore the stashed changes with `git stash apply` or `git stash pop`.

### 16. What are Git tags?

**Answer**: Tags are labels that point to specific commits, typically used to mark release versions (e.g., `v1.0.0`). Unlike branches, tags don't move — they permanently reference one commit.

### 17. What is a pull request?

**Answer**: A pull request (PR) is a GitHub feature that lets you propose changes from one branch to another. It enables code review, discussion, and approval before changes are merged.

### 18. What is `git reflog`?

**Answer**: `git reflog` records every time HEAD changes position — commits, checkouts, resets, rebases, etc. It's a safety net that can help recover "lost" commits after accidental resets.

### 19. What is a remote-tracking branch?

**Answer**: A remote-tracking branch (e.g., `origin/main`) is a local read-only reference that represents the last known state of a branch on a remote server. It's updated by `git fetch`.

### 20. What does `git push -u origin main` do?

**Answer**: It pushes the local `main` branch to the remote `origin` and sets up a tracking relationship (`-u`). After this, you can use `git push` and `git pull` without specifying the remote and branch.

### 21. Why should you not commit `.env` files?

**Answer**: `.env` files typically contain sensitive information like API keys, database passwords, and secrets. Committing them to a repository (especially public ones) exposes these credentials to anyone who can access the repo.

### 22. What is the difference between `git branch -d` and `git branch -D`?

**Answer**: `-d` is safe deletion — it refuses to delete a branch with unmerged commits. `-D` is forced deletion — it deletes the branch regardless of its merge status.

### 23. What is `origin` in Git?

**Answer**: `origin` is the default name given to the remote repository when you clone a project. It's just a convention — you can rename it to anything.

### 24. What is upstream in Git?

**Answer**: It can mean two things: (1) The original repository that a fork was created from, typically added as a remote named `upstream`. (2) The remote-tracking branch that a local branch is configured to track.

### 25. What does `git commit --amend` do?

**Answer**: It modifies the most recent commit. You can change the commit message or add new staged changes to the commit. It rewrites the commit (creates a new hash), so only use it on unpushed commits.

### 26. What is the difference between `git restore` and `git checkout`?

**Answer**: `git restore` is a modern command specifically for restoring file contents (discarding changes or unstaging files). `git checkout` is an older, overloaded command that handled both branch switching and file restoration. `git restore` and `git switch` were introduced to replace `git checkout` with clearer, purpose-specific commands.

### 27. What is `git cherry-pick`?

**Answer**: `git cherry-pick COMMIT_HASH` applies the changes from a specific commit onto your current branch. It creates a new commit with the same changes but a different hash. Useful for selectively applying commits from one branch to another.

### 28. What is `git bisect`?

**Answer**: `git bisect` helps you find which commit introduced a bug by performing a binary search through commit history. You mark commits as "good" or "bad" and Git narrows down the problematic commit.

### 29. What does `--force-with-lease` do?

**Answer**: It force pushes your changes to a remote but only if no one else has pushed new commits since your last fetch. It's a safer alternative to `--force` because it prevents accidentally overwriting a collaborator's work.

### 30. What is interactive rebase?

**Answer**: Interactive rebase (`git rebase -i`) lets you modify commits during the rebase process. You can reorder, squash, edit, reword, or drop commits. Commonly used to clean up commit history before creating a pull request.

### 31. How do you undo a pushed commit safely?

**Answer**: Use `git revert COMMIT_HASH` to create a new commit that undoes the changes. Then push the revert commit. This preserves history and is safe for shared branches. Avoid using `git reset` on pushed commits.

### 32. What is `git diff --staged`?

**Answer**: It shows the differences between the staging area and the last commit — the changes that will be included in the next commit. Also known as `git diff --cached`.

---

## Final Notes

This guide covers the essential Git and GitHub knowledge needed to work effectively on personal and team projects. Git is a vast tool with many advanced features, but mastering the fundamentals covered here will handle the vast majority of real-world workflows.

**Key resources for continued learning:**

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Pro Git Book (free)](https://git-scm.com/book/en/v2)
- [GitHub Skills](https://skills.github.com/)

---

> **Created with ❤️ as a comprehensive learning resource for developers starting their Git and GitHub journey.**

