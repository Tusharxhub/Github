# Switch and Checkout

## What is it?
`git switch` (and the older command `git checkout`) are used to change which branch you are currently working on.

## Why do we use it?
Creating a branch isn't enough; you must "switch" to it so that the files in your folder update to match that branch, and so that your new commits are saved to that branch.

## Basic Syntax

```bash
git switch <branch_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git switch` | Changes the active branch |
| `<branch_name>`| The name of the branch to move to |

## Example
To switch to an existing branch:
```bash
git switch feature-login
```

**Shortcut:** To create a new branch AND switch to it immediately:
```bash
git switch -c new-feature
```

*(Note: In older tutorials, you will see `git checkout -b new-feature`. This does the exact same thing, but `switch` is the newer, easier-to-understand command).*

## Common Mistakes
- **Switching with unsaved changes:** If you have modified files that conflict with the branch you are trying to switch to, Git will block the switch. You must commit or stash your changes first.

## Quick Summary
- Use `git switch` to jump between branches.
- Use `git switch -c <name>` to create and jump in one step.
- `git checkout` is the older version of this command.
