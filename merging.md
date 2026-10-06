# Merging and Merge Conflicts

Merging combines changes from one branch into another. First switch to the branch that should receive the changes, then merge the source branch into it.

## Merge a branch

**Command:** `git merge <branch-name>`  
**Purpose:** Integrates the named branch into the current branch.  
**Use when:** Bringing completed work into a target branch.

```bash
git switch main
git merge add-search
```

If the branches have diverged, Git may create a merge commit. If one branch is already an ancestor of the other, Git may perform a fast-forward update instead.

## Resolve a merge conflict

A conflict means Git could not automatically combine edits to the same part of a file.

1. Run `git status` to see which files need attention.
2. Open each conflicted file and find conflict markers:

   ```text
   <<<<<<< HEAD
   Content from the current branch
   =======
   Content from the branch being merged
   >>>>>>> add-search
   ```

3. Edit the file to the intended final content and remove all conflict markers.
4. Review the result, then stage the resolved file:

   ```bash
   git add <file>
   ```

5. Complete the merge if Git has not completed it automatically:

   ```bash
   git commit
   ```

Check `git status` and test the result. If you need to abandon an in-progress merge before committing, use `git merge --abort`; it attempts to return to the pre-merge state.

## Reduce conflict risk

- Keep branches focused and reasonably short-lived.
- Pull or fetch recent target-branch changes before beginning or updating work.
- Communicate when several people are editing the same files.
- Resolve conflicts deliberately; do not choose one entire side without reviewing it.

See [remote repositories](remote-repositories.md) for fetching and pulling, and [collaboration](collaboration.md) for pull request workflows.
