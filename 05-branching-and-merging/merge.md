# Merge

## What is it?
`git merge` is the command used to combine the history and changes of two branches into one.

## Why do we use it?
After you finish building a new feature on a separate branch, you need to bring that finished code back into the `main` branch so it becomes part of the final project. Merging does exactly this.

## Basic Syntax

```bash
git merge <branch_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git merge` | Combines another branch into your current branch |
| `<branch_name>`| The name of the branch you want to pull IN to your active branch |

## Example
If you finished working on `feature-login` and want to merge it into `main`:
1. First, make sure you are ON the `main` branch:
   ```bash
   git switch main
   ```
2. Then, merge the feature branch INTO main:
   ```bash
   git merge feature-login
   ```

## Common Mistakes
- **Merging into the wrong branch:** Always check `git branch` or `git status` to make sure you are currently on the branch that should *receive* the changes (usually `main`).
- **Forgetting to commit first:** You should have a clean working directory before you try to merge.

## Quick Summary
- Combines the work from one branch into another.
- Always switch to the receiving branch (like `main`) first.
- Run `git merge <feature-branch>` to bring those changes in.
