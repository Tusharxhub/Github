# Reset

## What is it?
`git reset` is a powerful command that moves your current branch backward in history to an older commit, essentially erasing recent commits.

## Why do we use it?
If you made a few commits that are completely wrong and you want to pretend they never happened, you can "reset" your timeline back to a safe point.

## Basic Syntax

```bash
git reset --hard <commit_id>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git reset` | Moves the branch pointer backward |
| `--soft` | Keeps your files changed, just uncommits them |
| `--hard` | **DANGEROUS**: Deletes the commits AND throws away the file changes |
| `<commit_id>` | The ID (hash) of the commit you want to go back to |

## Example
If you want to completely erase the last commit and throw away the code:
```bash
git reset --hard HEAD~1
```
*(HEAD~1 means "one commit before the current one")*

## Common Mistakes
- **Using `--hard` accidentally:** This will permanently delete your uncommitted code. If you want to undo a commit but KEEP the code in your editor, use `git reset --soft HEAD~1`.
- **Resetting pushed commits:** Never use `git reset` on commits you have already pushed to GitHub if you are working with a team. It will break their repository.

## Quick Summary
- Acts as a time machine to erase recent commits.
- `--soft` keeps your file changes.
- `--hard` destroys the changes entirely.
