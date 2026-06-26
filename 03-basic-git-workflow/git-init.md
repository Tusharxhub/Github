# Git Init

## What is it?
`git init` is the command used to create a brand new, empty Git repository. It transforms an ordinary, plain folder on your computer into a Git-tracked folder, allowing you to start recording changes.

## Why do we use it?
Before you run `git init`, Git has no idea your folder exists. It doesn't track any of the files inside it. When you run `git init`, Git creates a hidden directory called `.git` inside your folder. This `.git` folder is the brain of your repository; it contains all the databases, configuration files, and history that Git needs to function.

You only ever need to run `git init` **once** per project.

## Basic Syntax

```bash
git init
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git` | Calls the Git program |
| `init` | Short for "initialize" (start up / create) |

## Example Workflow

Let's say you want to start a new web project on your Desktop.

1. Open your terminal and create a new folder:
   ```bash
   mkdir my-website
   ```
2. Navigate into that folder:
   ```bash
   cd my-website
   ```
3. Initialize the Git repository:
   ```bash
   git init
   ```
   *Git will output: `Initialized empty Git repository in /path/to/my-website/.git/`*

## How does it work? (The `.git` folder)
When you run `git init`, it creates a hidden folder named `.git`. If you are on Mac/Linux, you can see it by running `ls -a`. If you are on Windows, you have to enable "Show Hidden Files" in Explorer.

**WARNING:** NEVER delete or manually edit the contents of the `.git` folder unless you know exactly what you are doing. If you delete the `.git` folder, your entire project's version history is permanently destroyed, and it goes back to being just a normal folder.

## Cloning vs Init
- Use `git init` when you are starting a brand new project from scratch on your own computer.
- Use `git clone` when the project already exists on GitHub and you just want to download it. (Running `git clone` automatically runs `git init` in the background for you).

## Common Mistakes
- **Running `git init` in your home directory:** Beginners sometimes open their terminal (which opens in `~` or `C:\Users\Name`) and blindly run `git init`. This turns their ENTIRE computer's user directory into a Git repository, which is a massive mess. Always `cd` into your specific project folder first.
- **Running `git init` inside another Git repository:** This creates a Git repo inside a Git repo (a submodule), which causes endless headaches. Only initialize the root folder of your project.

## Quick Summary
- `git init` creates a new local repository.
- It creates a hidden `.git` folder containing all version history.
- Run it exactly once per new project.
- Always make sure you are inside your project folder before running it.
