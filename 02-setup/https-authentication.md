# HTTPS Authentication

## What is it?
HTTPS is a method to authenticate your local Git with your GitHub account over the internet using a Personal Access Token (PAT) instead of a password.

## Why do we use it?
GitHub no longer allows you to use your account password when pushing code from the terminal for security reasons. You must use a Personal Access Token (PAT) if you connect via HTTPS.

## Basic Syntax
When you clone a repository via HTTPS, the URL looks like this:
```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

## Example: Generating a PAT
1. Go to **GitHub Settings** -> **Developer Settings** -> **Personal access tokens** -> **Tokens (classic)**.
2. Click **Generate new token**.
3. Give it a note (e.g., "Laptop Git").
4. Check the `repo` scope (this gives it permission to push/pull code).
5. Click generate and **copy the token**.

When you push code and the terminal asks for a password, paste this token instead.

## Common Mistakes
- **Closing the page before copying:** GitHub only shows the token once. If you lose it, you have to generate a new one.
- **Typing password instead of token:** Using your normal GitHub login password in the terminal will fail with an "Authentication failed" error.

## Quick Summary
- Passwords don't work in the terminal anymore.
- Generate a Personal Access Token (PAT) in GitHub settings.
- Check the `repo` permission when creating the PAT.
- Use the PAT whenever Git asks for a password.
