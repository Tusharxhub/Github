# Git vs GitHub

## The Biggest Misunderstanding
The most common mistake beginners make is thinking that Git and GitHub are the exact same thing. **They are completely different.** 

Git is a tool, a piece of software you install on your computer. GitHub is a service, a website you visit in your browser. You can use Git without ever touching GitHub, but you cannot use GitHub without Git.

## The Core Differences

| Feature | Git | GitHub |
| :--- | :--- | :--- |
| **What is it?** | A command-line software | A cloud-based website |
| **Where does it live?** | On your local computer | On the internet (Cloud) |
| **Who makes it?** | Open-source (Linus Torvalds) | Microsoft (Commercial company) |
| **Main Purpose?** | Tracking local file changes | Hosting and sharing code online |
| **Internet Required?** | No, works 100% offline | Yes, requires an internet connection |
| **Key Features** | Commits, Branches, Merging | Pull Requests, Issues, Actions, Stars |
| **Graphical Interface?** | No, mostly CLI (Command Line) | Yes, fully visual website |

## A Helpful Analogy

Think of writing a book.
- **Git** is like Microsoft Word running on your laptop. It lets you type, save, undo, and keep track of your local document history. You do all the actual work here.
- **GitHub** is like Google Drive or Dropbox. It's the place on the internet where you upload your Microsoft Word document so that your editor, publisher, and friends can read it, comment on it, and download their own copies.

## How they work together

1. You install **Git** on your laptop.
2. You create an account on **GitHub.com**.
3. You write some code locally and save it using **Git** (`git commit`).
4. You upload that saved code to your **GitHub** account using the command `git push`.
5. Your teammates download the code from **GitHub** to their local **Git** using the command `git clone` or `git pull`.

## Quick Summary
- **Git** is the local engine tracking your history.
- **GitHub** is the cloud garage storing and sharing your history.
- You must know Git to use GitHub effectively.
