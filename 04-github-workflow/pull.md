# Pull

## What is it?
`git pull` is the command used to download the latest changes from the remote GitHub repository and instantly merge them into your local repository. It is the exact opposite of `git push`.

## Why do we use it?
If you are working on a team, other developers are constantly pushing their new code to GitHub. Your local computer does not update automatically. To get their new code onto your computer so you can see it and test it, you must pull it. 

If you work alone but use two computers (like a desktop and a laptop), you will push from your desktop and pull from your laptop to keep them synchronized.

## Basic Syntax

```bash
git pull origin <branch_name>
```
*If you are simply pulling updates for the branch you are currently on, you can usually just type `git pull`.*

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git pull` | Downloads and merges new commits from the cloud |
| `origin` | The remote repository on GitHub |
| `<branch_name>`| The specific branch to pull down (usually `main`) |

## What actually happens during a pull?
`git pull` is actually a combination of two separate Git commands run back-to-back:
1. **`git fetch`**: Downloads all the new data and commits from GitHub but does NOT integrate them into your working files. It just saves them in the background.
2. **`git merge`**: Takes that downloaded data and merges it into your active files.

If you want to see what changes occurred on GitHub *before* you merge them into your files, you should run `git fetch` instead, review the logs, and then run `git merge` manually.

## Pulling with Merge Conflicts
If you modified `index.html` on your local computer, and a teammate modified the exact same lines in `index.html` and pushed it to GitHub, running `git pull` will trigger a **Merge Conflict**.

Git will pause and say: "I tried to pull their code and merge it into yours, but you both edited the same lines. I don't know which one to keep."
You will have to open your code editor, manually resolve the conflict by picking the correct lines of code, and then make a new commit to finish the pull.

## Common Mistakes
- **Forgetting to pull before you start working:** When you start your workday, the very first command you should run is `git pull origin main`. If you start writing code on outdated files, you will face nasty merge conflicts later when you try to push.
- **Pulling into a dirty working directory:** If you have uncommitted changes in your files, `git pull` might abort to prevent overwriting your unsaved work. Always `git commit` or `git stash` your work before pulling!

## Quick Summary
- Downloads new code from GitHub and merges it into your local files.
- Run `git pull origin main` frequently to stay up to date.
- Under the hood, it is a `fetch` followed by a `merge`.
- Always pull the latest code before you start working for the day.
