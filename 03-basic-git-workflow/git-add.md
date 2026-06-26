# Git Add

## What is it?
`git add` is the command used to move files from your Working Directory into the Staging Area.

## Why do we use it?
Git doesn't automatically save every file you change. The Staging Area lets you group specific changes together before saving them permanently (committing). This gives you complete control over what goes into the history.

## Basic Syntax

```bash
git add <file_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git` | Runs the Git program |
| `add` | Adds changes to the Staging Area |
| `<file_name>` | The name of the file to stage |

## Example
To add a single file:
```bash
git add index.html
```

To add all modified and new files in the current folder:
```bash
git add .
```

## Common Mistakes
- **Typing `git add .` without checking status:** It's easy to accidentally add passwords or temporary files to the staging area if you don't run `git status` first.
- **Forgetting the dot:** `git add .` (with a space before the dot) is a command. `git add.` will throw an error.

## Quick Summary
- Moves files to the Staging Area.
- Prepares files to be committed.
- Use `git add .` to add everything at once.
- Always run `git status` before `git add .`.
