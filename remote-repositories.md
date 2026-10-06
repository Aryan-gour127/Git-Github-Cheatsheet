# Remote Repositories

A remote is a named reference to another copy of a repository, commonly hosted on GitHub. `origin` is a conventional name for the remote created by `git clone`; it is not a special requirement.

## Inspect and configure a remote

**Command:** `git remote -v`  
**Purpose:** Lists configured remote names and their fetch/push URLs.  
**Use when:** Checking where a repository fetches from or pushes to.

```bash
git remote -v
```

**Command:** `git remote add origin <url>`  
**Purpose:** Adds a remote named `origin`.  
**Use when:** Connecting a locally initialized repository to a new hosted repository.

```bash
git remote add origin https://github.com/OWNER/REPOSITORY.git
```

If `origin` already exists, inspect it with `git remote -v`. To change its URL:

```bash
git remote set-url origin <url>
```

## Fetch, pull, and push

**Command:** `git fetch`  
**Purpose:** Downloads remote updates without integrating them into the current branch.  
**Use when:** You want to inspect what changed before deciding how to integrate it.

```bash
git fetch origin
```

**Command:** `git pull`  
**Purpose:** Fetches updates and integrates them into the current branch.  
**Use when:** Updating your local branch from its upstream branch.

```bash
git pull
```

`git pull` usually behaves like a fetch followed by a merge, but configuration can change the integration method. If your team expects a particular strategy, follow that project guidance.

**Command:** `git push -u origin <branch-name>`  
**Purpose:** Publishes local commits and sets the remote branch as the upstream for future pushes and pulls.  
**Use when:** Publishing a new local branch for the first time.

```bash
git push -u origin main
```

After an upstream is configured, `git push` and `git pull` usually know which branch to use.

## HTTPS and SSH URLs

GitHub supports HTTPS and SSH remote URLs. With HTTPS, GitHub authentication typically uses a browser sign-in or a credential manager; account passwords are not accepted as Git passwords. With SSH, configure an SSH key with GitHub before using the SSH URL. Never share private keys or access tokens.
