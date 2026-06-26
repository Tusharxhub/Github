# Repository

## What is it?
A repository (or "repo") is simply a folder on your computer that is being tracked by Git. It contains all your project files and the hidden `.git` folder that holds the version history.

## Why do we use it?
Without a repository, Git cannot track your files. A repository is the fundamental container for any Git-based project. You can have local repositories (on your computer) and remote repositories (on GitHub).

## Basic Syntax
There is no specific command called "repository". You either initialize one or clone one.

## Example
If you have a folder called `my-website`, and you want Git to track it, you turn that folder into a repository by running:
```bash
cd my-website
git init
```

## Common Mistakes
- **Creating a repo inside a repo:** Never run `git init` in a folder that is already inside another Git repository. It causes severe tracking confusion.
- **Deleting the `.git` folder:** This completely erases all your version history! 

## Quick Summary
- A repo is just a folder tracked by Git.
- It contains a hidden `.git` folder storing history.
- Every project needs its own repository.
