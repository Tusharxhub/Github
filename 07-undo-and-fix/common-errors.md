# Common Git Errors

Even experienced developers make mistakes and encounter Git errors. Don't panic! Git provides descriptive error messages if you read them carefully. Here are the most common errors and exactly how to fix them.

---

## 1. Non-Fast-Forward (Push Rejected)
**The Error Message:**
```text
error: failed to push some refs to 'https://github.com/...'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally.
```

**Why it happens:**
Someone else pushed new code to GitHub, or you made changes directly on the GitHub website (like editing the README). You are trying to push your local code, but GitHub rejects it because it would overwrite the new remote code.

**How to fix it:**
You need to pull the remote changes down to your computer and merge them first.
1. Run `git pull origin main` (or whatever branch you are on).
2. Fix any merge conflicts if they appear.
3. Once the merge is complete, run `git push` again.

---

## 2. Detached HEAD State
**The Error Message:**
```text
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them...
```

**Why it happens:**
Instead of checking out a branch name (like `git switch main`), you checked out a specific commit hash (like `git checkout a1b2c3d`). Git is warning you that you are no longer attached to any branch. If you make commits here, they will become "orphaned" and lost when you switch away.

**How to fix it:**
If you were just looking around at old code and want to go back to normal:
`git switch main`

If you made changes in detached HEAD and want to save them to a new branch:
`git switch -c new-recovery-branch`

---

## 3. Merge Conflicts
**The Error Message:**
```text
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

**Why it happens:**
You tried to `merge` or `pull`, but Git found that two different commits edited the exact same line of code in `index.html`. Git cannot guess which version is correct, so it halts the merge.

**How to fix it:**
1. Open the conflicting file (`index.html`) in your code editor (like VS Code).
2. You will see markers like `<<<<<<< HEAD`, `=======`, and `>>>>>>>`.
3. Manually edit the code to keep what you want, and delete the Git markers.
4. Run `git add index.html` to mark it as resolved.
5. Run `git commit` to finish the merge.

---

## 4. Wrong Author Name or Email
**The Error Message:**
You look at `git log` and realize your commits are attributed to the wrong name, or your GitHub profile isn't linking the commits to your account.

**Why it happens:**
You either forgot to configure your user details, or you set them incorrectly.

**How to fix it:**
Update your global configuration:
```bash
git config --global user.name "Your Real Name"
git config --global user.email "your.email@example.com"
```
*(Note: This only applies to future commits. Changing past commits is complicated and usually involves `git rebase`).*

---

## 5. Accidentally Committing a Large or Secret File
**The Problem:**
You ran `git add .` and committed an API key, a password, or a massive 5GB database file, but you *haven't* pushed it to GitHub yet.

**How to fix it:**
Because you haven't pushed yet, you can easily undo the last commit and unstage the files, keeping your edits intact in the working directory:
```bash
git reset --soft HEAD~1
```
Then, add the sensitive file to your `.gitignore`, and commit the safe files again.

*(If you already pushed the secret to GitHub, you must assume it is compromised. Revoke the API key or change the password immediately. Removing it from Git history requires tools like BFG Repo-Cleaner or `git filter-branch`).*
