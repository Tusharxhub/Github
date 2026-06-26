# Daily Developer Workflow

## What is it?
This is the standard, everyday loop of commands a developer runs when working on a project by themselves or in a small team.

## Why do we use it?
Memorizing this loop ensures you save your work frequently, write good history, and keep your code synced with GitHub.

## The Workflow

**Morning: Get the latest code**
Before you start coding, always check for updates.
```bash
git pull origin main
```

**During the day: Code, Add, Commit**
You write some code to build a feature, then save a snapshot.
```bash
git status
git add .
git commit -m "feat: add user profile page"
```
*(Repeat this Code -> Add -> Commit loop multiple times a day)*

**Evening: Push your work**
At the end of the day, or after finishing a major feature, push your commits to GitHub.
```bash
git push origin main
```

## Common Mistakes
- **Forgetting to `pull` first:** If someone else pushed code while you were sleeping, and you try to `push` at the end of the day without pulling first, Git will reject your push.

## Quick Summary
- Morning: `git pull`
- Day: `git add .` -> `git commit -m "..."`
- Evening: `git push`
