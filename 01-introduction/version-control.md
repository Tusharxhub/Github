# Version Control

## What is it?
Version control (also known as source control) is a system that records changes to a file or set of files over time so that you can recall specific versions later. It acts as a comprehensive "undo" button for your entire project, keeping track of every modification, who made it, and why.

## Why do we use it?
Imagine you are writing a long document or building a complex app. Without version control, you might end up saving multiple copies of your project to prevent losing work, resulting in a messy folder like this:
- `project_v1`
- `project_v2_final`
- `project_v3_really_final`
- `project_v4_FINAL_final`

Version control completely eliminates this mess. It allows you to:
1. **Revert files:** If you break something, you can instantly go back to a previous state where the code worked perfectly.
2. **Compare changes:** You can see exactly what lines of code were added or deleted between yesterday and today.
3. **Collaborate:** Multiple people can work on the exact same project at the exact same time without overwriting each other's work.
4. **Identify problems:** If a bug appears, you can trace it back to see exactly which change introduced the bug and who made it.

## The Two Types of Version Control
1. **Centralized Version Control Systems (CVCS):** Systems like Subversion (SVN) where a single central server contains all the versioned files. If the server goes down, nobody can save their version history.
2. **Distributed Version Control Systems (DVCS):** Systems like **Git**. In Git, every developer fully mirrors the entire repository on their own computer. If a server goes down, any client repository can be copied back up to the server to restore it. You can work entirely offline!

## Real-World Analogy
Think of version control like the "History" tab in Google Docs, but for software. In Google Docs, you don't save multiple files; you just type, and Google tracks every keystroke. If you delete a paragraph by mistake, you can open the history and restore it. Version control does exactly this, but it requires you to explicitly tell it when to take a "snapshot" of the history (which we call a "commit").

## Quick Summary
- Tracks changes to files over time.
- Acts like a "Time Machine" for your code.
- Allows multiple people to work on the same project safely.
- Git is a distributed system, meaning it works entirely offline.
