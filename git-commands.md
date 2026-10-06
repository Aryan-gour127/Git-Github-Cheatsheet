# Everyday Git Commands

## Install Git

Install Git using an official installer or your operating system's package manager. On Windows, for example:

```powershell
winget install --id Git.Git -e
```

Then open a new terminal and check the installation:

```bash
git --version
```

## Configure your identity

Git records the configured name and email in your commits. These values are not your GitHub login credentials.

**Command:** `git config --global user.name "Your Name"`  
**Purpose:** Sets the author name for commits made by your user account.  
**Use when:** Setting up Git on a computer for the first time.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Use an email address associated with your GitHub account if you want GitHub to attribute your commits to that account. `--global` applies the setting to all repositories for your user; omit it to configure only the current repository.

Check the values:

```bash
git config --global --list
```

## Initialize or copy a repository

**Command:** `git init`  
**Purpose:** Creates a new Git repository in the current directory.  
**Use when:** Starting version control for a project that is not already a Git repository.

```bash
git init
```

**Command:** `git clone <url>`  
**Purpose:** Downloads a repository, including its history, into a new directory.  
**Use when:** You want to work on a repository hosted on GitHub or another Git server.

```bash
git clone https://github.com/OWNER/REPOSITORY.git
```

## Check, stage, and save changes

**Command:** `git status`  
**Purpose:** Shows the current branch and which files are modified, staged, or untracked.  
**Use when:** You want to understand the state of your working directory.

```bash
git status
```

**Command:** `git add <file>`  
**Purpose:** Stages selected changes for the next commit.  
**Use when:** You have reviewed a file and want its current changes included in a commit.

```bash
git add README.md
```

To stage all changes under the current directory, use `git add .`; check `git status` first so you do not include unintended files.

**Command:** `git commit -m "message"`  
**Purpose:** Saves staged changes as a commit in the local repository.  
**Use when:** You have a focused set of changes ready to record.

```bash
git commit -m "Document setup steps"
```

**Command:** `git log`  
**Purpose:** Displays commit history.  
**Use when:** Reviewing previous work or finding a commit to inspect.

```bash
git log --oneline
```

**Command:** `git diff`  
**Purpose:** Shows unstaged changes compared with the last commit.  
**Use when:** Reviewing edits before staging them.

```bash
git diff
```

To review changes that are already staged, use `git diff --staged`.

## Sync with a remote

**Command:** `git pull`  
**Purpose:** Fetches remote changes and integrates them into the current branch.  
**Use when:** Updating a branch with work from its remote counterpart.

```bash
git pull
```

**Command:** `git push`  
**Purpose:** Sends local commits to a remote repository.  
**Use when:** Sharing your commits or updating a branch on GitHub.

```bash
git push
```

The first push of a new branch often needs an upstream:

```bash
git push -u origin <branch-name>
```

See [remote repositories](remote-repositories.md) for setup and synchronization details.
