# Chapter 06: Estimation & Velocity

In traditional project management, we ask: *"How many hours will this take?"* In Agile, we know that humans are notoriously bad at estimating time. Instead, we use **Relative Estimation**. We don't ask how many hours a task takes; we ask how big it is compared to other tasks.

---

## 6.1 Why Hours Don't Work
Estimation in hours fails for three main reasons:
1.  **The Senior vs. Junior Gap:** A task that takes a Senior 2 hours might take a Junior 8 hours. Time is subjective.
2.  **Hidden Complexity:** We often forget about "non-coding" time (testing, CI/CD delays, meetings).
3.  **Psychological Pressure:** If you say "4 hours" and it takes 6, you feel like you failed, even if the work is high quality.

---

## 6.2 Story Points & Fibonacci
Agile teams use **Story Points** to measure effort. This is a combination of **Complexity, Risk, and Uncertainty**.

Most teams use the **Fibonacci Sequence** (1, 2, 3, 5, 8, 13...) for points. 
* **The Gap Matters:** The jump from 5 to 8 is larger than 2 to 3. This reflects the reality that as a task gets bigger, our uncertainty about it grows.
* **The "Too Big" Rule:** If a story is a 13 or 21, it’s usually considered an Epic and must be broken down into smaller pieces before it enters a sprint.



---

## 6.3 Planning Poker
To avoid "Anchoring Bias" (where everyone agrees with the first person who speaks), teams play **Planning Poker**:
1.  The PO describes a story.
2.  The team discusses technical requirements.
3.  Everyone picks a card (point value) in secret.
4.  Everyone reveals at the same time.
5.  **The Outliers Talk:** If one person says "2" and another says "13," they discuss why. Often, the "13" saw a hidden technical risk the "2" missed.

---

## 6.4 Velocity: The Team's Capacity
**Velocity** is the average number of Story Points a team completes in a single sprint. 
* **Example:** If you finished 20 points in Sprint 1, 24 in Sprint 2, and 22 in Sprint 3, your average velocity is **22**.
* **Predictive Power:** If the Product Owner has a 100-point backlog, and your velocity is 22, you can estimate it will take approximately 5 sprints to finish.



---

## 6.5 The "Estimation Is Not a Contract" Rule
Velocity and points are tools for **planning**, not for **judgment**. 
* Do not compare velocity between different teams. Team A's "5" is not the same as Team B's "5."
* Velocity should be used to stop the team from over-committing. If your velocity is 20, don't pull 40 points into the next sprint.

---

## 🛠 Hands-on: Pointing Your Chores
Think of three real-world tasks:
1.  Changing a lightbulb.
2.  Mowing the lawn.
3.  Fixing a leaky sink.

If "Changing a lightbulb" is a **1**, how many points are the others?
* Is mowing the lawn a **3** (takes more effort but is predictable)?
* Is fixing the sink an **8** (high uncertainty—you don't know what's behind the pipe)?

---

**Next Up:** Agile isn't just about how we manage work; it's about how we write code. In **Chapter 07: Technical Agile Practices**, we explore engineering-specific habits like TDD and Pair Programming.
