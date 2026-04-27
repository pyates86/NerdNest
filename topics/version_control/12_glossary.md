# Chapter 12: Version Control Glossary

In the world of Version Control, engineers use specific jargon to describe complex states and actions. This glossary serves as a quick-reference guide to the most common terms you will encounter in documentation, terminal output, and technical interviews.

---

## 12.1 Core Git Concepts

* **Repository (Repo):** The project folder tracked by Git, containing all files, history, and configuration.
* **Commit:** A "snapshot" of your project at a specific point in time. Each commit has a unique ID (SHA).
* **HEAD:** A pointer to your current location in the Git history. Usually, it points to the latest commit on your active branch.
* **SHA (Hash):** A unique 40-character string (e.g., `1a2b3c4d...`) that identifies a specific commit.
* **Staging Area (Index):** The "waiting room" where changes live after you `git add` them, but before you `git commit` them.

---

## 12.2 Branching & Merging

* **Branch:** A parallel version of the repository. It allows you to work on different features simultaneously without affecting the `main` code.
* **Master / Main:** The default primary branch in a repository, typically representing the "stable" or "production" version of the code.
* **Merge:** The process of joining two or more development histories (branches) together.
* **Merge Conflict:** A state where Git cannot automatically combine changes because two different commits modified the exact same line of code.
* **Fast-Forward:** A type of merge that occurs when the target branch has no new commits since you branched off, allowing Git to simply move the pointer forward.

---

## 12.3 Remote & Collaboration

* **Remote:** A version of your repository hosted on the internet or a network (e.g., on GitHub).
* **Origin:** The default name Git gives to the primary remote repository you connected to.
* **Upstream:** In the context of forking, this refers to the original repository from which you created your fork.
* **Clone:** Creating a local copy of a remote repository on your computer.
* **Push:** Sending your local commits to a remote repository.
* **Pull:** Fetching changes from a remote repository and immediately merging them into your current branch.
* **Pull Request (PR):** A feature of platforms like GitHub that allows you to propose changes to a repository and request a review.

---

## 12.4 Advanced States

* **Detached HEAD:** A state where your `HEAD` pointer is pointing to a specific commit instead of a branch. Changes made in this state are easily lost if not saved to a new branch.
* **Rebase:** The process of moving or combining a sequence of commits to a new base commit, creating a linear history.
* **Squash:** The act of combining multiple commits into a single one (usually during a rebase) to clean up project history.
* **Cherry-pick:** Applying the changes introduced by a specific commit from one branch onto another.
* **Gitignore:** A text file (`.gitignore`) that tells Git which files or directories to ignore (e.g., `node_modules`, `.env`, or log files).

---

## 🛠 Hands-on: Checking Your Config
Now that you know the language, take a look at your own Git configuration to see where these terms live:

1.  **List all configs:** `git config --list`
2.  **Identify your remotes:** `git remote -v`
3.  **Check your current HEAD:** `cat .git/HEAD`

---

**Congratulations!** You have completed the **Version Control & Collaboration** track. You are now equipped with the tools and knowledge to manage code professionally, collaborate on global teams, and contribute to the future of software.
