# Rebase

## What is it?
`git rebase` is an alternative to `git merge`. It takes the commits from your current branch and "replays" them at the very tip of another branch (like `main`), creating a perfectly straight, linear history.

## Why do we use it?
While `git merge` creates a "merge commit" that ties two histories together, `git rebase` rewrites history to make it look like you wrote all your code *after* the latest updates on `main`. This keeps the project history very clean and easy to read.

## Basic Syntax

```bash
git rebase <base_branch>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git rebase` | Moves the base of the current branch |
| `<base_branch>`| The branch you want to place your commits on top of (usually `main`) |

## Example
If you are on `feature-branch` and want to update it with the latest `main` code:
```bash
git rebase main
```

## Common Mistakes
- **Rebasing public branches:** NEVER rebase a branch that you have already pushed to GitHub and that other people are working on. Rebasing rewrites history, which will cause massive conflicts for your teammates. Only rebase your own local, private branches.
- **Getting stuck in a rebase loop:** If you get conflicts during a rebase, you must fix them, `git add`, and then run `git rebase --continue`.

## Quick Summary
- Creates a clean, straight-line history instead of messy merge bubbles.
- Only use it on your own local branches.
- Never rebase a branch that others are using.
