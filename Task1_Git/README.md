## Step 1: Initialize a Repository  

- **`git init`**  
  Initializes a new Git repository in the current directory.  
  ✅ *Use case*: Start version control for a new or existing project.  
  🔹 *Example*:  
  ```bash
  mkdir my-project
  cd my-project
  git init
  ```
  ---

## Step 2: Clone a Repository  

- **`git clone <repo-url>`**  
  Creates a local copy of a remote repository.  
  ✅ *Use case*: Work on an existing project stored on GitHub, GitLab, or another Git server.  
  🔹 *Example*:  
  ```bash
  git clone https://github.com/user/project.git
  ```

---

## Step 3: Check Repository Status  

- **`git status`**  
  Displays the state of the working directory and staging area.  
  ✅ *Use case*: See which files are untracked, modified, or staged for commit.  
  🔹 *Example Output*:  
  ```bash
  On branch main
  Untracked files:
    (use "git add <file>..." to include in what will be committed)
      newfile.txt
  nothing added to commit but untracked files present
  ```

---

## Step 4: Branching Commands  

- **`git branch`**  
  Lists all branches in the repository.  
  ✅ *Use case*: Check available branches and see which branch you are currently on.  
  🔹 *Example*:  
  ```bash
  git branch
  ```

- **`git branch <branch-name>`**  
  Creates a new branch.   
  ✅ Use case: Start a new feature or bugfix without affecting the main branch.   
  🔹 Example:
  ```
  git branch feature-login
  ```

- **`git checkout <branch-name>`**  
  Switches to the specified branch.  
  ✅ Use case: Move to another branch to work on specific tasks.  
  🔹 Example:
  ```
  git checkout feature-login
  ``` 
- **`git checkout -b <branch-name>`**  
  Creates and switches to a new branch in a single command.  
  ✅ Use case: Quickly start working on a new feature branch.  
  🔹 Example:  
  ```  
  git checkout -b feature-payment
  ```


## Step 5: Stage & Commit Changes  

- **`git add <file>`**  
  Stages a specific file for the next commit.  
  ✅ *Use case*: Add only the selected file to be included in the commit.  
  🔹 *Example*:  
  ```bash
  git add hello.txt
  ```

* **`git add .`**  
  Stages all modified and new files in the current directory.  
  ✅ *Use case*: Quickly stage all changes at once.  
  🔹 *Example*:

  ```bash
  git add .
  ```

* **`git commit -m "message"`**  
  Records the staged changes into Git history with a descriptive message.  
  ✅ *Use case*: Save a snapshot of your project with a clear description of what was changed.  
  🔹 *Example*:

  ```bash
  git commit -m "Added hello.txt with sample content"
  ```


## Step 6: Remote Repository Commands  

- **`git remote add origin <repo-url>`**  
  Links your local repository to a remote one (e.g., GitHub, GitLab).  
  ✅ *Use case*: Connect your local project to a remote repository for collaboration.  
  🔹 *Example*:  
  ```bash
  git remote add origin https://github.com/user/project.git
  ```

* **`git push origin <branch-name>`**  
  Uploads local branch commits to the remote repository.  
  ✅ *Use case*: Share your changes with the team or back them up remotely.   
  🔹 *Example*:

  ```bash
  git push origin main
  ```

* **`git pull origin <branch-name>`**   
  Fetches and merges changes from the remote branch into the current branch.    
  ✅ *Use case*: Sync your local repository with the latest remote changes.   
  🔹 *Example*:

  ```bash
  git pull origin main
  ```

* **`git fetch origin`**    
  Downloads changes from the remote without merging them.   
  ✅ *Use case*: Review remote changes before merging.    
  🔹 *Example*:

  ```bash
  git fetch origin
  ```


## Step 7: Merging & Rebasing  

- **`git merge <branch-name>`**  
  Combines changes from the specified branch into the current branch.  
  ✅ *Use case*: Integrate a completed feature branch into `main` or another branch.  
  🔹 *Example*:  
  ```bash
  git checkout main
  git merge feature-login
  ```

* **`git rebase <branch-name>`**  
  Reapplies commits from the current branch on top of another branch, creating a cleaner, linear history.   
  ✅ *Use case*: Keep project history tidy by avoiding unnecessary merge commits.   
  🔹 *Example*:

  ```bash
  git checkout feature-login
  git rebase main
  ```


## Step 8: Stash Commands  

- **`git stash`**  
  Temporarily saves uncommitted changes and cleans your working directory.  
  ✅ *Use case*: Switch branches without committing unfinished work.  
  🔹 *Example*:  
  ```bash
  git stash
  ```

* **`git stash list`**    
  Shows all stashed changes.    
  ✅ *Use case*: Review previously stashed work.    
  🔹 *Example*:

  ```bash
  git stash list
  ```

* **`git stash pop`**   
  Restores the most recently stashed changes and removes them from the stash list.    
  ✅ *Use case*: Retrieve your saved changes to continue working.   
  🔹 *Example*:

  ```bash
  git stash pop
  ```
