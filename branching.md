# Branching

A branch is a movable name pointing to a line of development. Branches let you work on a feature or fix without immediately changing the default branch.

## List branches

**Command:** `git branch`  
**Purpose:** Lists local branches; the current branch is marked with `*`.  
**Use when:** Checking which branch you are on or what branches exist.

```bash
git branch
```

List local and remote-tracking branches:

```bash
git branch --all
```

## Create and switch branches

**Command:** `git switch -c <branch-name>`  
**Purpose:** Creates a branch and switches to it.  
**Use when:** Beginning an isolated feature or fix.

```bash
git switch -c add-search
```

**Command:** `git switch <branch-name>`  
**Purpose:** Switches to an existing branch.  
**Use when:** Returning to another line of work.

```bash
git switch main
```

Git may prevent switching if doing so would overwrite local changes. Commit, stash, or otherwise safely handle those changes first.

## `switch` and `checkout`

`git switch` is the focused command for changing branches. The older `git checkout` command can switch branches, restore files, and perform other operations, so it can be less clear to beginners.

```bash
git checkout -b add-search   # Create and switch (older form)
git checkout main            # Switch branches (older form)
```

Use `git restore` for restoring file contents; see [undoing changes](undoing-changes.md).

## Rename or delete a branch

Rename the current branch:

```bash
git branch -m new-name
```

**Command:** `git branch -d <branch-name>`  
**Purpose:** Deletes a local branch that Git considers fully merged.  
**Use when:** Cleaning up a completed branch.

```bash
git branch -d add-search
```

`git branch -D <branch-name>` forces deletion even if the branch is not merged. It can discard the only convenient reference to work, so use it only when you are sure the branch is no longer needed.

Delete a branch from a remote:

```bash
git push origin --delete <branch-name>
```

## Typical feature branch

```bash
git switch main
git pull
git switch -c describe-your-change
# edit files
git add <file>
git commit -m "Describe your change"
git push -u origin describe-your-change
```

Then open a pull request on GitHub. For the full collaboration flow, see [collaboration](collaboration.md).
