# 🧠 Complete Git & GitHub Tutorial

---

# ****\*\*\*\*****\*****\*\*\*\***** GIT TUTORIAL ********\*\*\*\*********\*********\*\*\*\*********

## 🔹 Repository Setup

git init  
→ Initialize a new git repository

git status  
→ Check current repository status

git add "file_name"  
git add .  
→ Stage specific file or all files

git commit -m "message"  
→ Create a commit

git log  
git log --oneline  
git log --graph --oneline --all  
→ View commit history

---

## 🔹 Undo & Restore

git restore file_name  
→ Discard changes in working directory

git restore --staged file_name  
→ Unstage file

git commit --amend -m "new message"  
→ Change last commit message

git reset --soft HEAD~1  
→ Undo commit, keep changes staged

git reset --mixed HEAD~1  
→ Undo commit, keep changes unstaged

git reset --hard HEAD~1  
→ Delete commit and changes permanently

---

## 🔹 Branching

git branch  
→ List branches

git switch branch_name  
→ Switch branch

git switch -c branch_name  
→ Create and switch branch

git branch -d branch_name  
→ Delete branch

git branch -m new_name  
→ Rename current branch

git branch -m old_name new_name  
→ Rename specific branch

git branch --merged  
→ Show merged branches

git branch --no-merged  
→ Show unmerged branches

---

## 🔹 Merging

git merge branch_name  
→ Merge branch into current branch

---

## 🔹 Rebase (Clean History)

git rebase branch_name  
→ Move current branch commits on top of another branch

git rebase -i HEAD~3  
→ Interactive rebase (edit/squash/reorder commits)

git rebase --abort  
→ Cancel rebase

git rebase --continue  
→ Continue rebase after conflict

---

## 🔹 Stash (Temporary Save)

git stash  
→ Save uncommitted changes

git stash push -m "message"  
→ Save with message

git stash list  
→ Show stash list

git stash apply  
→ Apply last stash

git stash pop  
→ Apply and remove stash

git stash drop  
→ Delete stash

git stash clear  
→ Delete all stashes

---

## 🔹 Viewing Changes

git diff  
→ Show unstaged changes

git diff --staged  
→ Show staged changes

git show commit_id  
→ Show details of specific commit

---

## 🔹 Tagging

git tag  
→ List tags

git tag v1.0  
→ Create tag

git tag -a v1.0 -m "version 1.0"  
→ Create annotated tag

git push origin v1.0  
→ Push tag to remote

git push origin --tags  
→ Push all tags

---

## 🔹 Remote Management

git remote add origin repo_url  
→ Add remote repository

git remote -v  
→ View remote URLs

git remote set-url origin new_url  
→ Change remote URL

git remote remove origin  
→ Remove remote

---

# ****\*\*\*\*****\*****\*\*\*\***** GITHUB TUTORIAL ********\*\*\*\*********\*********\*\*\*\*********

## 🔹 Push & Pull

git push  
→ Push to remote

git push -u origin main  
→ Push and set upstream

git push --force  
→ Force push (overwrite remote)

git fetch  
→ Download remote changes

git pull  
→ Fetch + Merge

git pull --rebase  
→ Fetch + Rebase

---

## 🔹 Cloning

git clone repo_url  
→ Clone repository

---

## 🔹 Tracking Branches

git branch -vv  
→ Show upstream tracking info

---

## 🔹 Conflict Resolution

git status  
→ Check conflict files

After fixing conflicts:

git add file_name  
git commit

---

# 🚀 Advanced Useful Commands

git cherry-pick commit_id  
→ Apply specific commit

git reflog  
→ Show all reference history (life saver)

git clean -fd  
→ Remove untracked files and folders

git blame file_name  
→ See who changed each line

git shortlog  
→ Show contributors summary
