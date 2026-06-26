# Tags and Releases

## What is it?
A **Tag** is a permanent label you attach to a specific commit to mark an important milestone (like version `v1.0.0`). A **Release** is a GitHub feature built on top of a tag that adds release notes and downloadable files.

## Why do we use it?
Tags make it easy to find specific versions of your software. Instead of looking for commit `a1b2c3d`, you look for tag `v2.1.0`. Releases allow users to download compiled versions of your software without needing to clone the raw code.

## Basic Syntax

Create a tag:
```bash
git tag -a v1.0.0 -m "First major release"
```

Push tags to GitHub:
```bash
git push origin --tags
```

## Example
1. You finish building your app and commit the final code.
2. You run `git tag -a v1.0.0 -m "Launch version"`.
3. You run `git push origin v1.0.0`.
4. On GitHub, you go to "Releases" -> "Draft a new release", select `v1.0.0`, write release notes, and publish.

## Common Mistakes
- **Forgetting to push tags:** Normal `git push` does not push tags! You must use `git push --tags` or push the specific tag name.

## Quick Summary
- Tags attach a version number to a commit.
- Use `git tag -a <name>` to create one.
- Releases on GitHub provide a professional way to distribute versions of your app.
