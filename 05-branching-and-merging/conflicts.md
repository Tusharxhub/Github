# Merge Conflicts

## What is it?
A merge conflict happens when Git cannot automatically merge two branches because they both modified the exact same part of the same file in different ways. 

## Why do we use it?
We don't "use" conflicts; they happen to us! When a conflict occurs, Git pauses the merge and asks you (the human) to decide which changes to keep. It's a safety mechanism to prevent code from being accidentally overwritten.

## Basic Syntax
When a conflict occurs, Git modifies the conflicting file to look like this:
```text
<<<<<<< HEAD
This is the code currently on the main branch.
=======
This is the code from the feature branch.
>>>>>>> feature-branch
```

## How to Fix It
1. **Open the conflicting file** in your text editor (like VS Code).
2. **Find the conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`).
3. **Delete the markers** and edit the code to look exactly how you want the final version to be.
4. **Save the file.**
5. **Stage and Commit:**
   ```bash
   git add <file>
   git commit -m "Resolve merge conflict in <file>"
   ```

## Common Mistakes
- **Panicking:** Conflicts are totally normal! Take a deep breath and read the file.
- **Leaving the markers in:** If you forget to delete the `<<<<<<<` symbols, your code will crash when you try to run it.
- **Using `git reset --hard`:** Don't delete your branch just because you got a conflict. Fix it manually.

## Quick Summary
- Occurs when two branches edit the exact same lines of code.
- Git stops the merge and asks you to choose.
- Open the file, remove the `<<< === >>>` markers, and save.
- Run `git add` and `git commit` to finish the merge.
