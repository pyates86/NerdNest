# Chapter 07: Technical Agile Practices

Agile is not just a management strategy; it is an engineering discipline. You can have the most organized Jira board in the world, but if your codebase is a "spaghetti" mess that breaks every time you push, you aren't truly Agile. This chapter focuses on the technical habits—often derived from **Extreme Programming (XP)**—that allow code to change as quickly as the requirements do.

---

## 7.1 Test-Driven Development (TDD)
In TDD, you write the test *before* you write the functional code. This follows the **Red-Green-Refactor** cycle:
1.  **Red:** Write a small test for a new feature and watch it fail.
2.  **Green:** Write just enough code to make the test pass.
3.  **Refactor:** Clean up the code while ensuring the test stays green.

**Why it matters:** TDD ensures you have a safety net of tests from day one, making it safe to change or "refactor" the code later without fear of breaking everything.



---

## 7.2 Pair Programming
Two developers, one workstation.
* **The Driver:** The person typing the code, focused on the immediate syntax and implementation.
* **The Navigator:** The person reviewing the code in real-time, focused on the "big picture," edge cases, and architectural alignment.

**Why it matters:** It drastically reduces bugs, facilitates instant knowledge sharing, and leads to higher-quality solutions that "two heads" agreed upon.

---

## 7.3 Continuous Integration (CI)
CI is the practice of merging all developer working copies to a shared mainline several times a day.
* **Automated Builds:** Every time you push code, a server automatically builds the app.
* **Automated Testing:** The server runs your entire test suite. If any test fails, the build "breaks," and the team is notified immediately.

**Why it matters:** It prevents "Integration Hell"—the nightmare scenario where developers spend weeks trying to merge their separate branches at the end of a project.



---

## 7.4 Simple Design & Refactoring
Agile engineers follow the **YAGNI** principle: *"You Ain't Gonna Need It."* * Don't build complex abstractions for features that *might* be requested next year. 
* Build the simplest thing that works today, and **Refactor** (improve the internal structure of the code without changing its external behavior) as the requirements evolve.

---

## 7.5 Collective Code Ownership
In an Agile team, no one "owns" a specific file or module. Anyone can change any part of the system to complete a user story.
* **Peer Reviews:** Using Pull Requests (PRs) ensures that at least two sets of eyes have seen every line of code.
* **Standards:** The team agrees on a shared coding style (linting) so the code looks like it was written by one person.

---

## 🛠 Hands-on: The "Red-Green" Exercise
Try this on your next simple function:
1.  **Write the test first:** If you're building a `sum(a, b)` function, write a test that expects `sum(2, 2)` to be `4`.
2.  **Run the test:** Watch it fail (because the function doesn't exist yet).
3.  **Write the code:** Create the function.
4.  **Run the test again:** Feel the satisfaction of seeing it turn green.
5.  **Refactor:** Can you make the code cleaner? If you do, run the test again to prove you didn't break it.

---

**Next Up:** Now that we understand the philosophy, mechanics, and technical habits, it's time to master the tool where it all lives. In **Chapter 08: Jira Mastery for Devs**, we learn how to use the "IDE of Project Management."
