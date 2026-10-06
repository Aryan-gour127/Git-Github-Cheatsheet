# Undoing Changes

The right command depends on whether the change is unstaged, staged, committed locally, or already shared. Check `git status` and `git log` before changing history.

## Discard unstaged edits to a file

**Command:** `git restore <file>`  
**Purpose:** Replaces the file's unstaged working-tree changes with the staged version, or with the last committed version if nothing is staged.  
**Use when:** You intentionally want to discard local edits to that file.

```bash
git restore README.md
```

This discards those unstaged edits. Review or back them up first if they may be needed.

## Unstage a file

**Command:** `git restore --staged <file>`  
**Purpose:** Removes a file from the staging area without discarding its working-tree edits.  
**Use when:** You staged a file by mistake or want to revise what will go into the commit.

```bash
git restore --staged README.md
```

## Reset commits

**Command:** `git reset <commit>`  
**Purpose:** Moves the current branch tip to a selected commit.  
**Use when:** Reorganizing local, unpublished commits and you understand what will happen to their changes.

```bash
git reset --soft HEAD~1   # Undo the last commit; keep changes staged
git reset HEAD~1          # Undo the last commit; keep changes, unstaged
```

`git reset --hard <commit>` also discards changes in the index and working tree. It can permanently lose work; avoid it unless you have verified exactly what will be removed.

## Revert a commit

**Command:** `git revert <commit>`  
**Purpose:** Creates a new commit that undoes the changes from an earlier commit.  
**Use when:** Undoing a commit that has already been pushed or shared, without rewriting shared history.

```bash
git log --oneline
git revert <commit-hash>
```

Resolve any conflicts Git reports, then complete the revert as prompted.

## Amend the latest commit

**Command:** `git commit --amend`  
**Purpose:** Replaces the latest commit, optionally including newly staged changes.  
**Use when:** Correcting the message or adding a small omitted change before the commit has been shared.

```bash
git add <forgotten-file>
git commit --amend
```

Amending changes the commit identity/hash. Avoid amending commits other people may already have based work on.

## Quick decision guide

| Situation | Consider |
|---|---|
| Discard an unstaged file edit | `git restore <file>` |
| Unstage but keep the edits | `git restore --staged <file>` |
| Undo a local, unpublished commit | `git reset` |
| Undo a shared commit safely | `git revert` |
| Fix the latest, unshared commit | `git commit --amend` |
