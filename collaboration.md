# Collaboration Workflow

This is a common contribution flow when working through a fork. A project may use a different branch naming, review, or commit policy; follow its contribution guide.

## Fork → Clone → Branch → Commit → Push → Pull Request

1. **Fork** the repository on GitHub if you do not have permission to create a branch in the original repository.
2. **Clone** your fork:

   ```bash
   git clone https://github.com/YOUR-USERNAME/REPOSITORY.git
   cd REPOSITORY
   ```

3. **Create a branch** for one feature or fix:

   ```bash
   git switch -c fix-description
   ```

4. **Edit, review, stage, and commit** your work:

   ```bash
   git status
   git diff
   git add <file>
   git diff --staged
   git commit -m "Describe the change"
   ```

5. **Push** the branch to your fork:

   ```bash
   git push -u origin fix-description
   ```

6. **Open a pull request** on GitHub from your branch to the intended base branch. Describe the change, link related issues when appropriate, and respond to review feedback.

## Pull request workflow

- Keep the PR focused and explain why the change is useful.
- Review the PR diff yourself before requesting review.
- Run relevant checks and mention anything that could not be tested.
- Address feedback with additional commits or the project's preferred update method.
- Merge only after the required checks and approvals are complete.

## Keep a fork updated

Add the original repository as an `upstream` remote once:

```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/REPOSITORY.git
```

Confirm the remotes:

```bash
git remote -v
```

Fetch changes from the original repository and integrate them into your local default branch:

```bash
git fetch upstream
git switch main
git merge upstream/main
git push origin main
```

Replace `main` if the project uses a different default branch. If the branches have conflicting changes, resolve them as described in [merging](merging.md).

## Good collaboration habits

- Pull or fetch recent changes before starting work.
- Use descriptive branch names and commit messages.
- Avoid committing generated files or local secrets.
- Ask before force-pushing or rewriting history on a shared branch.
- Communicate early when a conflict or blocked change affects others.
