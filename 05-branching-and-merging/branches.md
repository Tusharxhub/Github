# Branches

## What is it?
A branch is a lightweight, movable pointer to a specific commit. Creating a branch allows you to split off from the main line of development and work on a feature independently without affecting the main code.

## Why do we use it?
Imagine you are building a website and want to test a crazy new dark mode design. If you edit the main files and it breaks, your website is ruined. Instead, you create a "dark-mode" branch. You can freely break things on this branch, and the main branch remains perfectly safe.

## Basic Syntax

```bash
git branch <branch_name>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git branch` | Command to list, create, or delete branches |
| `<branch_name>`| The name of the new branch |

## Example
To create a new branch:
```bash
git branch feature-login
```

To see a list of all branches (the one with the `*` is the one you are currently on):
```bash
git branch
```

## Common Mistakes
- **Branch names with spaces:** You cannot use spaces in branch names. Use hyphens (`feature-login`) or underscores (`feature_login`).
- **Forgetting to switch:** `git branch my-feature` *creates* the branch, but it does NOT switch you to it. You are still on the main branch until you switch.

## Quick Summary
- Branches allow safe, parallel development.
- The default branch is usually called `main`.
- Use `git branch` to list your branches.
