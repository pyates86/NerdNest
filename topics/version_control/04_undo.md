# Chapter 04: Git "Time Travel" (Undo)

In the world of coding, mistakes are inevitable. You might delete a critical file, break a feature that was working yesterday, or realize a commit was a bad idea. Git is designed to be a "safety net," allowing you to move backward in time to recover your work.

---

## 4.1 The Different Levels of "Undo"
Because Git has a three-stage lifecycle (Working Directory, Staging Area, Repository), there are different ways to undo changes depending on where they are.

### 1. Discarding Local Changes (Working Directory)
If you edited a file but haven't staged it yet and want to throw those changes away:
`git checkout -- <filename>`
*(Note: In modern Git, you can also use `git restore <filename>`)*.

### 2. Unstaging a File (Staging Area)
If you ran `git add` but realized you aren't ready to commit that file yet:
`git reset HEAD <filename>`
*(Note: This keeps your code changes but moves the file out of the "Staging Area" back to the "Working Directory")*.

---

## 4.2 Reverting History (The Safe Way)
If you have already committed a change and realize it’s a mistake, you can use **`git revert`**.

* **Command:** `git revert <commit-ID>`
* **Effect:** Git creates a *new* commit that does the exact opposite of the target commit. 
* **Why use it?** It is "non-destructive." It doesn't delete the history of your mistake; it just records a fix. This is the safest method when working on a team.

---

## 4.3 Resetting History (The Dangerous Way)
**`git reset`** is a more powerful and destructive tool. It literally moves the branch pointer back to a previous commit, acting as if the subsequent commits never happened.

* **Soft Reset:** `git reset --soft <commit-ID>`
  * Moves history back, but keeps your work in the Staging Area.
* **Hard Reset:** `git reset --hard <commit-ID>`
  * **WARNING:** This deletes all changes made after that commit. Your working directory is wiped clean to match the old state. Use this with extreme caution.

---

## 4.4 Recovering the "Unrecoverable" with Reflog
Have you ever done a "Hard Reset" and realized you deleted something you actually needed? Git keeps a secret log of every time your `HEAD` pointer moves.

* **Command:** `git reflog`
* This shows a list of every action you've taken. Even if a commit is no longer on a branch, you can find its ID here and use `git reset --hard <ID>` to bring it back from the dead.

---

## 🛠 Hands-on: Fixing a Mistake
Let's practice a safe recovery:

1.  **Make a "bad" change:** `echo "This is a bug" >> index.md`
2.  **Commit it:** `git commit -am "Add a bug"`
3.  **Realize the error:** Look at your log with `git log --oneline`.
4.  **Revert it:** `git revert HEAD` (This reverts the last commit).
5.  **Check the result:** Run `cat index.md`. The bug line is gone, and `git log` shows a new "Revert" commit.

---

**Next Up:** Everything we have done so far has stayed on our local computer. In **Chapter 05: GitHub & Remote Work**, we will learn how to connect our local code to the cloud and share it with the world.
