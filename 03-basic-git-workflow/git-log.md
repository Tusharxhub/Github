# Git Log

## What is it?
`git log` is a command that displays the commit history of your repository. It shows you who made a commit, when they made it, and the commit message.

## Why do we use it?
If you want to see what your team has been working on, find a specific old commit to revert to, or just check if your latest commit was successful, you use `git log`.

## Basic Syntax

```bash
git log
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git` | Runs the Git program |
| `log` | Displays the history of commits |

## Example
To see a full history:
```bash
git log
```

To see a shorter, easier-to-read version (one line per commit):
```bash
git log --oneline
```

*Note: If the log is very long, it opens in a viewer. Press `q` to quit and return to the normal terminal.*

## Common Mistakes
- **Getting stuck in the log:** If you see a `:` at the bottom of your screen and can't type new commands, it means the log is paginated. Just press `q` on your keyboard to exit!

## Quick Summary
- Shows the history of all commits.
- Useful for tracking down past changes.
- Use `git log --oneline` for a compact view.
- Press `q` to quit the log viewer.
