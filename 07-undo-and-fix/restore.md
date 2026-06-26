# Restore

## What is it?
`git restore` is a command used to discard uncommitted changes in your working directory, or to unstage files from the staging area.

## Why do we use it?
If you make a mess of a file and just want to throw away your recent changes and go back to the way the file was at the last commit, you use `git restore`. It is the Git equivalent of Ctrl+Z (Undo), but for the whole file.

## Basic Syntax

To throw away changes in the working directory:
```bash
git restore <file_name>
```

To remove a file from the staging area (unstage it):
```bash
git restore --staged <file_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git restore` | Restores files to a previous state |
| `--staged` | Specifically targets the staging area (undoes `git add`) |
| `<file_name>`| The file you want to target |

## Example
If you accidentally deleted a block of code in `index.html` and haven't committed yet:
```bash
git restore index.html
```
The file will instantly revert to exactly how it looked at the last commit.

## Common Mistakes
- **Restoring an untracked file:** `git restore` only works on files Git is tracking. If you create a brand new file and want to delete it, just delete it normally using your OS.
- **Accidental data loss:** Running `git restore .` throws away ALL unsaved changes in your folder permanently. Be careful!

## Quick Summary
- `git restore <file>` throws away unsaved edits.
- `git restore --staged <file>` undoes a `git add`.
- Replaces the older, confusing `git checkout <file>` command.
