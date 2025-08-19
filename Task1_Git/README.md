# DevOps Intern Task - Git Commands

This repository is part of my DevOps internship, demonstrating basic Git commands.

# Useful Git Commands with Use Cases

Git is a powerful version control system used to track changes in code. Below is a list of the most useful Git commands along with their use cases.

## Basic Commands
- **git init**: Initializes a new Git repository.
  - Use case: Start version control for a new project.

- **git clone <repo-url>**: Copies a remote repository to your local machine.
  - Use case: Download a team’s repository from GitHub to work on it locally.

- **git status**: Shows the current status of the working directory (staged, unstaged, or untracked files).
  - Use case: Check which files are modified or ready for commit.

## Branching Commands
- **git branch**: Lists all branches in the repository.
  - Use case: View available branches and identify the current branch.

- **git branch <branch-name>**: Creates a new branch.
  - Use case: Create a separate branch for developing a new feature without affecting the main codebase.

- **git checkout <branch-name>**: Switches to the specified branch.
  - Use case: Move to a different branch to work on specific tasks.

- **git checkout -b <branch-name>**: Creates and switches to a new branch in one command.
  - Use case: Quickly start working on a new feature branch.

## Committing Changes
- **git add <file> or git add .**: Stages changes for the next commit.
  - Use case: Prepare modified files to be committed.

- **git commit -m "message"**: Commits staged changes with a descriptive message.
  - Use case: Save changes to the repository with a note about what was done.

- **git log**: Displays the commit history.
  - Use case: Review past commits, including their hashes and messages.

## Remote Repository Commands
- **git remote add origin <repo-url>**: Links a local repository to a remote one.
  - Use case: Connect your local repo to a GitHub repository.

- **git push origin <branch-name>**: Pushes local changes to the specified remote branch.
  - Use case: Upload your code to GitHub for collaboration or backup.

- **git pull origin <branch-name>**: Fetches and merges changes from the remote branch.
  - Use case: Sync your local repository with the latest changes from the team.

## Merging and Rebasing
- **git merge <branch-name>**: Merges changes from the specified branch into the current branch.
  - Use case: Integrate a feature branch into the main branch.

- **git rebase <branch-name>**: Reapplies your commits on top of another branch for a linear history.
  - Use case: Keep a clean commit history by avoiding merge commits.

## Other Useful Commands
- **git stash**: Temporarily saves uncommitted changes.
  - Use case: Store changes temporarily to switch branches without committing.

- **git stash pop**: Restores the most recently stashed changes.
  - Use case: Retrieve saved changes to continue working.

- **git reset --hard <commit-hash>**: Resets the branch to a specific commit, discarding later changes.
  - Use case: Undo unwanted commits (use with caution as it deletes changes).

- **git diff**: Shows differences between modified files and the last commit.
  - Use case: Review what has changed in your files before committing.

These commands cover essential Git workflows. For more details, refer to the official Git documentation.

this is to check puch gha