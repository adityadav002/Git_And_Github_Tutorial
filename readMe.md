<div align="center">

# 🚀 Git & GitHub Complete Tutorial

**A comprehensive, beginner-friendly reference guide for Git version control and GitHub collaboration.**

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

</div>

---

## 📚 Table of Contents

| #   | Topic                                           |
| --- | ----------------------------------------------- |
| 1   | [🗂️ Repository Setup](#️-repository-setup)       |
| 2   | [↩️ Undo & Restore](#️-undo--restore)            |
| 3   | [🌿 Branching](#-branching)                     |
| 4   | [🔀 Merging](#-merging)                         |
| 5   | [📐 Rebase](#-rebase--clean-history)            |
| 6   | [📦 Stash](#-stash--temporary-save)             |
| 7   | [🔍 Viewing Changes](#-viewing-changes)         |
| 8   | [🏷️ Tagging](#️-tagging)                         |
| 9   | [🌐 Remote Management](#-remote-management)     |
| 10  | [⬆️ Push & Pull](#️-push--pull)                  |
| 11  | [📥 Cloning](#-cloning)                         |
| 12  | [🔗 Tracking Branches](#-tracking-branches)     |
| 13  | [⚠️ Conflict Resolution](#️-conflict-resolution) |
| 14  | [⚡ Advanced Commands](#-advanced-commands)     |

---

## 🗂️ Repository Setup

> **Initialize and manage your Git repository from the ground up.**

| Command                           | Description                                       |
| --------------------------------- | ------------------------------------------------- |
| `git init`                        | Initialize a new Git repository                   |
| `git status`                      | Check the current state of your working directory |
| `git add <file>`                  | Stage a specific file for commit                  |
| `git add .`                       | Stage **all** modified/new files                  |
| `git commit -m "message"`         | Save staged changes with a descriptive message    |
| `git log`                         | View full commit history                          |
| `git log --oneline`               | Compact one-line commit history                   |
| `git log --graph --oneline --all` | Visual branch graph of all commits                |

```bash
# Example workflow
git init
git add .
git commit -m "Initial commit"
git log --oneline
```

---

## ↩️ Undo & Restore

> **Safely undo mistakes at any stage — staged, unstaged, or committed.**

| Command                           | Description                                       |
| --------------------------------- | ------------------------------------------------- |
| `git restore <file>`              | Discard changes in working directory              |
| `git restore --staged <file>`     | Unstage a file (keep changes)                     |
| `git commit --amend -m "new msg"` | Edit the **last** commit message                  |
| `git reset --soft HEAD~1`         | Undo last commit → keep changes **staged**        |
| `git reset --mixed HEAD~1`        | Undo last commit → keep changes **unstaged**      |
| `git reset --hard HEAD~1`         | ⚠️ Permanently delete last commit and all changes |

```bash
# Accidentally staged the wrong file?
git restore --staged mistake.txt

# Typo in your last commit message?
git commit --amend -m "Fix: correct typo in login function"
```

> ⚠️ **Warning:** `git reset --hard` is **irreversible**. Use with caution!

---

## 🌿 Branching

> **Work on features or fixes in isolation without affecting the main codebase.**

| Command                     | Description                       |
| --------------------------- | --------------------------------- |
| `git branch`                | List all local branches           |
| `git switch <branch>`       | Switch to an existing branch      |
| `git switch -c <branch>`    | Create and switch to a new branch |
| `git branch -d <branch>`    | Delete a merged branch            |
| `git branch -m <new-name>`  | Rename the current branch         |
| `git branch -m <old> <new>` | Rename a specific branch          |
| `git branch --merged`       | Show branches already merged      |
| `git branch --no-merged`    | Show branches not yet merged      |

```bash
# Start working on a new feature
git switch -c feature/user-authentication

# Clean up after merging
git branch --merged
git branch -d feature/user-authentication
```

---

## 🔀 Merging

> **Combine completed feature branches back into the main branch.**

| Command              | Description                                    |
| -------------------- | ---------------------------------------------- |
| `git merge <branch>` | Merge specified branch into the current branch |

```bash
# Merge a feature into main
git switch main
git merge feature/user-authentication
```

---

## 📐 Rebase — Clean History

> **Rewrite commit history for a cleaner, linear project timeline.**

| Command                 | Description                                           |
| ----------------------- | ----------------------------------------------------- |
| `git rebase <branch>`   | Move current branch commits on top of another         |
| `git rebase -i HEAD~3`  | Interactively edit, squash, or reorder last 3 commits |
| `git rebase --abort`    | Cancel an ongoing rebase                              |
| `git rebase --continue` | Resume rebase after resolving a conflict              |

```bash
# Clean up last 3 commits before pushing
git rebase -i HEAD~3
# Options: pick, squash, reword, drop
```

> 💡 **Tip:** Never rebase commits that have already been pushed to a shared branch!

---

## 📦 Stash — Temporary Save

> **Temporarily shelve changes so you can switch context without committing.**

| Command                       | Description                                   |
| ----------------------------- | --------------------------------------------- |
| `git stash`                   | Save all uncommitted changes                  |
| `git stash push -m "message"` | Save stash with a descriptive label           |
| `git stash list`              | View all saved stashes                        |
| `git stash apply`             | Apply the most recent stash (keep it in list) |
| `git stash pop`               | Apply and **remove** the most recent stash    |
| `git stash drop`              | Delete the most recent stash                  |
| `git stash clear`             | Delete **all** stashes                        |

```bash
# You're mid-feature and need to fix a hotfix urgently
git stash push -m "WIP: user auth form"
git switch hotfix/critical-bug
# ... fix and commit ...
git switch feature/user-auth
git stash pop
```

---

## 🔍 Viewing Changes

> **Inspect exactly what changed, where, and when.**

| Command                | Description                            |
| ---------------------- | -------------------------------------- |
| `git diff`             | Show unstaged changes                  |
| `git diff --staged`    | Show staged (ready-to-commit) changes  |
| `git show <commit-id>` | Show full details of a specific commit |

```bash
# Review changes before staging
git diff

# Review what will be committed
git diff --staged
```

---

## 🏷️ Tagging

> **Mark specific points in history, like releases or milestones.**

| Command                            | Description                            |
| ---------------------------------- | -------------------------------------- |
| `git tag`                          | List all tags                          |
| `git tag v1.0`                     | Create a lightweight tag               |
| `git tag -a v1.0 -m "Version 1.0"` | Create an annotated tag with a message |
| `git push origin v1.0`             | Push a specific tag to remote          |
| `git push origin --tags`           | Push **all** tags to remote            |

```bash
# Mark a production release
git tag -a v2.0.0 -m "Release version 2.0.0"
git push origin v2.0.0
```

---

## 🌐 Remote Management

> **Connect and manage your local repository with a remote server.**

| Command                               | Description                          |
| ------------------------------------- | ------------------------------------ |
| `git remote add origin <url>`         | Link a remote repository             |
| `git remote -v`                       | View all remote connections and URLs |
| `git remote set-url origin <new-url>` | Update the remote URL                |
| `git remote remove origin`            | Remove the remote connection         |

```bash
# Connect to GitHub for the first time
git remote add origin https://github.com/username/repo.git
git remote -v
```

---

## ⬆️ Push & Pull

> **Sync your local commits with GitHub and keep up to date with your team.**

| Command                   | Description                               |
| ------------------------- | ----------------------------------------- |
| `git push`                | Push commits to remote                    |
| `git push -u origin main` | Push and set tracking upstream branch     |
| `git push --force`        | ⚠️ Force push (overwrites remote history) |
| `git fetch`               | Download remote changes (don't apply yet) |
| `git pull`                | Fetch **and** merge remote changes        |
| `git pull --rebase`       | Fetch and rebase instead of merge         |

```bash
# First-time push to GitHub
git push -u origin main

# Sync your team's latest changes
git pull --rebase
```

> ⚠️ **Warning:** `git push --force` overwrites remote history. Never use on shared branches!

---

## 📥 Cloning

> **Download a complete copy of any repository to your local machine.**

| Command           | Description                       |
| ----------------- | --------------------------------- |
| `git clone <url>` | Clone a remote repository locally |

```bash
git clone https://github.com/username/repository.git
```

---

## 🔗 Tracking Branches

> **Understand the connection between your local and remote branches.**

| Command          | Description                                         |
| ---------------- | --------------------------------------------------- |
| `git branch -vv` | Show all branches with their upstream tracking info |

```bash
git branch -vv
# main  abc1234 [origin/main] Latest commit message
```

---

## ⚠️ Conflict Resolution

> **Resolve merge conflicts when two branches have competing changes.**

```bash
# Step 1: Check which files have conflicts
git status

# Step 2: Open the conflicting file and look for conflict markers
# <<<<<<< HEAD
#   your changes
# =======
#   incoming changes
# >>>>>>> branch-name

# Step 3: Edit the file to keep what you want, then:
git add <resolved-file>
git commit
```

---

## ⚡ Advanced Commands

> **Power-user tools for complex operations and history investigation.**

| Command                       | Description                                            |
| ----------------------------- | ------------------------------------------------------ |
| `git cherry-pick <commit-id>` | Apply a specific commit onto the current branch        |
| `git reflog`                  | 🛟 View ALL reference history — the ultimate undo tool |
| `git clean -fd`               | Remove all untracked files and folders                 |
| `git blame <file>`            | See who last changed each line of a file               |
| `git shortlog`                | Summarize commits by contributor                       |

```bash
# Accidentally deleted a branch? Recover it with reflog!
git reflog
git switch -c recovered-branch <commit-id>

# Find out who wrote a specific line
git blame src/app.js
```

> 💡 **Pro Tip:** `git reflog` is your safety net. It keeps a log of everything — even after resets and deleted branches!

---

<div align="center">

## 🎯 Quick Reference Cheat Sheet

| Stage                | Command                                           |
| -------------------- | ------------------------------------------------- |
| Start project        | `git init` → `git add .` → `git commit -m "init"` |
| New feature          | `git switch -c feature/name`                      |
| Save progress        | `git add .` → `git commit -m "message"`           |
| Sync with team       | `git pull --rebase`                               |
| Publish work         | `git push -u origin <branch>`                     |
| Undo last commit     | `git reset --soft HEAD~1`                         |
| Emergency save       | `git stash push -m "WIP"`                         |
| Something went wrong | `git reflog`                                      |

---

### ⭐ Found this helpful? Give it a star!

_Made with ❤️ for developers who want to master Git._

</div>
