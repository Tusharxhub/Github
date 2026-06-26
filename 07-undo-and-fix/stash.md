# Stash

## What is it?
`git stash` takes your uncommitted changes (both staged and unstaged), saves them to a temporary clipboard, and cleans your working directory.

## Why do we use it?
Imagine you are halfway through coding a feature, and your boss tells you to urgently fix a bug on the `main` branch. You can't switch to `main` with half-finished code, but you aren't ready to commit yet. You `stash` your changes, fix the bug, and then pop your stashed changes back into your files later.

## Basic Syntax

```bash
git stash
```

To bring the changes back:
```bash
git stash pop
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git stash` | Saves changes to a clipboard and cleans the directory |
| `pop` | Removes the most recent stash from the clipboard and applies it to your files |

## Example
```bash
# Save your half-finished work
git stash

# Switch to main and fix the bug
git switch main
# ... fix bug, commit, push ...

# Switch back to your feature and restore your work
git switch feature-branch
git stash pop
```

## Common Mistakes
- **Forgetting what you stashed:** If you stash things and forget about them, your stash list will get huge. You can view your stashes using `git stash list`.
- **Stashing untracked files:** By default, `git stash` does not save brand new files. To include them, use `git stash -u`.

## Quick Summary
- Like a temporary clipboard for your uncommitted code.
- Cleans your working directory so you can safely switch branches.
- Use `git stash pop` to get your code back.
