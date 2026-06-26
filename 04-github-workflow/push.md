# Push

## What is it?
`git push` is the command used to upload your local commits to a remote repository (like GitHub).

## Why do we use it?
Commits made using `git commit` are only saved on your laptop. If your laptop breaks, you lose your work. Pushing uploads those commits to GitHub so they are backed up, and so other team members can see them.

## Basic Syntax

```bash
git push -u origin <branch_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git push` | Uploads local commits |
| `-u` | Sets the upstream tracking (so next time you can just type `git push`) |
| `origin` | The name of the remote destination |
| `<branch_name>` | The branch you are pushing (usually `main`) |

## Example
For your very first push on a new project:
```bash
git push -u origin main
```
After you use `-u` once, for all future pushes you only need to type:
```bash
git push
```

## Common Mistakes
- **Pushing without committing:** You can only push commits. If you just made changes and didn't `add` and `commit` them, `git push` will say everything is up to date.
- **Push rejected (non-fast-forward):** This happens if someone else pushed code to GitHub, and your local repo doesn't have it yet. You must `git pull` before you can `git push`.

## Quick Summary
- Uploads your saved commits to GitHub.
- Use `git push -u origin main` the first time.
- Use `git push` after that.
- Always commit before pushing!
