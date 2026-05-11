# Chapter 09: Advanced Jira & Reporting

In an Agile environment, data is the "Telemetry" of the team. Leaders and stakeholders don't look at your code to see if a project is healthy; they look at **Jira Reports**. Understanding these charts allows you to have data-driven conversations about deadlines, scope creep, and team burnout.

---

## 9.1 The Burndown Chart
The Burndown Chart is the most common report used during a Scrum sprint. It tracks the total work remaining against the time available in the sprint.

* **The Ideal Line:** A straight diagonal line from the start of the sprint to zero at the end.
* **The Actual Line:** Your team's real-time progress.
* **Reading the Data:** * If the actual line is **above** the ideal line, the team is "behind" and may not finish all committed stories.
    * If the line is **below**, the team is ahead of schedule.
    * Flat lines indicate "Blockers" or a lack of progress.



---

## 9.2 Velocity Report
As discussed in Chapter 06, Velocity tracks the amount of work a team completes sprint-over-sprint.

* **Commitment vs. Achievement:** Jira shows two bars for every sprint—what the team *said* they would do and what they *actually* finished.
* **Stability:** A "bumpy" velocity (e.g., 10 points, then 40, then 5) suggests the team is struggling with estimation or constant interruptions. A stable velocity (e.g., 22, 24, 21) makes the team highly predictable.

---

## 9.3 Cumulative Flow Diagram (CFD)
Commonly used in Kanban, the CFD shows the distribution of issues across various statuses over time. It is the best tool for identifying **Bottlenecks**.

* **Widening Bands:** If the "In Progress" or "Testing" band is getting wider, work is piling up faster than it can be finished.
* **Narrowing Bands:** The team is clearing the backlog effectively.
* **The Goal:** A smooth, upward-sloping set of bands indicating a steady "Flow."



---

## 9.4 Control Charts & Cycle Time
For teams focused on efficiency, the Control Chart measures the **Cycle Time** for each issue.

* **The "Lead Time":** How long a ticket sat in the backlog before work started.
* **The "Cycle Time":** How long it took once it moved to "In Progress."
* **Outliers:** Tickets that took significantly longer than average. These are the perfect candidates for discussion during a **Retrospective**.

---

## 9.5 Building Custom Dashboards
Jira allows you to create personal and shared dashboards using "Gadgets." A high-impact engineering dashboard usually includes:
1.  **Filter Results:** Your active tickets.
2.  **Sprint Health Gadget:** Visual summary of the current sprint.
3.  **Pie Chart:** Distribution of issues by Priority or Component.
4.  **Assigned to Me:** To keep your personal "Backlog" clear.

---

## 🛠 Hands-on: The "Bottleneck" Audit
1.  **Open your team's CFD:** Look at the last 3 months.
2.  **Find the "Fat" Band:** Which status has the most vertical height? This is your team's primary bottleneck.
3.  **Investigate:** Is "Testing" the fat band? Maybe the team needs more automated tests. Is "To Do" the fat band? The Product Owner might be overwhelming the team with new ideas.
4.  **Propose a WIP Limit:** Use the data from the CFD to justify a new limit to the team.

---

**Next Up:** We wrap up this section by providing the "API Documentation" for everything we've learned. In **Chapter 10: Agile Resources & Glossary**, you'll find the external links and the "Definitions" for all Agile terminology.
