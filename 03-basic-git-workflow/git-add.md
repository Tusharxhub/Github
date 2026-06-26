# Git Add

## What is it?
`git add` is the command used to move files from your Working Directory into the Staging Area. It tells Git, "I want to include these specific files in my next save (commit)."

## Why do we use it?
Git forces you into a two-step process to save files: first you `add`, then you `commit`. 
Why not just save everything at once? 
Imagine you spent the whole day working, and you fixed a bug in `app.js` and also added a new feature in `index.html`. These are two completely unrelated changes. In Git, it is best practice to keep commits focused on a single topic. 

The Staging Area allows you to selectively choose which files to package together. You can `git add app.js` and commit it as "fix bug", and then separately `git add index.html` and commit it as "add new feature".

## Basic Syntax

**To add a single file:**
```bash
git add <file_name>
```

**To add everything at once (most common):**
```bash
git add .
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `git add` | Stages files for commit |
| `index.html` | Only stages the specific file named index.html |
| `.` | The period means "everything in the current directory and all subdirectories" |
| `-A` | Adds all changes, including file deletions, across the entire repository |

## Example Workflow

1. You modify three files: `header.css`, `footer.css`, and `database.js`.
2. You only want to commit the CSS changes first.
3. You run:
   ```bash
   git add header.css footer.css
   ```
4. You check `git status`. The CSS files will be green (staged), and the JS file will be red (unstaged).
5. You commit the CSS changes.
   ```bash
   git commit -m "style: update header and footer layouts"
   ```

## Undoing a Git Add
What happens if you accidentally run `git add .` and stage a massive file that you didn't want to commit?
You can easily "unstage" a file using:
```bash
git restore --staged <file_name>
```
*(Older versions of Git used `git reset HEAD <file_name>` for this).*

## Common Mistakes
- **Running `git add .` without checking status:** This is a dangerous habit. If you always just add everything blindly, you will eventually accidentally commit API keys, passwords, or massive `node_modules` folders. Always run `git status` before `git add .`
- **Assuming `git add` saves the file:** `git add` DOES NOT save your file to history. If you `add` a file and then your computer crashes before you `commit`, you lose that history. The file is only permanently saved in the Git database once you run `git commit`.

## Quick Summary
- `git add` prepares your files to be saved.
- Moves files from Working Directory to the Staging Area.
- Use `git add .` to stage all modified and new files.
- Run `git status` before you add to prevent mistakes!
