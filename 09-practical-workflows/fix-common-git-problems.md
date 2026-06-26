# Fix Common Git Problems

## What is it?
A quick workflow guide for recovering from common mistakes without panicking.

## Problem 1: I committed to the wrong branch!
**Scenario:** You were supposed to be on `feature-branch` but you accidentally committed on `main`.
**Fix:**
```bash
# 1. Create a new branch pointing to this exact moment
git branch feature-branch

# 2. Move main back one commit (undoing it from main)
git reset --hard HEAD~1

# 3. Switch to your new branch where the commit is safely saved
git switch feature-branch
```

## Problem 2: I made a typo in my last commit message!
**Fix:**
```bash
git commit --amend -m "The correct and fixed message"
```
*(Warning: Only do this if you haven't pushed the commit to GitHub yet).*

## Problem 3: I added a file I didn't mean to add!
**Scenario:** You ran `git add .` but realized it included a massive `.mp4` video file.
**Fix:**
```bash
git restore --staged video.mp4
```

## Problem 4: I totally broke my code, take me back to my last commit!
**Fix:**
```bash
git restore .
```
*(Warning: This permanently deletes all unsaved changes).*

## Problem 5: I committed an API key and pushed it!
**Fix:** 
Do not just delete it and push again (it will remain in the history). 
1. Immediately go to the service (AWS, Stripe, etc.) and **revoke/delete the key**. Consider it permanently compromised.
2. Remove it from your code, add it to `.gitignore`, and commit.

## Quick Summary
- `commit --amend` fixes the last message.
- `restore --staged` undoes an accidental `add`.
- `restore .` throws away unsaved code.
- Always revoke leaked API keys immediately.
