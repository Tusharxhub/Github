# GitHub CLI (gh)

## What is it?
The GitHub CLI (Command Line Interface) is an official tool from GitHub that lets you use GitHub features directly from your terminal, without opening a web browser. The command starts with `gh`.

## Why do we use it?
It dramatically speeds up your workflow. Instead of clicking through the GitHub website to create a repository, open a pull request, or check issues, you can do it all instantly via the terminal.

## Basic Syntax

```bash
gh <command> <subcommand>
```

## Example
First, log in:
```bash
gh auth login
```

Create a new repository on GitHub straight from your terminal:
```bash
gh repo create my-project --public --source=. --remote=origin
```

Open a Pull Request from the terminal:
```bash
gh pr create --title "Add Login Feature" --body "This PR adds the new login page."
```

## Common Mistakes
- **Confusing `git` and `gh`:** `git` is the version control software. `gh` is a tool specifically for interacting with the GitHub website.
- **Forgetting to authenticate:** You must run `gh auth login` before you can use most `gh` commands.

## Quick Summary
- Brings GitHub website features to your terminal.
- Starts with the `gh` command.
- Great for power users who want to save time.
