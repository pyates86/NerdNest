# Chapter 09: Advanced Git (Rebase & Stash)

As you become more comfortable with the basic Git loop, you will encounter scenarios where your workflow feels clunky. Maybe your history is cluttered with "fixed typo" commits, or perhaps you need to switch branches but aren't ready to commit your current work. This is where **Rebase** and **Stash** come in.

---

## 9.1 Git Stash: The "Pause" Button
Imagine you are mid-way through a complex feature on the `new-ui` branch, and a critical bug is found on `main`. You need to switch branches immediately, but Git won't let you because you have uncommitted changes.

You don't want to make a "half-finished" commit just to switch branches. Instead, you **Stash**.

* **Stash your work:** `git stash` (This takes your uncommitted changes and puts them in a temporary storage area, leaving your working directory clean).
* **Switch and fix:** You can now `git checkout main`, fix the bug, and commit.
* **Retrieve your work:** Switch back to `new-ui` and run `git stash pop`. Your work-in-progress returns exactly as it was.

---

## 9.2 Git Rebase: Cleaning Up History
Merging is great, but it creates "merge commits" that can make the project history look like a tangled web. **Rebase** is an alternative way to integrate changes from one branch into another.

* **The Concept:** Instead of "merging" the two branches, Rebase takes your commits and "re-plays" them on top of the latest commit of the target branch.
* **The Result:** A perfectly linear project history without unnecessary merge commits.



### The Golden Rule of Rebase:
**Never rebase commits that you have already pushed to a public repository.** Rebase rewrites history (it changes the Commit IDs). If others are working on those same commits, it will break their local repositories.

---

## 9.3 Interactive Rebase (Squashing)
If you have a string of messy commits like "fixed typo," "fixed typo again," and "actually fixed typo," you can use an **Interactive Rebase** to "Squash" them into a single, clean commit.

* **Command:** `git rebase -i HEAD~3` (This opens an editor for the last 3 commits).
* You can change the word `pick` to `squash` for the commits you want to combine.

---

## 9.4 Cherry-Picking
Sometimes you only want a *specific* commit from another branch without merging the entire thing. This is called **Cherry-Picking**.

* **Command:** `git cherry-pick <commit-ID>`
* Git applies only the changes from that specific commit to your current branch.

---

## 🛠 Hands-on: Using the Stash
1. **Modify a file:** Open `index.md` and add some "work in progress" text.
2. **Try to switch:** Try `git checkout main`. If you have local changes, Git might block you.
3. **Stash it:** Run `git stash`. Your changes disappear from the file.
4. **List stashes:** Run `git stash list`.
5. **Pop it:** Run `git stash pop`. Your "work in progress" text reappears!

---

**Next Up:** We've mastered the manual tools. Now it's time to let the machines do the work. In **Chapter 10: GitHub Automations**, we will explore how to use GitHub Actions to automate your repetitive tasks.
