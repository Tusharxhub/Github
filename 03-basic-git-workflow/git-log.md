# Git Log

## What is it?
`git log` is the command used to view the history of your repository. It acts as a time machine interface, printing out a list of every commit ever made, who made it, when it was made, and the message attached to it.

## Why do we use it?
If you are working on a team project, you need to know what changes your teammates have made recently. If a bug is suddenly introduced into the app, you can use `git log` to trace back through the history and see exactly which commit broke the code. It is essential for auditing, reviewing, and navigating past versions.

## Basic Syntax

```bash
git log
```

## Reading the Output
When you type `git log`, you will see output that looks like this:

```text
commit 8a3f9e2b1c4d5e6f7a8b9c0d1e2f3a4b5c6d7e8f (HEAD -> main, origin/main)
Author: Jane Doe <jane@example.com>
Date:   Mon Oct 24 14:32:01 2026 -0400

    feat: add user authentication to the login page

commit 1f2e3d4c5b6a7f8e9d0c1b2a3f4e5d6c7b8a9f0e
Author: John Smith <john@example.com>
Date:   Sun Oct 23 09:15:22 2026 -0400

    docs: update README with installation instructions
```

**Key Elements:**
- **Commit Hash:** The long 40-character string (e.g., `8a3f9...`). This is the unique ID for that specific snapshot.
- **HEAD:** Shows where you currently are in the timeline.
- **Author & Date:** Exactly who made the change and when.
- **Message:** The description of the changes.

## Advanced Log Formats (Highly Recommended)
The default `git log` output is very long and hard to read if you have hundreds of commits. You can use flags to format it beautifully.

**1. One-Line Summary:**
Compresses every commit into a single line showing the short hash and the message.
```bash
git log --oneline
```

**2. See the Code Changes:**
Shows exactly what lines of code were added (+) or deleted (-) in each commit.
```bash
git log -p
```

**3. Graphical View:**
Draws an ASCII tree in your terminal showing how branches diverge and merge.
```bash
git log --graph --oneline --all
```

## Navigating the Log
If you have a long history, `git log` will open in a "pager" (a scrollable view).
- Press **`Spacebar`** or **`Page Down`** to scroll down.
- Press **`w`** or **`Page Up`** to scroll up.
- Press **`q`** to quit and return to your normal terminal.

## Common Mistakes
- **Getting stuck in the log:** Beginners often run `git log`, see the output, and then don't know how to type new commands because the terminal seems "stuck". Remember to press `q` to quit the log view!
- **Not using `--oneline`:** Reading the full default log for a project with 10,000 commits is impossible. Get used to using `git log --oneline`.

## Quick Summary
- `git log` shows the commit history.
- It displays the hash, author, date, and message.
- Use `git log --oneline` for a cleaner, compact view.
- Press `q` to exit the log view.
