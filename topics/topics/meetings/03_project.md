# Chapter 03: Project & Execution Meetings

Project and Execution meetings are the "heartbeat" of an Agile team. These are high-frequency, structured sessions designed to keep the development cycle moving, remove blockers, and ensure that the "Definition of Done" is being met. In these meetings, we optimize for **velocity and clarity**.

---

## 3.1 The Daily Stand-up (The Pulse)
The Stand-up is a 15-minute synchronization point. It is not a status report for the manager; it is a huddle for the developers.

* **The Format:** Each node (engineer) reports on:
    1.  What did I complete since the last sync?
    2.  What will I complete before the next sync?
    3.  What is blocking my progress?
* **The Anti-Pattern:** Turning the stand-up into a technical deep-dive. If an issue requires more than 60 seconds of discussion, move it to a "Parking Lot" session immediately following the stand-up.

---

## 3.2 Sprint Planning (The Roadmap)
This is where the team commits to a "Batch" of work. The goal is to align the team’s capacity with the Product Owner's priorities.

* **The Goal:** Define the **Sprint Goal** (the "Why") and the **Sprint Backlog** (the "What").
* **The Engineer's Role:** To provide "Reality Checks" on technical complexity. If a task is too vague to estimate, it isn't ready for the sprint.

---

## 3.3 Backlog Refinement / Grooming (The Prep)
Refinement is the "Preprocessing" stage. We look at future tasks and ensure they are "Ready for Dev."

* **Story Pointing:** Using relative estimation (like Fibonacci numbers) to gauge effort.
* **Decomposition:** If a user story is too large (an "Epic"), we break it down into smaller, testable units.
* **Clarification:** Defining "Acceptance Criteria" so there is no ambiguity when an engineer starts coding.

---

## 3.4 The Sprint Demo / Review (The Output)
This is the "Validation" phase. The team presents "Shippable Code" to stakeholders.

* **Show, Don't Tell:** Avoid PowerPoint slides. Show the actual software running in a staging environment.
* **Feedback Loop:** This is the primary point where business stakeholders provide input on the direction of the product.
* **Celebrate Wins:** It serves as a psychological "Commit" point for the team to acknowledge what they built.

---

## 3.5 The "Am I Needed?" Filter
Project meetings can quickly become bloated. Use the following logic to keep execution lean:
* **Stand-ups:** Mandatory for the active dev team.
* **Refinement:** Essential for the engineers who will likely work on those specific features.
* **Planning:** Mandatory to ensure collective commitment.

---

## 🛠 Hands-on: The "Blocker" Challenge
In your next Stand-up, focus specifically on the "Blocker" section:
1.  **Be Specific:** Instead of "I'm stuck on the API," say "I'm blocked by a 403 error on the Auth endpoint that I can't reproduce locally."
2.  **Request a "Sidebar":** Immediately follow up with: *"Does anyone have 5 minutes after this to help me debug?"*
3.  **Observe:** Notice how much faster the "System" resolves the error when the request is specific and targeted.

---

**Next Up:** While project meetings focus on the *work*, we also need to focus on the *people* doing the work. In **Chapter 04: Team Health & Syncs**, we will look at Retrospectives and Chapter meetings.
