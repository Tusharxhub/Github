# File Lifecycle

## What is it?
In Git, files go through a specific lifecycle. They are not simply "saved" or "unsaved". They move through different areas: Untracked, Working Directory, Staging Area, and Repository.

## Why do we use it?
Understanding this lifecycle is the secret to mastering Git. It explains why we have to run `add` before `commit`.

## The Lifecycle Stages
1. **Untracked:** A brand new file. Git doesn't know it exists yet.
2. **Tracked (Modified):** A file Git knows about, which has been changed but not added to the Staging Area.
3. **Staged:** A file that is ready to be committed.
4. **Committed:** The file is safely stored in the local Git database.

## Basic Workflow

```mermaid
flowchart LR
    A[Untracked / Modified] -->|git add| B[Staged]
    B -->|git commit| C[Committed]
    C -->|Edit File| A
```

## Quick Summary
- **Working Directory:** Where you type your code.
- **Staging Area:** Where you prepare files for saving.
- **Repository:** Where files are permanently saved as commits.
