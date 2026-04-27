# Chapter 06: Collaborative Pull Requests

In a professional environment, no one pushes code directly to the `main` branch of a shared repository. Doing so would risk introducing bugs or breaking the production environment. Instead, teams use a workflow centered around the **Pull Request (PR)**.

---

## 6.1 What is a Pull Request?
A Pull Request is not a Git command, but a feature of platforms like GitHub. It is a formal way to say: *"I have finished a feature on this branch. I would like you to review my changes and, if they are good, 'pull' them into the main project."*

### The PR Lifecycle:
1. **Branch:** You create a local feature branch and push it to GitHub.
2. **Open:** You open a Pull Request on GitHub, comparing your feature branch to the `main` branch.
3. **Review:** Teammates look at your code, leave comments, and suggest changes.
4. **Update:** You make any necessary fixes and push them to the same branch (the PR updates automatically).
5. **Merge:** Once approved, the code is merged into `main`, and the feature branch is deleted.



---

## 6.2 The Power of Code Review
Code reviews are the "secret sauce" of high-quality software. They serve three main purposes:
* **Bug Detection:** Another set of eyes can catch logic errors you missed.
* **Knowledge Sharing:** Junior developers learn from senior reviews, and vice-versa.
* **Consistency:** Ensuring the code follows the team's style and architectural standards.

---

## 6.3 Best Practices for PRs
A "Good" Pull Request makes life easier for your reviewers.
* **Keep it Small:** A PR that changes 50 lines is easy to review; a PR that changes 2,000 lines is impossible.
* **Write a Clear Description:** Explain *what* you changed and *why*.
* **Link to Issues:** If your code fixes a specific bug, mention the issue number (e.g., "Closes #42").

---

## 6.4 Syncing with Upstream
While you are working on your feature branch, other people might be merging their own PRs into `main`. Your local copy of `main` will become outdated.

Before you merge your own work, you should:
1. Switch to main: `git checkout main`
2. Get the latest changes: `git pull origin main`
3. Switch back to your feature: `git checkout my-feature`
4. Merge main into your feature: `git merge main` (This ensures your feature works with the newest code).

---

## 🛠 Hands-on: Opening a PR
1. **Create a branch:** `git checkout -b readme-update`
2. **Edit a file:** Add your name or a bio to your `README.md`.
3. **Commit and Push:** `git commit -am "Update README with bio"`
   `git push origin readme-update`
4. **Go to GitHub:** You will see a yellow bar saying "Compare & pull request." Click it.
5. **Create:** Add a title and description, then click "Create pull request."
6. **Merge:** Since you own the repo, you can click "Merge pull request" yourself to see the change appear in the main project history.

---

**Next Up:** Pull Requests are great for teams you belong to. But what if you want to contribute to a project you don't have access to? In **Chapter 07: Open Source & Forking**, we will learn the community-standard way to contribute to millions of public projects.
