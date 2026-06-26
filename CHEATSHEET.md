# Git Cheat Sheet

Here is a quick reference for the most commonly used Git commands.

| Command | Description |
| ------- | ----------- |
| `git init` | Initializes a new local Git repository |
| `git clone <url>` | Downloads a project and its entire version history |
| `git status` | Lists all new or modified files to be committed |
| `git add <file>` | Stages a specific file for the next commit |
| `git add .` | Stages all modified and new files |
| `git commit -m "[message]"` | Records file snapshots permanently in version history |
| `git branch` | Lists all local branches in the current repository |
| `git branch <branch-name>` | Creates a new branch |
| `git checkout <branch-name>` | Switches to the specified branch |
| `git switch <branch-name>` | Switches to the specified branch (newer command) |
| `git merge <branch-name>` | Combines the specified branch’s history into the current branch |
| `git remote add origin <url>` | Connects the local repository to a remote server |
| `git push -u origin <branch>` | Uploads local branch commits to the remote repository |
| `git pull` | Fetches and merges changes on the remote server to your working directory |
| `git log` | Shows commit history for the currently active branch |
| `git log --oneline` | Shows a condensed commit history |
| `git reset <file>` | Unstages the file, but preserve its contents |
| `git restore <file>` | Discards changes in the working directory |
| `git revert <commit>` | Creates a new commit that undoes changes from a previous commit |
| `git stash` | Temporarily stores all modified tracked files |
