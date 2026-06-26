# Git Commit

## What is it?
`git commit` is the command used to take all the files currently in your Staging Area and save them permanently in the local Git repository's database as a "snapshot." Every commit represents a specific point in time for your project.

## Why do we use it?
Committing is how you definitively save your work in Git. Think of it like hitting the "Save" button in a video game at a checkpoint. If you go face a boss and die (i.e., you write code that completely breaks your app), you can reload your last save (commit) and try again. 

Every commit gets a unique ID (a 40-character hash, like `a1b2c3d...`) and a message explaining what changed. This creates a readable timeline of your project's development.

## Basic Syntax

```bash
git commit -m "Your descriptive message here"
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git commit` | Creates a new commit (snapshot) of staged changes |
| `-m` | Stands for "message" |
| `"..."` | The message explaining the changes (must be in quotes) |

## Best Practices for Commit Messages
A commit message should explain **what** the commit changes and **why**.
- **Bad:** `git commit -m "fixed stuff"` (Tells us nothing)
- **Bad:** `git commit -m "update"` (Too vague)
- **Good:** `git commit -m "fix: resolve crash on login screen"`
- **Good:** `git commit -m "feat: add user profile picture upload"`

Many professional teams use "Conventional Commits" which start with a prefix:
- `feat:` for new features
- `fix:` for bug fixes
- `docs:` for documentation changes
- `style:` for CSS or formatting changes

## Advanced Usage: Skipping the Staging Area
If you have modified files that are *already being tracked* by Git, you can combine `git add` and `git commit` into a single command using the `-am` flag:
```bash
git commit -am "fix header alignment"
```
*(Note: This does NOT add brand new, untracked files. It only works on files Git already knows about.)*

## Common Mistakes
- **Vague commit messages:** If you use bad commit messages, looking through your `git log` six months from now will be incredibly confusing.
- **Forgetting to stage first:** If you type `git commit -m "msg"` without running `git add` first, Git will say "nothing to commit, working tree clean" (or it will show unstaged files). You must move files to the staging area first.
- **Committing too much at once:** Try to make small, focused commits. Don't build a new homepage, fix three bugs, and rewrite the database in a single commit. Break them up into logical pieces.

## Quick Summary
- Saves staged changes permanently to local history.
- Always include a clear, descriptive message explaining *why* the change was made.
- A commit is a safe save point for your code.
- Small, frequent commits are better than giant, infrequent ones.
