# Create a Repository

## What is it?
Creating a repository on GitHub gives you a blank project space in the cloud where you can push your local code.

## Why do we use it?
While Git works entirely on your local computer, GitHub is the cloud backup. By creating a remote repository, you create a destination to push your code to, allowing you to share it with others or access it from another computer.

## Basic Syntax
Creating a repository is done via the GitHub website interface.

## Example
1. Log in to [GitHub](https://github.com).
2. Click the `+` icon in the top right corner and select **New repository**.
3. Give it a name (e.g., `my-first-repo`).
4. Choose to make it Public or Private.
5. Do **not** check "Add a README file" if you already have local code you want to push. (If you check it, GitHub creates an initial commit that will conflict with your local commits).
6. Click **Create repository**.

## Common Mistakes
- **Adding a README on GitHub when pushing existing code:** If you have an existing local project, create an *empty* repository on GitHub. If you initialize the GitHub repo with a README, Git will block your first push because the remote and local histories do not match.

## Quick Summary
- Create a repo on GitHub to serve as the cloud backup for your code.
- Create an **empty** repo if you plan to push existing local code.
