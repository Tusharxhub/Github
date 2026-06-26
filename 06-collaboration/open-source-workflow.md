# Open Source Workflow

## What is it?
The standard process for contributing code to an open-source project (a project where anyone in the world can see and contribute to the code).

## Why do we use it?
Since you do not have direct write access to public projects, you must use the "Fork and Pull" workflow to submit your changes safely.

## The Workflow Steps

1. **Fork the Repository:** Go to the project on GitHub and click "Fork".
2. **Clone your Fork:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/project.git
   ```
3. **Add Upstream Remote:** Connect your local repo to the original project so you can get their updates.
   ```bash
   git remote add upstream https://github.com/ORIGINAL_OWNER/project.git
   ```
4. **Create a Branch:**
   ```bash
   git switch -c fix-typo
   ```
5. **Make Changes and Commit:**
   ```bash
   git add .
   git commit -m "docs: fix typo in readme"
   ```
6. **Push to YOUR Fork:**
   ```bash
   git push origin fix-typo
   ```
7. **Open a Pull Request:** Go to the original project's GitHub page and click "New Pull Request" to ask them to merge your branch.

## Common Mistakes
- **Working on the `main` branch:** Never do your work on the `main` branch of your fork. Always create a new branch. It makes it much easier to keep your fork updated with the original project.

## Quick Summary
- Fork -> Clone -> Branch -> Commit -> Push -> Pull Request.
- This is the universal standard for open-source contributions.
