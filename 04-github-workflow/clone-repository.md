# Clone a Repository

## What is it?
`git clone` is a command used to download a complete copy of an existing GitHub repository to your local computer.

## Why do we use it?
If you want to work on a project that is already hosted on GitHub (like an open-source project, or a team project), you need to get it onto your laptop. Cloning downloads the files AND the entire Git version history.

## Basic Syntax

```bash
git clone <repository_url>
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git` | Runs the Git program |
| `clone` | Downloads the repo and history |
| `<repository_url>` | The HTTPS or SSH link from GitHub |

## Example
Go to a GitHub repository, click the green "Code" button, and copy the URL. Then run:
```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```
This will create a new folder named `REPOSITORY` on your computer.

## Common Mistakes
- **Forgetting to `cd` into the cloned folder:** After cloning, you must `cd` (change directory) into the newly created folder before you can run Git commands like `git status`.
- **Cloning inside another repo:** Never run `git clone` inside a folder that is already a Git repository!

## Quick Summary
- `git clone` downloads a project from GitHub.
- It includes all the files and the entire commit history.
- Always remember to `cd` into the downloaded folder afterward.
