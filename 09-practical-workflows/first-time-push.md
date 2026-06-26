# First Time Push Workflow

## What is it?
This is the step-by-step workflow for taking a project that exists ONLY on your local computer, and pushing it to GitHub for the very first time.

## Why do we use it?
You use this workflow when you start a new project locally, and later decide you want to back it up on GitHub.

## The Workflow

**Step 1: Initialize Git in your folder**
```bash
cd my-project
git init
```

**Step 2: Stage and commit your files**
```bash
git add .
git commit -m "Initial commit"
```

**Step 3: Rename branch to main (if necessary)**
```bash
git branch -M main
```

**Step 4: Create an EMPTY repository on GitHub**
Go to GitHub, create a new repo. Do **NOT** add a README, .gitignore, or license.

**Step 5: Link local repo to GitHub repo**
*(Copy the URL from GitHub)*
```bash
git remote add origin https://github.com/USERNAME/my-project.git
```

**Step 6: Push your code**
```bash
git push -u origin main
```

## Quick Summary
- `init` -> `add` -> `commit` -> `remote add` -> `push -u`.
- Make sure the GitHub repo is completely empty before linking and pushing.
