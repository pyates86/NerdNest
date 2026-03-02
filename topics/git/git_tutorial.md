# Git Version Control Tutorial 

Below is a concise, beginner-friendly tutorial on using the **Git version control system** for software engineers. This guide covers the essentials of Git, from setup to common workflows, with practical examples tailored for collaborative software development. It assumes basic familiarity with the command line and focuses on real-world use cases.


## What is Git?

Git is a distributed version control system that tracks changes to source code, enabling multiple developers to collaborate on a project. It records snapshots of your project (called commits), allows branching for parallel development, and supports merging changes. Git is widely used in software engineering for its speed, flexibility, and robust collaboration features.


## Tutorial Goals

By the end of this tutorial, you’ll know how to:

* Install and configure Git.  
* Initialize and manage a Git repository.  
* Create, track, and commit changes.  
* Use branches for feature development.  
* Collaborate with others using remote repositories (e.g., GitHub).  
* Resolve merge conflicts.  
* Follow best practices for Git workflows.


## Prerequisites

* A computer with a command-line interface.  
* A code editor (e.g., VS Code).  
* (Optional) A GitHub, GitLab, or Bitbucket account for remote repositories.


## Step 1: Install and Configure Git

* **Install Git**:  
  * **Windows/macOS**: Download from [git-scm.com](https://git-scm.com) and follow the installer instructions.  
  * **Linux**: Install via package manager (e.g., `sudo apt install git for Ubuntu`).  
  * Verify installation: `git --version` (should output something like `git version 2.39.2`).  
* **Configure Git**: 

Set your name and email, which Git attaches to your commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Optionally, set your default editor for commit messages:

```bash
git config --global core.editor "code --wait"  # For VS Code
```

Check your configuration:

```bash
git config --list
```

## Step 2: Initialize a Git Repository

**Create a Project Directory**:

```bash
mkdir my-project
cd my-project
```

**Initialize a Git Repository**: Initialize an empty Git repository in the directory:

```bash
git init
```

This creates a hidden `.git` folder to store version history.

* **Verify Initialization**: 

Check the repository status:

```bash
git status
```

Output should show an empty repository with no files tracked.


## Step 3: Track and Commit Changes

* **Create a File**: 

Create a sample file, e.g., `index.py`:

```bash
echo "print('Hello, Git!')" > index.py
```

* **Check Status**:

```bash
git status
```


Output shows `index.py` as an untracked file.

* **Stage the File**:   
  Add `index.py` to the staging area (preparing it for a commit):

```bash
git add index.py
```


Or stage all files:

```bash
git add .
```

* **Commit the Changes**: 

Save the staged changes as a commit with a descriptive message:

```bash
git commit -m "Initial commit: Add index.py with hello world"
```

The `-m` flag specifies the commit message.

* **View Commit History**: 

Check the commit log:

```bash
git log
```

Output shows the commit with its hash, author, date, and message. Use `git log --oneline` for a compact view.


## Step 4: Work with Branches

Branches allow parallel development, e.g., for new features or bug fixes, without affecting the main codebase.

**List Branches**:

```bash
git branch
```

The default branch is usually `main` (or `master` in older setups).

* **Create a New Branch**: 

Create a branch for a new feature:

```bash
git branch feature-hello
```

* **Switch to the Branch**:

```bash
git checkout feature-hello
```

Or combine creation and switching:

```bash
git checkout -b feature-hello
```

* **Make Changes**:

Edit `index.py` to add a new line:

```py
print('Hello, Git!')
print('This is a new feature.')
```

Stage and commit the changes:

```bash
git add index.py
git commit -m "Add new print statement in feature-hello"
```

* **Merge the Branch**: 

Switch back to the main branch:

```bash
git checkout main
```

Merge the feature branch into `main`:

```bash
git merge feature-hello
```

If there are no conflicts, Git updates `main` with the changes.

* **Delete the Branch** (Optional): 

After merging, delete the feature branch:

```bash
git branch -d feature-hello
```

## Step 5: Collaborate with Remote Repositories

Remote repositories (e.g., on GitHub) enable team collaboration and backups.

* **Create a Remote Repository**:  
  * On GitHub, create a new repository (e.g., `my-project`).  
  * Copy the repository URL (e.g., [https://github.com/your-username/my-project.git](https://github.com/your-username/my-project.git) ).  
* **Link Local Repository to Remote**: 

Add the remote repository:

```bash
git remote add origin https://github.com/your-username/my-project.git
```

Verify the remote:

```bash
git remote -v
```

* **Push Changes to Remote**: 

Push the `main` branch to GitHub:

```bash
git push -u origin main
```

The `-u` flag sets `origin main` as the default upstream branch.

* **Clone a Repository** (For Team Members): 

To work on an existing project, clone it:

```bash
git clone https://github.com/your-username/my-project.git
cd my-project
```

* **Pull Changes**: 

To sync with the latest changes from the remote:

```bash
git pull origin main
```

## Step 6: Handle Merge Conflicts

Merge conflicts occur when Git can’t automatically reconcile changes (e.g., two developers edit the same line).

* **Simulate a Conflict**:  
  * On `main`, edit `index.py`:

```py
print('Hello from main!')
```

Commit and push:

```bash
git add index.py
git commit -m "Update greeting on main"
git push origin main
```

* On `feature-hello`, edit the same line differently:

```py
print('Hello from feature!')
```

Commit:

```bash
git add index.py
git commit -m "Update greeting on feature-hello"
```

* **Attempt to Merge**: 

Switch to `main` and merge `feature-hello`:

```bash
git checkout main
git merge feature-hello
```

Git will report a conflict in `index.py`.

**Resolve the Conflict:
 
Open** `index.py`**, which will show conflict 

markers: 

\`\`\`python 

\<\<\<\<\<\<\< HEAD 

print('Hello from main\!')**  

print('Hello from feature\!')

*feature-hello*

```bash
Edit to keep the desired version or combine changes:
28
print('Hello from both branches!')
```

Stage and commit the resolved file:

```bash
git add index.py
git commit -m "Resolve merge conflict"
```

**Push the Changes**:

```bash
git push origin main
```

## Step 7: Best Practices for Git Workflows

* **Write Clear Commit Messages**:  
  * Use concise, descriptive messages (e.g., "Fix login bug in auth module").  
  * Follow a convention: `<type>(<scope>): <description>` (e.g., `feat(ui): add dark mode toggle`).  
* **Commit Frequently, but Logically**:  
  * Commit related changes together (e.g., one commit per feature or fix).  
  * Avoid committing large, unrelated changes in one go.  
* **Use Feature Branches**:  
  * Create a new branch for each feature, bug fix, or experiment.  
  * Keep `main` stable and production-ready.  
* **Pull and Push Regularly**:  
  * Pull changes before starting work to avoid conflicts.  
  * Push your branch to the remote for backups and collaboration.  
* **Review Code**:  
  * Use pull requests (PRs) on GitHub/GitLab for team reviews before merging.  
  * Address feedback and test thoroughly.  
* **Keep the Repository Clean**:  
  * Delete merged branches.  
  * Avoid committing large binary files or sensitive data (use `.gitignore`).  
* **Use .gitignore**:   
  Create a `.gitignore` file to exclude files like:

```bash
node_modules/
*.log
.env
```


Find templates at [gitignore.io](https://www.gitignore.io).


## Step 8: Useful Git Commands

* **Undo Changes**:  
  * Discard untracked files: `git clean -fd`  
  * Discard staged changes: `git restore <file>`  
  * Revert to last commit: `git reset --hard`  
* **View Differences**:  
  * Changes in working directory: `git diff`  
  * Staged changes: `git diff --cached`  
* **Stash Changes**:  
  * Save uncommitted changes: `git stash`  
  * Restore stashed changes: `git stash pop`  
* **Revert a Commit**:  
  * Undo a commit: `git revert <commit-hash>`  
* **Cherry-Pick**:  
  * Apply a specific commit to another branch:

```bash
git cherry-pick <commit-hash>
```

## Step 9: Collaborate Using Pull Requests

* **Push a Feature Branch**:

```bash
git push origin feature-hello
```


* **Create a Pull Request**:  
  * On GitHub, navigate to your repository and click “New Pull Request.”  
  * Select `feature-hello` as the source branch and `main` as the target.  
  * Add a description and request reviewers.  
      
* **Review and Merge**:  
  * Team members review the PR, comment, and suggest changes.  
  * Once approved, merge the PR into `main` (optionally delete the feature branch).  
      
* **Sync Local Repository**: After the PR is merged, update your local `main`:

```bash
git checkout main
git pull origin main
```


  ---

**Step 10: Advanced Tips**

* **Rebase for Cleaner History**:  
  * Rebase a feature branch onto `main` to avoid merge commits:

```bash
git checkout feature-hello
git rebase main
```

    

  * Resolve conflicts if any, then force-push:

```bash
git push --force
```


* **Squash Commits**:  
  * Combine multiple commits into one for a cleaner history:

```bash
git rebase -i main
```

    

Change `pick` to `squash` for commits to combine, then edit the commit message.

* **Use Tags for Releases**:  
  * Tag a commit for a release:

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
git push origin v1.0.0
```


* **Bisect for Bug Hunting**:  
  * Find the commit that introduced a bug:

```bash
git bisect start
git bisect bad  # Current state is broken
git bisect good <commit-hash>  # Known good commit
```

Git checks out commits until you identify the faulty one.


## Resources

* **Official Git Documentation**: [git-scm.com/doc](https://git-scm.com/doc)  
* **Interactive Git Tutorial**: [learngitbranching.js.org](https://learngitbranching.js.org)  
* **GitHub Guides**: [guides.github.com](https://guides.github.com)  
* **Pro Git Book**: Free at [git-scm.com/book](https://git-scm.com/book)


## Practice Exercise

* Create a new repository and initialize it with a `README.md`.  
* Commit the initial `README.md`.  
* Create a branch `add-feature` and add a file `app.js` with a simple function.  
* Commit and merge the branch into `main`.  
* Push to a remote repository on GitHub.  
* Simulate a merge conflict by editing the same line in two branches, then resolve it.  
* Create a pull request for a new feature and merge it.

  ---

This tutorial covers the core Git workflows for software engineers. Practice these steps in a test repository to build confidence.
