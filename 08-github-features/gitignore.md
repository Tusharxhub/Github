# Gitignore

## What is it?
`.gitignore` is a special hidden text file you create in your repository. You list files and folders inside it that you want Git to completely ignore (not track, not stage, not commit).

## Why do we use it?
Some files should NEVER be uploaded to GitHub. This includes:
- **Secrets:** API keys, database passwords (like `.env` files).
- **Dependencies:** Massive folders of downloaded libraries (like `node_modules`).
- **System files:** Junk files created by your operating system (like `.DS_Store` on Mac).

## Basic Syntax

1. Create a file exactly named `.gitignore`.
2. Add the names of files or folders inside.

```text
# Ignore the node_modules folder
node_modules/

# Ignore all .env files
.env

# Ignore a specific file
secret-notes.txt
```

## Example
For a standard Node.js or Next.js project, your `.gitignore` might look like this:
```text
node_modules/
.env
.env.local
.next/
dist/
.DS_Store
```

## Common Mistakes
- **Ignoring files after committing them:** If you already committed `.env` and *then* add it to `.gitignore`, Git will STILL track it. You must remove it from Git's memory first using `git rm --cached .env`.
- **Typing the name wrong:** It must be exactly `.gitignore` with a dot at the beginning.

## Quick Summary
- Tells Git which files to ignore.
- Prevents uploading passwords, API keys, and huge dependency folders.
- Create it as soon as you initialize your project.
