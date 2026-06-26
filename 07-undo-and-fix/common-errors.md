# Common Errors

## What is it?
This is a collection of the most frequent errors beginners encounter when using Git, and how to fix them.

## 1. `fatal: not a git repository`
**Why it happens:** You are trying to run a Git command (like `git status` or `git add`) in a folder that has not been initialized with `git init`, or you forgot to `cd` into the cloned folder.
**How to fix:** Ensure you are in the correct folder, and run `git init` if it's a new project.

## 2. `error: failed to push some refs... (non-fast-forward)`
**Why it happens:** You are trying to `git push`, but someone else has pushed changes to GitHub that you don't have locally.
**How to fix:** Run `git pull origin main` to get their changes, resolve any conflicts, and then `git push` again.

## 3. `fatal: remote origin already exists`
**Why it happens:** You are trying to run `git remote add origin <url>`, but this repository already has a remote named "origin".
**How to fix:** If you want to change the URL, use `git remote set-url origin <new_url>`.

## 4. `Authentication failed`
**Why it happens:** You used your GitHub account password instead of a Personal Access Token (PAT) when pushing via HTTPS.
**How to fix:** Generate a PAT in GitHub settings and use it as your password in the terminal.

## Quick Summary
- Always read the error message carefully; Git usually tells you exactly how to fix it!
- Most push errors require a `pull` first.
- Most "not a git repo" errors mean you are in the wrong folder.
