# Troubleshooting

Start with `git status` and read the full error message. These are common situations and safe first steps.

## `fatal: not a git repository`

**Meaning:** The current directory is not inside a Git repository.  
**Try:** Change to the project directory and check for the `.git` directory, or initialize the project if it is new.

```bash
cd path/to/project
git status
```

Use `git init` only when you intend to start a new repository in the current directory.

## `error: remote origin already exists`

**Meaning:** A remote named `origin` is already configured.  
**Try:** Inspect it; if it points to the wrong URL, update it rather than adding another `origin`.

```bash
git remote -v
git remote set-url origin <correct-url>
```

## `rejected - non-fast-forward`

**Meaning:** The remote branch has commits your local branch does not have, so Git will not push over them.  
**Try:** Fetch and integrate the remote changes, resolve any conflicts, then push.

```bash
git pull
git push
```

If your project requires a particular pull strategy, use its guidance. Do not force-push as a reflex; it can overwrite shared work.

## `Permission denied` or authentication failed

**Meaning:** The Git server could not authenticate you or you do not have permission to access that repository.  
**Try:** Verify the remote URL, confirm you are signed in with an account that has access, and check your HTTPS credential-manager or SSH-key setup.

```bash
git remote -v
```

For GitHub HTTPS access, use the supported browser/credential-manager flow or a properly scoped token when required; GitHub account passwords are not accepted as Git passwords. Never paste credentials into a repository or share private keys.

## Merge conflict

**Meaning:** Git could not automatically combine overlapping changes.  
**Try:** Run `git status`, edit the conflicted files to the intended content, remove conflict markers, stage the resolved files, and finish the merge.

```bash
git status
git add <resolved-file>
git commit
```

See [merging](merging.md) for the full process.

## `nothing to commit, working tree clean`

**Meaning:** Git sees no changes to commit. Your edits may already be committed, may not have been saved, or may be ignored.  
**Try:** Check `git status`, confirm the file was saved, and inspect ignore rules if the file is missing from the status output.

```bash
git status
git check-ignore -v <file>
```

## Detached HEAD

**Meaning:** You checked out a commit directly rather than a branch. New commits may not be associated with a branch name.  
**Try:** If you want to keep work from this state, create a branch where you are:

```bash
git switch -c keep-my-work
```

If you did not make work you need to keep, switch back to a branch:

```bash
git switch main
```

## `src refspec ... does not match any`

**Meaning:** The branch or reference you tried to push may not exist locally, or the repository may not have a commit yet.  
**Try:** Check the branch name and make an initial commit if needed.

```bash
git branch
git status
```
