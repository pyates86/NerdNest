# Chapter 8: Multi-Agent Teams & Orchestration

In the previous chapters, we focused on a single agent—one "brain" with its own tools and memory. However, just as a single developer cannot build, test, and deploy an entire enterprise application alone, a single agent often struggles with massive, complex tasks.

The next evolution is **Multi-Agent Systems (MAS)**: a team of specialized agents working together to solve a common goal.

---

## 8.1 Why Multi-Agent?
Why not just build one "God Agent" that can do everything?
1.  **Context Management:** Large prompts for complex tasks "clog" the model's focus. Smaller, specialized prompts for specific roles lead to higher accuracy.
2.  **Specialization:** A "Security Agent" and a "UX Agent" can have different personas, tools, and constraints.
3.  **Parallelization:** Agents can work on separate tasks simultaneously (e.g., one writes code while another writes documentation).

---

## 8.2 Common Multi-Agent Architectures
There are two primary ways to organize an AI team:

### A. The Hierarchical (Conductor) Model
A "Manager Agent" receives the high-level goal from the user, breaks it into sub-tasks, and assigns them to specialized "Worker Agents." The workers report back to the Manager, who validates the results.
* **Best for:** Tasks with clear hierarchies, like software development or project management.

### B. The Collaborative (Peer-to-Peer) Model
Agents work in a "round-robin" or "sequential" fashion. Agent A finishes a task and "hands it off" to Agent B.
* **Best for:** Linear workflows, like a content pipeline (Researcher → Writer → Editor → Publisher).

---

## 8.3 Orchestration Frameworks
In 2026, engineers rarely build the logic for these "handoffs" from scratch. We use **Orchestration Frameworks**:

* **CrewAI:** Focuses on "Role-Playing." You define a "Crew" where agents have specific roles, backstories, and goals. It handles the task delegation automatically.
* **Microsoft AutoGen:** Highly flexible and customizable. It excels at "conversational" multi-agent workflows where agents might need to debate a solution.
* **LangGraph:** A low-level framework that treats agent workflows as "graphs" (Nodes and Edges). It provides the most control over exactly how an agent "loops" or "branches."

---

## 8.4 Communication & Handoffs
For a team to work, the agents must communicate effectively. This is usually handled via:
* **Shared State:** All agents have access to a central "whiteboard" or database where they can see the progress of the project.
* **Message Passing:** One agent explicitly "pings" another with a specific request and the necessary context.

---

## 8.5 Avoiding "Agentic Chaos"
When multiple agents talk to each other, things can go wrong:
* **The Echo Chamber:** Two agents might get stuck in an infinite loop of "Thank you" / "No, thank you" or "I fixed it" / "No, you didn't."
* **Goal Drift:** Without a strong "Manager" or "Critic," the agents might get distracted by minor sub-tasks and forget the main objective.
* **Cost Escalation:** Every message between agents uses tokens. A poorly designed team can spend $50 on a task that a single agent could have done for $0.05.

---

## 🛠 Hands-on: Designing a "Mini-Crew"

Imagine you are building an AI team to **"Automate a Weekly Security Report."** Define the roles and responsibilities for a 3-agent team:

1.  **Agent 1 (The Log Scraper):** * *Goal:* Pull all 'Critical' and 'Warning' logs from the last 7 days.
    * *Tools:* Log Explorer API.
2.  **Agent 2 (The Security Analyst):** * *Goal:* Identify patterns in the logs (e.g., brute force attempts).
    * *Tools:* Threat Intelligence Database.
3.  **Agent 3 (The Report Writer):** * *Goal:* Summarize findings into a professional PDF for the CTO.
    * *Tools:* PDF Generator.

**Reflection:** Which agent should be the "Manager" in this scenario, or should it be a linear "Peer-to-Peer" handoff?

---

> **Note:** Now that we have a team of agents, we have a team of "actuators" that can potentially do damage. In **Chapter 9: Agent Security & Guardrails**, we will learn how to keep our digital workforce under control.
