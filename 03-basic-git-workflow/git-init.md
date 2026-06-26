# Git Init

## What is it?
`git init` is the command used to initialize (create) a brand new, empty Git repository in your current folder.

## Why do we use it?
When you start a new project on your computer, Git does not automatically track it. You must explicitly tell Git, "Hey, start tracking this folder," by initializing it.

## Basic Syntax

```bash
git init
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git` | Runs the Git program |
| `init` | Initializes a new repository |

## Example
```bash
mkdir my-new-project
cd my-new-project
git init
```
This creates a new folder, moves into it, and sets it up as a Git repository. You will see a message like: `Initialized empty Git repository in...`

## Common Mistakes
- **Running `git init` in the home directory:** This accidentally makes your entire computer a Git repository. Only run it inside specific project folders!
- **Running it multiple times:** Running `git init` in an already initialized repository is generally harmless, but it's unnecessary.

## Quick Summary
- Turns an ordinary folder into a Git repository.
- Creates a hidden `.git` folder.
- Only needs to be run once per new project.
