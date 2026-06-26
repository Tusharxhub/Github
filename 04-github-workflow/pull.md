# Pull

## What is it?
`git pull` is the command used to download new commits from GitHub and immediately merge them into your local project.

## Why do we use it?
If you are working on a team, or working from two different computers, the GitHub repository might have new code that your current computer does not have. You use `git pull` to update your local files to match GitHub.

## Basic Syntax

```bash
git pull origin <branch_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git pull` | Downloads and merges remote changes |
| `origin` | The remote repository name |
| `<branch_name>` | The branch to pull from (usually `main`) |

## Example
To grab the latest changes from the main branch on GitHub:
```bash
git pull origin main
```

If you previously set up tracking (with `git push -u`), you can simply type:
```bash
git pull
```

## Common Mistakes
- **Pulling with uncommitted changes:** If you have unsaved work in your files, and you try to pull, Git might abort the pull to prevent overwriting your work. Always commit or stash your changes before pulling.
- **Merge conflicts during pull:** If you and someone else edited the exact same line of code, pulling will cause a merge conflict that you must fix manually.

## Quick Summary
- Downloads new code from GitHub and updates your local files.
- Essential for team collaboration.
- Always commit your current work before pulling to avoid issues.
