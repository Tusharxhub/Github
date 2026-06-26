# Push

## What is it?
`git push` is the command used to upload your local repository content (your commits) to a remote repository (like GitHub).

## Why do we use it?
Commits made using `git commit` are completely localized. They exist only on the hard drive of your laptop. If your laptop gets stolen or the hard drive crashes, you lose your work. Pushing uploads those commits to the cloud (GitHub) so they are securely backed up. Furthermore, if you are working on a team, pushing is how you share your code with the rest of the developers.

## Basic Syntax

For the very first push of a branch:
```bash
git push -u origin <branch_name>
```

For all future pushes on that branch:
```bash
git push
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git push` | Uploads local commits to a remote server |
| `-u` | Stands for "--set-upstream". It creates a permanent link between your local branch and the remote branch. |
| `origin` | The nickname of the remote destination (GitHub) |
| `<branch_name>` | The branch you are pushing (e.g., `main` or `feature-login`) |

## What actually happens during a push?
When you run `git push`, Git calculates the difference between your local branch and the remote branch on GitHub. It then securely packages the new commits, compresses them, and sends them over HTTPS or SSH. Once GitHub receives them, the remote branch is updated to match your local branch.

## Resolving Push Rejections (Non-Fast-Forward Error)
The most common error you will face is:
`error: failed to push some refs to 'https://github.com/...'`
`hint: Updates were rejected because the remote contains work that you do not have locally.`

**Why this happens:** Someone else (or you, from a different computer) pushed code to GitHub while you were working. GitHub refuses your push because accepting it would overwrite the other person's code.

**The Fix:** You must merge their code into yours before you can push.
1. Run `git pull origin main` (This downloads their code and merges it with yours).
2. Fix any merge conflicts if they exist.
3. Run `git push` again.

## Common Mistakes
- **Pushing without committing:** You can only push *commits*. If you just made changes in your code editor and didn't `add` and `commit` them, `git push` will say "Everything up-to-date", but your new code won't be on GitHub.
- **Pushing secrets:** If you accidentally commit an API key or password and run `git push`, it is now public on the internet. Hackers scan GitHub 24/7 for leaked keys. Never push `.env` files!

## Quick Summary
- Uploads your saved local commits to GitHub.
- Use `git push -u origin main` the very first time you push a branch.
- Use `git push` after that.
- Always commit before pushing!
- If a push is rejected, you must `git pull` first.
