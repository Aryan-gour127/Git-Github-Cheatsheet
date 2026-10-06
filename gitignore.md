# `.gitignore` Guide

A `.gitignore` file tells Git which **untracked** files and directories to ignore. It is usually placed at the root of a repository, and can also be added in subdirectories.

## Example

```gitignore
# Operating system files
.DS_Store
Thumbs.db

# Editor settings (keep shared project configuration if needed)
.vscode/

# Generated output
dist/
build/

# Local environment files; do not commit secrets
.env
.env.*
!.env.example
```

Patterns depend on the project. Do not ignore files the project needs to build or run, and do not ignore shared editor settings if the team intentionally tracks them.

## Common patterns

| Pattern | Meaning |
|---|---|
| `file.txt` | Ignore a matching file name under this directory and its descendants |
| `/file.txt` | Ignore this file only at the directory containing this `.gitignore` |
| `logs/` | Ignore directories named `logs` |
| `*.log` | Ignore files ending in `.log` |
| `!keep.log` | Do not ignore `keep.log` when it was excluded by an earlier pattern |

Patterns are evaluated relative to the `.gitignore` file that contains them. A `!` exception may not re-include a file if one of its parent directories is ignored.

## Important: already tracked files

`.gitignore` does not affect files already tracked by Git. To stop tracking a file while keeping the local copy:

```bash
git rm --cached <file>
```

Then commit the removal. If the file contains a password, key, or token, ignoring it is not enough: remove and rotate the exposed secret, and follow the project's process for addressing it in repository history.

## Find out why a file is ignored

**Command:** `git check-ignore -v <file>`  
**Purpose:** Shows the ignore rule and file that match a path.  
**Use when:** A file is not appearing in `git status` and you want to find out why.

```bash
git check-ignore -v path/to/file
```

GitHub maintains template `.gitignore` files for many languages and tools. Choose templates that fit the actual project instead of adding every possible rule.
