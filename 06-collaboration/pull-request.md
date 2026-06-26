# Pull Request (PR)

## What is it?
A Pull Request (PR) is a GitHub feature that allows you to propose changes to a repository. You are literally requesting the owner to "pull" your code into their project.

## Why do we use it?
In professional environments and open-source, you never push code directly to the `main` branch. You create a branch, push it to GitHub, and open a Pull Request. This allows other developers to review your code, discuss it, and approve it before it gets merged.

## Basic Syntax
Pull Requests are created on the GitHub website, not the terminal.

## Example
1. Create a new branch and write some code:
   ```bash
   git switch -c add-login
   git add .
   git commit -m "feat: add login page"
   ```
2. Push your branch to GitHub:
   ```bash
   git push -u origin add-login
   ```
3. Go to your repository on GitHub. You will see a green button saying **Compare & pull request**.
4. Click it, write a good description, and click **Create pull request**.

## Common Mistakes
- **Leaving the description blank:** Always explain *why* you made the change and *how* you tested it so reviewers understand your code.
- **Making the PR too big:** Try to keep Pull Requests small and focused on a single feature or bug fix. Massive PRs take forever to review.

## Quick Summary
- A request for someone to review and merge your code.
- Standard practice for all team collaboration.
- Created on the GitHub website after pushing a branch.
