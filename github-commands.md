# GitHub Features

GitHub hosts Git repositories and provides collaboration tools. Many actions below are done in the GitHub website; Git commands handle local repository history and synchronization.

## Create a repository

On GitHub, choose **New repository**, enter a name, and select visibility. You can initialize it with a README, `.gitignore`, or license. If you already have local project files, avoid initializing the hosted repository with files that conflict with your local history; connect the repositories carefully.

## README files

A `README.md` explains what a repository is for and how to use it. GitHub renders Markdown on the repository home page. Useful sections include an overview, requirements, setup, usage, contribution guidance, and license.

## `.gitignore`

A `.gitignore` lists untracked files and paths Git should ignore, such as local settings, generated output, and caches. It does not stop tracking a file already committed. See [the `.gitignore` guide](gitignore.md).

## Issues

Issues track questions, bugs, tasks, and feature requests. Use a clear title and include enough context to reproduce a bug or understand a task. Labels, assignees, and milestones help organize work.

## Pull requests

A pull request (PR) proposes changes from one branch into another. It provides a place to review a diff, discuss changes, run checks, and merge the work. See [collaboration](collaboration.md) for a typical PR workflow.

## Forks

A fork is your GitHub-hosted copy of another user's repository. Forks are commonly used when you cannot push directly to the original project. You can clone your fork, make a branch, and open a PR back to the original repository.

## Stars and Watch

- **Star** a repository to bookmark or show appreciation for it. A star is not a formal endorsement or a subscription to every update.
- **Watch** a repository to control notifications about its activity. Choose notification settings that fit your needs.

## Discussions

GitHub Discussions provides a forum for questions, ideas, announcements, and community conversation. Use Issues for actionable bugs or work items and Discussions for open-ended conversation, following the project's own guidance.

## Releases

Releases present a version of a project, often associated with a Git tag. Maintainers can summarize changes and attach downloadable assets. Follow the project's versioning policy when creating releases.

## GitHub Pages

GitHub Pages can publish a website from a repository or a build workflow. Check repository and organization settings for available sources, supported configuration, and access restrictions.

## GitHub Actions

GitHub Actions runs automated workflows, commonly for tests, builds, and deployment. Workflow files are typically stored in `.github/workflows/`. Review third-party actions and workflow permissions before using them; never expose secrets in logs or commit them into workflow files.
