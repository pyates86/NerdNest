# Chapter 04: Kanban & Flow

While Scrum (Chapter 03) relies on fixed-length "pulses" (Sprints), **Kanban** is a methodology focused on continuous delivery and efficiency. It is a visual system for managing work as it moves through a process. Kanban is particularly popular for DevOps, SRE, and maintenance teams where work arrives unpredictably and needs to be addressed immediately.

---

## 4.1 The Core Principles of Kanban
Kanban is less about "roles and ceremonies" and more about **flow**. It follows four foundational principles:
1.  **Visualize the Workflow:** Use a board to show every piece of work (cards) and every stage of the process (columns).
2.  **Limit Work in Progress (WIP):** This is the most critical rule. You must limit how many tasks can be in a specific state at one time.
3.  **Manage Flow:** Observe how work moves through the system and identify where it gets stuck (bottlenecks).
4.  **Make Process Policies Explicit:** Everyone should know exactly what "In Review" or "Done" means without asking.

---

## 4.2 The Kanban Board
A typical Kanban board represents a "Value Stream." It moves from left (To Do) to right (Done).

* **Backlog:** Ideas and requests.
* **Ready for Dev:** Prioritized tasks.
* **In Progress:** Active development.
* **Peer Review:** Code being audited.
* **Testing/QA:** Validation.
* **Done:** Shipped to production.



---

## 4.3 WIP Limits: The Secret Sauce
In Scrum, the Sprint acts as a container. In Kanban, the **WIP Limit** is the constraint.
* If your "Review" column has a WIP limit of 2, and there are already two PRs waiting, **no one is allowed to move a new task into Review.**
* **Why it works:** It forces the team to "Stop starting and start finishing." Instead of picking up a new feature, a developer is forced to help clear the bottleneck in the Review column.

---

## 4.4 Kanban vs. Scrum: Which to use?

| Feature | Scrum | Kanban |
| :--- | :--- | :--- |
| **Cadence** | Regular fixed-length sprints | Continuous flow |
| **Release Methodology** | At the end of sprint (usually) | Continuous delivery |
| **Roles** | PO, Scrum Master, Dev Team | No required roles |
| **Primary Metric** | Velocity (Points per sprint) | Cycle Time (Time per task) |
| **Change** | No changes during the sprint | Changes can happen at any time |

---

## 4.5 Key Metrics: Lead Time and Cycle Time
In a flow-based system, we measure speed differently:
* **Lead Time:** The total time from when a request is made until it is delivered.
* **Cycle Time:** The time from when work actually starts on a task until it is finished.
* **Goal:** A healthy Kanban team works to reduce Cycle Time by identifying and removing bottlenecks.

---

## 🛠 Hands-on: The WIP Limit Challenge
Look at your current team's board (Jira, Trello, or physical):
1.  **Identify the Pile-up:** Which column consistently has the most tickets? (Usually "In Review" or "Waiting for QA").
2.  **Propose a Limit:** Suggest a WIP limit for that column. For example, if you have 4 developers, set the "In Progress" limit to 3.
3.  **Watch the Behavior Change:** Observe how the team starts collaborating more on finishing existing tickets rather than hoarding new ones.

---

**Next Up:** Whether you use Scrum or Kanban, you need a way to define the work itself. In **Chapter 05: User Stories & Requirements**, we learn how to write tickets that make sense.
