# Chapter 03: Branching & Merging

One of the most powerful features of Git is the ability to work in "parallel universes." In professional engineering, you never want to experiment on your working code directly. Instead, you create a **Branch**.

---

## 3.1 What is a Branch?
Think of a branch as a lightweight pointer to a specific commit. By default, every Git repository starts with a branch called `main` (or sometimes `master`). 

When you create a new branch, you are effectively "splitting" the timeline. You can make changes, commit them, and test them without affecting the `main` branch. This is essential for:
* Developing new features.
* Fixing bugs.
* Experimenting with risky code.



---

## 3.2 Navigating Branches
The core commands for managing these timelines are:

* **Create a branch:** `git branch <name>`
* **Switch to a branch:** `git checkout <name>` (or the modern `git switch <name>`)
* **Create and switch in one go:** `git checkout -b <name>`

While you are on a feature branch, `git log` will show different history than when you are on `main`.

---

## 3.3 Merging: Bringing it All Together
Once your work on a branch is finished and tested, you need to bring those changes back into the `main` branch. This is called **Merging**.

1.  **Switch to the target branch:** `git checkout main`
2.  **Merge the feature:** `git merge <feature-branch-name>`

Git will try to automatically combine the changes. If the changes were in different parts of the code, Git succeeds instantly (this is often called a **Fast-Forward** merge).

---

## 3.4 Handling Merge Conflicts
Sometimes, two branches change the **exact same line** in the same file. When you try to merge, Git gets confused and stops. This is a **Merge Conflict**.

When this happens, Git marks the file as "Unmerged." You must open the file and look for the conflict markers. They look like this:

- **Top Section:** Code currently on the Main branch.
- **Middle Divider:** A line of ======= signs.
- **Bottom Section:** The new code from the Feature branch you are trying to merge.

You manually delete the markers, choose the version of the code you want to keep, then `git add` the file and `git commit` to finish the merge.

---

## 🛠 Hands-on: Feature Branching
Let's simulate a real-world workflow:

1.  **Create a new branch:** `git checkout -b feature-idea`
2.  **Make a change:** `echo "New Experimental Feature" >> index.md`
3.  **Commit it:** `git commit -am "Add experimental feature"` 
4.  **Go back to main:** `git checkout main`
5.  **Observe:** Run `cat index.md`. Your new feature is gone! It only exists on the other branch.
6.  **Merge it:** `git merge feature-idea`
7.  **Confirm:** Run `cat index.md` again. The feature is now safely on the main branch.
8.  **Cleanup:** `git branch -d feature-idea` (Deletes the branch now that it's merged).

---

**Next Up:** Sometimes we make mistakes. In **Chapter 04: Git "Time Travel" (Undo)**, we will learn how to move backward in time to fix errors and recover lost work.
