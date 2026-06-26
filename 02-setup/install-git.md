# Install Git

## What is it?
Installing Git means downloading the Git software onto your computer so that your terminal or command prompt can understand Git commands.

## Why do we use it?
You cannot use Git commands like `git init` or `git commit` until the Git software is installed on your operating system.

## Basic Syntax

### Windows
1. Download the installer from [git-scm.com/download/win](https://git-scm.com/download/win).
2. Run the `.exe` file and follow the installation wizard (default settings are fine).

### macOS
```bash
brew install git
```

### Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install git
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `brew` / `apt` | Package managers to download software |
| `install git` | Tells the package manager to download Git |

## Example
After installing, always verify the installation by checking the version:
```bash
git --version
```
Expected output: `git version 2.x.x`

## Common Mistakes
- **Typing Git commands without installing:** Your terminal will say "command not found".
- **Installing an outdated version:** Always try to get the latest stable version for your OS.

## Quick Summary
- Windows: Download from the official website.
- Mac/Linux: Use the terminal package manager.
- Verify installation with `git --version`.
