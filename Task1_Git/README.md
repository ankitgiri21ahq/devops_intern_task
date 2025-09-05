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