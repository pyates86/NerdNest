# Chapter 02: Git Essentials: The Lifecycle

Understanding Git isn't just about memorizing commands; it’s about understanding the **state** of your files. Unlike other backup systems, Git doesn't just watch your files; it requires you to intentionally move them through a specific lifecycle.

---

## 2.1 The Three States
A Git project consists of three main "areas" where your code can live. Navigating these areas is the heart of the Git workflow.

1.  **The Working Directory:** This is your actual project folder on your computer. When you edit a file, the changes exist here first.
2.  **The Staging Area (Index):** This is a middle ground. You "add" changes here to prepare them for a snapshot. It allows you to choose exactly which changes to include in your next version.
3.  **The Git Directory (Repository):** This is where Git stores the compressed snapshots (commits) permanently. Once a change is here, it is part of the project's history.



---

## 2.2 Initializing a Repository
To start tracking a project with Git, you must turn a standard folder into a **Git Repository**.

1. Create a new folder: `mkdir my-first-repo && cd my-first-repo`
2. Initialize Git: `git init`

This creates a hidden `.git` folder. **Do not delete or modify this folder**; it contains the entire history and logic of your version control for this project.

---

## 2.3 The Core Workflow: Add and Commit
The process of saving your work follows a simple loop:

### Step 1: Check the Status
`git status` is the most important command in Git. It tells you which files have been modified and where they sit in the lifecycle.

### Step 2: Stage Your Changes
When you are happy with a change, move it from the Working Directory to the Staging Area:
`git add <filename>` (or `git add .` to stage all changes).

### Step 3: Commit
A **Commit** is a permanent snapshot of your staged changes. Every commit requires a **message** that explains *why* the change was made.
`git commit -m "Add initial project structure"`

---

## 2.4 Identifying Yourself
Before your first commit, Git needs to know who you are so it can attribute the work to you. Set your global config:

* `git config --global user.name "Your Name"`
* `git config --global user.email "you@example.com"`

---

## 🛠 Hands-on: Your First Snapshot
Let's put the lifecycle into practice:

1.  **Create a file:** `echo "Hello Git" > index.md`
2.  **Check status:** `git status` (The file will be "Untracked" in red).
3.  **Stage it:** `git add index.md`
4.  **Check status:** `git status` (The file will be "Changes to be committed" in green).
5.  **Commit it:** `git commit -m "Create index file"`
6.  **View History:** `git log` (You will see your commit, the author, the date, and a unique ID called a **SHA**).

---

**Next Up:** In **Chapter 03: Branching & Merging**, we will learn how to create "parallel timelines" so you can work on new features without touching your stable code.
