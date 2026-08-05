# 🚀 Git Cheat Sheet

> A clean and beginner-friendly reference for the most important Git commands with simple explanations and visual examples.

---

# 📚 Table of Contents

- Git Setup
- Repository
- Staging & Committing
- Branching
- Remote Repository
- Pull & Push
- Merge & Rebase
- Undo Changes
- Stashing
- Logs & History
- Tags
- Helpful Commands

---

# ⚙️ Git Setup

## Check Git Version

```bash
git --version
```

📌 Checks whether Git is installed and shows the installed version.

---

## Configure Username

```bash
git config --global user.name "Your Name"
```

📌 Sets your Git username.

---

## Configure Email

```bash
git config --global user.email "you@example.com"
```

📌 Sets your Git email.

---

## View Configuration

```bash
git config --list
```

📌 Displays all Git configuration settings.

---

# 📂 Repository

## Initialize a Repository

```bash
git init
```

📌 Creates a new Git repository in the current folder.

```
Project Folder
│
├── .git/
├── src/
└── README.md
```

---

## Clone an Existing Repository

```bash
git clone <repository-url>
```

Example

```bash
git clone https://github.com/user/project.git
```

📌 Downloads an existing repository from GitHub.

```
GitHub
   │
   ▼
Your Computer
```

---

# 📄 Check Repository Status

```bash
git status
```

📌 Shows modified, staged, and untracked files.

Example

```
Modified:
  app.js

Untracked:
  styles.css
```

---

# 📦 Staging Files

## Stage One File

```bash
git add filename
```

Example

```bash
git add index.js
```

📌 Adds a specific file to the staging area.

---

## Stage All Files

```bash
git add .
```

📌 Adds every changed file to staging.

```
Working Directory
        │
        ▼
 Staging Area
```

---

# 💾 Commit Changes

## Commit with Message

```bash
git commit -m "Add login page"
```

📌 Saves staged changes into Git history.

```
Working Directory
      │
      ▼
 Staging Area
      │
      ▼
 Git History
```

---

## Stage and Commit Tracked Files

```bash
git commit -am "Fix navbar"
```

📌 Stages and commits modified tracked files.

> Doesn't include newly created files.

---

# 🌿 Branches

## View Branches

```bash
git branch
```

📌 Lists all local branches.

---

## Create a Branch

```bash
git branch feature/login
```

📌 Creates a new branch.

```
main
 │
 └── feature/login
```

---

## Switch Branch

```bash
git checkout feature/login
```

or

```bash
git switch feature/login
```

📌 Moves to another branch.

---

## Create and Switch

```bash
git checkout -b feature/login
```

or

```bash
git switch -c feature/login
```

📌 Creates and switches to a new branch in one command.

---

## Delete Branch

```bash
git branch -d feature/login
```

📌 Deletes a merged branch.

---

## Force Delete Branch

```bash
git branch -D feature/login
```

📌 Deletes a branch even if it's not merged.

---

# 🌍 Remote Repository

## View Remote

```bash
git remote -v
```

📌 Shows connected GitHub repositories.

---

## Add Remote

```bash
git remote add origin <repository-url>
```

Example

```bash
git remote add origin https://github.com/user/project.git
```

---

## Change Remote URL

```bash
git remote set-url origin <new-url>
```

📌 Updates the repository URL.

---

# ☁️ Push Changes

## First Push

```bash
git push -u origin main
```

📌 Pushes local commits and sets upstream.

```
Local Repository
        │
        ▼
      GitHub
```

---

## Push Changes

```bash
git push
```

📌 Uploads commits to GitHub.

---

# ⬇️ Pull Changes

## Download Latest Changes

```bash
git pull
```

📌 Downloads and merges changes from GitHub.

```
GitHub
   │
   ▼
Local Repository
```

---

## Fetch Without Merging

```bash
git fetch
```

📌 Downloads changes but doesn't merge them.

---

# 🔀 Merge

```bash
git merge feature/login
```

📌 Merges another branch into the current branch.

```
feature/login
      │
      ▼
     main
```

---

# 🔄 Rebase

```bash
git rebase main
```

📌 Replays your commits on top of another branch for a cleaner history.

Before

```
main
A──B──C

feature
     \
      D──E
```

After

```
main
A──B──C

feature
        \
         D──E
```

---

# ⏪ Undo Changes

## Restore File

```bash
git restore filename
```

📌 Discards unstaged changes.

---

## Unstage File

```bash
git restore --staged filename
```

📌 Removes a file from staging.

---

## Undo Last Commit (Keep Changes)

```bash
git reset --soft HEAD~1
```

📌 Removes last commit but keeps files staged.

---

## Undo Last Commit (Keep Files)

```bash
git reset --mixed HEAD~1
```

📌 Removes last commit and unstages files.

---

## Remove Everything

```bash
git reset --hard HEAD
```

⚠️ Permanently deletes uncommitted changes.

---

# 📦 Stash

## Save Current Work

```bash
git stash
```

📌 Temporarily stores unfinished work.

---

## View Stashes

```bash
git stash list
```

---

## Apply Latest Stash

```bash
git stash apply
```

---

## Remove Latest Stash

```bash
git stash pop
```

---

# 📜 Logs

## Commit History

```bash
git log
```

📌 Shows detailed commit history.

---

## One-Line History

```bash
git log --oneline
```

Example

```
a4d91f2 Add login
8bd2ab3 Update README
13fe245 Initial commit
```

---

## Graph View

```bash
git log --oneline --graph --all
```

Example

```
* a4d91f2 Login
|\
| * 5bc129 Dashboard
|/
* 13fe245 Initial
```

---

# 🏷️ Tags

## Create Tag

```bash
git tag v1.0
```

---

## List Tags

```bash
git tag
```

---

## Push Tags

```bash
git push origin --tags
```

---

# 🗑️ Remove Files

## Remove File

```bash
git rm filename
```

📌 Deletes file and stages deletion.

---

## Remove Cached File

```bash
git rm --cached filename
```

📌 Removes file from Git but keeps it locally.

---

# 🔍 Difference

## View Changes

```bash
git diff
```

📌 Shows unstaged changes.

---

## View Staged Changes

```bash
git diff --staged
```

📌 Shows staged changes before committing.

---

# ⭐ Helpful Commands

## Show Current Branch

```bash
git branch --show-current
```

---

## Show File History

```bash
git blame filename
```

Shows who changed each line.

---

## Find Commit

```bash
git log --grep="login"
```

Search commits by message.

---

## Clean Untracked Files

```bash
git clean -fd
```

⚠️ Deletes untracked files and folders.

---

# 🧠 Git Workflow

```
        Create / Modify Files
                 │
                 ▼
        git status
                 │
                 ▼
          git add .
                 │
                 ▼
git commit -m "Meaningful message"
                 │
                 ▼
           git push
                 │
                 ▼
             GitHub
```

---

# 🎯 Most Used Commands

| Command | Purpose |
|----------|----------|
| `git init` | Initialize repository |
| `git clone` | Download repository |
| `git status` | Check status |
| `git add .` | Stage all changes |
| `git commit -m` | Save changes |
| `git push` | Upload commits |
| `git pull` | Download latest changes |
| `git fetch` | Fetch changes only |
| `git branch` | View branches |
| `git switch` | Switch branch |
| `git merge` | Merge branches |
| `git rebase` | Clean commit history |
| `git stash` | Save unfinished work |
| `git log --oneline` | Compact commit history |
| `git diff` | View changes |
| `git restore` | Undo file changes |
| `git reset` | Undo commits |

---

# 💡 Best Practices

- ✅ Commit small, meaningful changes.
- ✅ Write clear commit messages.
- ✅ Pull before pushing.
- ✅ Create feature branches for new work.
- ✅ Never commit sensitive files (`.env`, API keys).
- ✅ Add a `.gitignore` file.
- ✅ Review changes using `git diff` before committing.

---

## ⭐ If this repository helps you, consider giving it a Star!
