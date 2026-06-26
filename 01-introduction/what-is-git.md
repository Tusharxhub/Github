# What is Git?

## What is it?
Git is a free, open-source Distributed Version Control System (DVCS). It was created in 2005 by Linus Torvalds, the creator of the Linux operating system, to help manage the massive collaborative effort of building the Linux kernel. 

Git allows you to track every single modification made to a file, revert back to older versions, and work seamlessly with thousands of other developers on the exact same project without accidentally overwriting each other's work.

## Why do we use it?
Before Git, teams used systems where a single central server held all the code (like Subversion or SVN). If that server went down, nobody could work. If you wanted to work on an airplane without Wi-Fi, you couldn't save your versions.

Git solved this by being **Distributed**. When you use Git, you don't just download a snapshot of the code; you download the *entire history of the project* onto your local hard drive. 

**Key Benefits of Git:**
1. **Speed:** Since everything is on your local hard drive, operations like checking history or saving changes happen instantly. You don't need an internet connection.
2. **Data Integrity:** Git uses a cryptographic hash function called SHA-1 to secure your code. It is impossible to change a file, date, or commit message without Git knowing about it.
3. **Non-linear Development:** Git allows you to branch off from the main code, experiment, and then merge it back effortlessly. Branching in Git takes milliseconds.
4. **Offline Working:** You can do 99% of your work offline, only needing the internet when you are ready to share your code (using `git push`).

## The Concept of Snapshots, Not Differences
Other systems store information as a list of file-based changes (deltas). They save the original file and then a list of lines that changed.
Git doesn't do this. Git thinks of its data more like a stream of snapshots. Every time you commit, Git takes a picture of what all your files look like at that moment and stores a reference to that snapshot. If files haven't changed, Git doesn't store the file again, just a link to the previous identical file.

## Quick Summary
- Git is the software installed on your computer that tracks local changes.
- It is incredibly fast, secure, and allows you to work completely offline.
- Created by Linus Torvalds for Linux development.
- Tracks files through "snapshots" rather than line-by-line differences.
