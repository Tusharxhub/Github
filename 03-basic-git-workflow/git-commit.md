# Git Commit

## What is it?
`git commit` takes all the files in the Staging Area and saves them permanently in the local repository's history as a "snapshot."

## Why do we use it?
Committing is how you save your work in Git. It is like hitting "Save" in a video game. Each commit gets a unique ID and a message explaining what changed, allowing you to go back to this exact point in the future.

## Basic Syntax

```bash
git commit -m "Your descriptive message here"
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git commit` | Creates a new commit (snapshot) |
| `-m` | Stands for "message" |
| `"..."` | The message explaining the changes |

## Example
```bash
git commit -m "Add navigation bar to the homepage"
```

## Common Mistakes
- **Vague commit messages:** Messages like "fixed stuff" or "updated" are useless when trying to find a bug later. Write clear messages like "Fix login button color."
- **Forgetting to stage first:** If you type `git commit` without running `git add` first, Git will say "nothing to commit".

## Quick Summary
- Saves staged changes permanently to local history.
- Always include a clear, descriptive message.
- A commit is a safe save point for your code.
