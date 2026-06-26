# Configure Git

## What is it?
Configuring Git means setting up your global user information (Name and Email) so Git knows who is making the commits.

## Why do we use it?
Every commit must be attached to an author. If you don't configure this, Git won't let you commit. Furthermore, the email you configure here should match your GitHub account email so that GitHub correctly links your commits to your profile.

## Basic Syntax

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git config` | Tool to set or get configuration variables |
| `--global` | Applies this setting to all projects on your computer |
| `user.name` | The variable for your name |
| `user.email` | The variable for your email |

## Example
If your name is John Doe:
```bash
git config --global user.name "John Doe"
git config --global user.email "johndoe@email.com"
```

To verify your configuration:
```bash
git config --list
```

## Common Mistakes
- **Using a fake email:** Use the exact email address you registered your GitHub account with to ensure your contributions show up on your profile graph.
- **Forgetting quotes around name:** Always use quotes like `"John Doe"` if your name has spaces.

## Quick Summary
- Set your name and email immediately after installing Git.
- Use `--global` to set it once for your entire computer.
- Verify with `git config --list`.
