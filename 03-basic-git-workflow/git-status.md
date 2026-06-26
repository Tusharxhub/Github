# Git Status

## What is it?
`git status` is a command that tells you the current state of your repository. It shows which files have been changed, which are ready to be committed (staged), and which are untracked.

## Why do we use it?
It is the most frequently used Git command. Before doing almost anything in Git (adding, committing, pushing), you should check `git status` to make sure you know exactly what is happening in your project.

## Basic Syntax

```bash
git status
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git` | Runs the Git program |
| `status` | Shows the status of files in the working directory and staging area |

## Example
If you create a new file called `index.html` and run `git status`, you will see:
```text
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	index.html
```

## Common Mistakes
- **Not using it enough:** Beginners often blindly type `git add .` and `git commit` without checking `git status` first, accidentally committing broken files or passwords.

## Quick Summary
- Shows what is going on in your repo.
- Red text usually means files are modified/untracked.
- Green text means files are staged and ready to commit.
- Use it constantly!
