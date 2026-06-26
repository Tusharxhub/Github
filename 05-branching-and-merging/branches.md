# Branches

## What is it?
A branch in Git is essentially an independent timeline of development. It allows you to duplicate the main code, isolate it in a separate workspace, make changes, and test them without ever affecting the original code.

## Why do we use it?
Imagine you are building a website and the `main` branch holds the live, working code that actual users see. 
Your boss asks you to build a complex new login system. If you start writing the code directly on the `main` branch, your website will be broken and unusable while you are half-finished. 

Instead, you create a branch called `feature-login`. You write code, test it, break it, and fix it entirely within this isolated branch. Meanwhile, the `main` branch remains perfectly stable. Once the login system is 100% finished and tested, you **merge** the branch back into `main`.

Branches are the foundation of professional team workflows. Every developer creates a new branch for every task they work on.

## Basic Syntax

**To see a list of all branches:**
```bash
git branch
```
*The branch with an asterisk (`*`) next to it is the one you are currently on.*

**To create a new branch:**
```bash
git branch <new_branch_name>
```

**To create a branch AND instantly switch to it (Recommended):**
```bash
git switch -c <new_branch_name>
```

## Branch Naming Conventions
In a professional environment, branches should be named descriptively so everyone knows what is being worked on.
- **Good:** `feature/user-login`, `bugfix/header-alignment`, `docs/update-readme`
- **Bad:** `my-branch`, `tushar-work`, `fixes`, `test2`

## How Branches Work Under the Hood
In many older version control systems, creating a branch literally copies every single file into a new folder, which is incredibly slow and takes up massive hard drive space.
In Git, a branch is just a lightweight, movable pointer to a specific commit. Creating a branch takes a fraction of a millisecond and takes up zero hard drive space, no matter how massive the project is. This is why Git users are encouraged to branch constantly!

## Common Mistakes
- **Working on the `main` branch:** You should almost never write new code directly on `main`. Always create a branch first.
- **Forgetting to switch:** Sometimes beginners create a branch (`git branch feature1`) but forget to actually switch to it (`git switch feature1`). They start writing code and realize they are still on `main`.
- **Not pulling `main` before branching:** Before you branch off `main`, always make sure `main` is fully up-to-date by running `git pull origin main`. Otherwise, your new branch will be based on outdated code.

## Quick Summary
- Branches allow for parallel, isolated development.
- The `main` branch should always contain stable, production-ready code.
- Use `git switch -c <name>` to create and move to a new branch.
- Branching in Git is lightning fast and uses zero space.
