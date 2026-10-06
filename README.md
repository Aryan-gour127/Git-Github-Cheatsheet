# Git & GitHub Cheat Sheet

A beginner-friendly reference for essential Git commands, branching, collaboration, troubleshooting, and useful GitHub features.

> **Suggested GitHub description:** 📚 A beginner-friendly Git & GitHub cheat sheet covering essential commands, workflows, branching, collaboration, troubleshooting, and useful GitHub features.
>
> **Suggested topics:** `git` `github` `git-cheatsheet` `version-control` `developer-resources` `beginners` `open-source` `programming`

## Git in a nutshell

- **Git** is a version control system. It records changes to files so you can review history, restore earlier versions, and work on changes in parallel.
- **GitHub** is an online platform for hosting Git repositories and collaborating through pull requests, issues, and other tools.
- **Git vs. GitHub:** Git is the tool that tracks versions; GitHub is one service that hosts Git repositories. Git also works locally and with other hosting services.

## Getting started

1. [Install Git](git-commands.md#install-git).
2. [Set your name and email](git-commands.md#configure-your-identity).
3. In a project folder, run `git init` to start tracking it, or use `git clone <url>` to copy an existing repository.
4. Use `git status` often to check what has changed.
5. Stage changes with `git add`, then save a snapshot with `git commit`.

## Guides

- [Everyday Git commands](git-commands.md)
- [Branching](branching.md)
- [Merging and conflicts](merging.md)
- [Remote repositories](remote-repositories.md)
- [Undoing changes](undoing-changes.md)
- [GitHub features](github-commands.md)
- [Collaboration workflow](collaboration.md)
- [Troubleshooting](troubleshooting.md)
- [Writing a `.gitignore`](gitignore.md)

## A safe everyday loop

```bash
git status
git add <file>
git diff --staged
git commit -m "Describe the change"
git push
```

Review staged changes before committing. If the repository has a remote, get its latest changes before starting work when appropriate; see [remote repositories](remote-repositories.md).

## A few important habits

- Commits are local until pushed to a remote.
- A commit should describe a small, coherent change.
- Avoid committing passwords, API keys, private keys, or other secrets. Adding a secret to `.gitignore` does not remove it from commits already made.
- Prefer `git revert` to undo a commit that has already been shared. See [undoing changes](undoing-changes.md).
- Be careful with `git reset --hard` and force pushes: they can discard work or rewrite shared history.
