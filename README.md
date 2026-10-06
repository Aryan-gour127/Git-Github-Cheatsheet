# 🌸 Git & GitHub Cheat Sheet

> 🐣 **A little reference for your Git & GitHub journey!**

Whether you're making your **first commit**, creating branches, fixing merge conflicts, or pushing your latest project to GitHub — this cheat sheet is here to help. 💻✨

---

## 🎀 What's Inside?

This repository covers:

```text
🌱 Git Basics
📦 Everyday Commands
🌿 Branching
🔀 Merging & Conflicts
☁️ Remote Repositories
↩️ Undoing Changes
🤝 Collaboration
🐙 GitHub Features
🛠️ Troubleshooting
🙈 .gitignore
```

> 💡 **Goal:** Keep the most useful Git & GitHub commands in one simple, beginner-friendly place.

---

## 🐙 Git in a Nutshell

### 🌱 What is Git?

**Git** is a version control system that keeps track of changes in your files.

It lets you:

* 🕐 View your project history
* ↩️ Restore previous versions
* 🌿 Create separate branches
* 🔀 Merge different changes
* 👥 Work with other developers

### ☁️ What is GitHub?

**GitHub** is an online platform for hosting Git repositories and collaborating with other developers.

You can use GitHub for:

* 📦 Hosting repositories
* 🤝 Pull Requests
* 🐛 Issues
* 💬 Discussions
* ⭐ Stars
* 👥 Collaboration
* 🚀 Open-source projects

### ⚡ Git vs GitHub

| Git                       | GitHub                                |
| ------------------------- | ------------------------------------- |
| 🖥️ Software/tool         | ☁️ Online platform                    |
| 📌 Tracks changes         | 📦 Hosts repositories                 |
| 💻 Works locally          | 🌐 Works online                       |
| 🔀 Handles branches       | 🤝 Enables collaboration              |
| 🕐 Stores project history | 🐙 Provides Git-based developer tools |

> ✨ **Think of it this way:**
> Git = Your version-control toolbox 🧰
> GitHub = Your online workshop 🏠

---

## 🚀 Getting Started

### 1️⃣ Install Git

👉 [Install Git](git-commands.md#install-git)

### 2️⃣ Configure Your Identity

Set your Git username and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### 3️⃣ Start a Repository

Create a new Git repository:

```bash
git init
```

Or clone an existing repository:

```bash
git clone <url>
```

### 4️⃣ Check Your Project

```bash
git status
```

> 👀 Make `git status` your best friend. It tells you what's happening inside your repository.

### 5️⃣ Stage Your Changes

```bash
git add <file>
```

Or stage everything:

```bash
git add .
```

### 6️⃣ Create a Commit

```bash
git commit -m "Describe the change"
```

### 7️⃣ Push to GitHub

```bash
git push
```

🎉 And your changes are on GitHub!

---

# 📚 Guides

Explore the detailed guides in this repository:

| Guide                                            | What's inside                              |
| ------------------------------------------------ | ------------------------------------------ |
| 📦 [Everyday Git Commands](git-commands.md)      | Essential commands you'll use regularly    |
| 🌿 [Branching](branching.md)                     | Create, switch and manage branches         |
| 🔀 [Merging & Conflicts](merging.md)             | Merge branches and solve conflicts         |
| ☁️ [Remote Repositories](remote-repositories.md) | Push, pull, fetch and manage remotes       |
| ↩️ [Undoing Changes](undoing-changes.md)         | Restore, reset, revert and amend           |
| 🐙 [GitHub Features](github-commands.md)         | Useful GitHub features and workflows       |
| 🤝 [Collaboration](collaboration.md)             | Work with other developers                 |
| 🛠️ [Troubleshooting](troubleshooting.md)        | Common Git problems and solutions          |
| 🙈 [`.gitignore`](gitignore.md)                  | Keep unwanted files out of your repository |

---

# 🔄 A Safe Everyday Git Loop

When working on a project, this is a simple workflow to remember:

```bash
git status

git add <file>

git diff --staged

git commit -m "Describe the change"

git push
```

### 🧠 Why this workflow?

```text
👀 Check
   ↓
📦 Stage
   ↓
🔍 Review
   ↓
💾 Commit
   ↓
☁️ Push
```

> 💡 **Tip:** Always review your staged changes before committing.

If your repository uses a remote, make sure you're working with the latest changes when appropriate.

👉 [Learn more about remote repositories](remote-repositories.md)

---

# 🌟 Important Git Habits

### 💾 1. Commits are Local

A commit exists on your local machine until you push it to a remote repository.

```text
Your Computer
     │
     │ git commit
     ▼
  Local Git
     │
     │ git push
     ▼
   GitHub ☁️
```

---

### 🧩 2. Keep Commits Small

A good commit should represent **one small, coherent change**.

Instead of:

```text
❌ "Updated everything"
```

Prefer:

```text
✅ "Add login form"
✅ "Fix navbar alignment"
✅ "Update README"
```

Small commits = easier history + easier debugging. ✨

---

### 🔐 3. Never Commit Secrets

🚨 **Never commit:**

```text
❌ Passwords
❌ API keys
❌ Private keys
❌ Access tokens
❌ Database credentials
❌ .env files containing secrets
```

A `.gitignore` file can prevent files from being added in the future, but:

> ⚠️ **Adding a secret to `.gitignore` does NOT remove it from commits that already contain it.**

If a secret has already been pushed, treat it as exposed and rotate/revoke it.

👉 [Learn about `.gitignore`](gitignore.md)

---

### ↩️ 4. Be Careful When Undoing Changes

For commits that have already been shared, **`git revert`** is generally safer because it creates a new commit that reverses the earlier one.

👉 [Learn about undoing changes](undoing-changes.md)

---

### ⚠️ 5. Be Careful With `reset --hard`

Commands such as:

```bash
git reset --hard
```

can permanently discard local changes.

Force pushing can also rewrite shared history:

```bash
git push --force
```

🚨 Use these carefully, especially when working with other people.

---

# 🧠 Quick Command Memory

```text
🌱 Start
git init

📥 Copy a repository
git clone <url>

👀 Check changes
git status

📦 Stage changes
git add .

💾 Save changes
git commit -m "message"

☁️ Upload changes
git push

⬇️ Get changes
git pull

🌿 Create branch
git branch <name>

🔀 Switch branch
git switch <name>

🔀 Merge branch
git merge <name>

↩️ Undo a shared commit
git revert <commit>

🔍 View history
git log
```

---

# 🐣 Beginner Workflow

If you're completely new to Git, remember this:

```text
        💻 Make changes
              ↓
        👀 git status
              ↓
        📦 git add
              ↓
        💾 git commit
              ↓
        ☁️ git push
              ↓
          🐙 GitHub
```

That's the basic Git cycle. 🎀

---

# 💗 Repository Goals

This cheat sheet is designed to be:

* 🌱 Beginner-friendly
* 📚 Easy to reference
* 🧠 Easy to understand
* 🛠️ Practical
* 🔄 Continuously expandable

I'll keep adding useful commands, workflows, tips, and troubleshooting examples as I learn more about Git and GitHub.

---

## ⭐ If This Helps You

If this repository helps you learn Git or saves you from searching for the same command 20 times 😭:

**⭐ Give it a star!**

Feel free to fork it, improve it, and add your own useful Git tips.

---

## 🛠️ Tech

```text
Git
GitHub
Markdown
```

---

## 📜 License

This repository is open for learning and educational purposes.

---

<div align="center">

### 🌸 Keep committing. Keep learning. Keep building. 🚀

**`git add` → `git commit` → `git push` → 🎉**

Made with 💗 and a little too much `git status`.

</div>
