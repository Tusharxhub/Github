# Open Source Contribution Workflow

## What is it?
This workflow explains how to contribute to a public open-source project where you do not have permission to push code directly.

## Why do we use it?
It utilizes a "Fork" to give you a personal copy of the project where you have full admin rights, allowing you to build features and then suggest them back to the original owner.

## The Workflow

**Step 1: Fork the project**
Go to the project on GitHub and click **Fork**. This creates a copy under your account.

**Step 2: Clone your fork**
```bash
git clone https://github.com/YOUR_USERNAME/project.git
cd project
```

**Step 3: Add the original repo as "upstream"**
This allows you to pull down updates that the original authors make.
```bash
git remote add upstream https://github.com/ORIGINAL_OWNER/project.git
```

**Step 4: Create a branch and make changes**
```bash
git switch -c fix-bug
git add .
git commit -m "fix: resolve crash on startup"
```

**Step 5: Sync with upstream (Crucial!)**
Before pushing, ensure your code doesn't conflict with recent updates to the original project.
```bash
git pull upstream main
```

**Step 6: Push to YOUR fork**
```bash
git push -u origin fix-bug
```

**Step 7: Open a Pull Request**
Go to the original repository on GitHub, click **Pull Requests**, and click **New Pull Request** to compare your fork against their main branch.

## Quick Summary
- Fork the original repo.
- Clone your fork.
- Set upstream to track the original.
- Branch, Commit, Push to your fork.
- Open PR on the original repo.
