# Git Status

## What is it?
`git status` is the command used to check the current state of your repository. It tells you exactly what Git sees at this very moment: what branch you are on, which files are modified, which files are staged for the next commit, and which files are completely untracked.

## Why do we use it?
`git status` is arguably the most important command in Git. It is your eyes and ears. Whenever you are confused, whenever a command fails, or whenever you come back to a project after a coffee break, you should run `git status`. It acts as a safety check to ensure you know exactly what you are about to save.

## Basic Syntax

```bash
git status
```

## Reading the Output

When you run `git status`, Git will output information categorized into three main sections:

### 1. Untracked files (Red Text)
These are brand new files that you just created. Git says, "I see these files exist, but I am not tracking their history yet."
```text
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
```

### 2. Changes not staged for commit (Red Text)
These are files that Git is already tracking, and you have made changes to them, but you haven't moved them to the Staging Area yet.
```text
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   styles.css
```

### 3. Changes to be committed (Green Text)
These are files that have been successfully added to the Staging Area using `git add`. They are fully prepared and waiting for you to run `git commit`.
```text
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
        modified:   styles.css
```

## Advanced Usage
If you just want a quick overview without all the explanatory text, you can use the "short" flag:
```bash
git status -s
```
This prints a compact list:
` M styles.css` (Modified)
`?? index.html` (Untracked)
`A  app.js` (Added to staging)

## Common Mistakes
- **Not reading the hints:** Beginners often ignore the text output of `git status`. Read it carefully! Git actively tells you exactly what commands to run next. For example, it will tell you to use `git restore` to undo a mistake, or `git add` to stage a file.
- **Committing blindly:** Never run `git commit` without running `git status` first to verify exactly what files you are saving. You might accidentally commit a massive video file or a `.env` password file.

## Quick Summary
- `git status` shows the current state of your files.
- It is a safe, read-only command. You can run it 100 times a day without breaking anything.
- Shows Untracked (new), Modified (changed), and Staged (ready) files.
- Always run this before running `git add` or `git commit`.
