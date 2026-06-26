# Revert

## What is it?
`git revert` is a safe way to undo a previous commit. Instead of deleting the old commit (like `reset` does), it creates a *brand new commit* that does the exact opposite of the original one.

## Why do we use it?
If you push code to GitHub and realize it broke the app, you need to undo it. You shouldn't use `git reset` because deleting history on GitHub causes chaos for your teammates. Instead, you use `git revert`, which safely adds an "undo" commit to the history.

## Basic Syntax

```bash
git revert <commit_id>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git revert` | Creates a new commit that inverses an old one |
| `<commit_id>`| The hash of the commit you want to undo |

## Example
1. Find the bad commit using `git log`:
   ```text
   a1b2c3d Bad commit that broke the website
   ```
2. Revert it:
   ```bash
   git revert a1b2c3d
   ```
Git will open your text editor to confirm the new commit message (usually "Revert: Bad commit that..."). Save and close.

## Common Mistakes
- **Confusing it with reset:** Remember: `reset` *erases* history (dangerous on GitHub). `revert` *adds* to history (safe on GitHub).

## Quick Summary
- The safest way to undo a commit.
- Creates a new commit that does the exact opposite of the target commit.
- Always use this method when undoing code that is already on GitHub.
