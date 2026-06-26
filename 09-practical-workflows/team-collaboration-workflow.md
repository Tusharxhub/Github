# Team Collaboration Workflow

## What is it?
This is the professional workflow used in companies where multiple developers are working on the same repository simultaneously.

## Why do we use it?
If everyone pushes code directly to the `main` branch, the codebase will break constantly. This workflow uses branches and Pull Requests to ensure code is reviewed before it becomes official.

## The Workflow

**Step 1: Get latest main code**
```bash
git switch main
git pull origin main
```

**Step 2: Create a feature branch**
Never work directly on main!
```bash
git switch -c feature/login-page
```

**Step 3: Code and commit**
```bash
git add .
git commit -m "feat: build login form UI"
```

**Step 4: Push the branch to GitHub**
```bash
git push -u origin feature/login-page
```

**Step 5: Open a Pull Request**
Go to GitHub and click "Compare & pull request". Ask a teammate to review your code.

**Step 6: Merge and cleanup**
Once approved, click "Merge PR" on GitHub. Then locally:
```bash
git switch main
git pull origin main
git branch -d feature/login-page  # Delete the local branch to keep things clean
```

## Quick Summary
- Never code on `main`.
- Always create a branch for your feature.
- Push the branch and open a Pull Request.
- Merge on GitHub, pull locally, delete the old branch.
