# Fetch

## What is it?
`git fetch` downloads commits, files, and branches from a remote repository into your local repository, but it **does not** modify your working files.

## Why do we use it?
Sometimes you want to see what changes have been made on GitHub *without* actually changing your own files just yet. `git pull` is actually a combination of two commands: `git fetch` (download the data) + `git merge` (combine it with your files). Fetch lets you look before you leap.

## Basic Syntax

```bash
git fetch
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git fetch` | Downloads updates from the remote repository without merging them |

## Example
```bash
git fetch origin
```
After fetching, you can run `git status` and Git might tell you: "Your branch is behind 'origin/main' by 3 commits." This tells you that there is new code on GitHub waiting to be merged.

## Common Mistakes
- **Expecting files to change:** Beginners often run `git fetch` and then get confused why their code didn't update. Remember, fetch only downloads the *history* to the hidden `.git` folder. It does not touch your visible files.

## Quick Summary
- Downloads updates from GitHub but doesn't change your active files.
- Safe way to check if there are updates on the server.
- `git pull` is basically `git fetch` followed by `git merge`.
