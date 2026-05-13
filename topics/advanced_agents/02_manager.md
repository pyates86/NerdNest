# Chapter 02: Manager (Centralized) Pattern

As tasks become more complex, a single agent with a dozen tools can become overwhelmed, leading to "context fatigue" or incorrect tool selection. The **Manager Pattern** (also known as the **Hub-and-Spoke** or **Supervisor** model) solves this by introducing a hierarchical structure similar to a human corporate department.

---

## 2.1 The Architecture of Authority
In this pattern, one "High-Level" agent acts as the **Manager**. It does not perform the granular work itself. Instead, it manages a team of specialized **Worker Agents**.

* **The Manager:** Receives the user request, breaks it down into a plan, delegates sub-tasks to the appropriate workers, and synthesizes the final answer.
* **The Workers:** Specialized agents with access to specific tools (e.g., a "Research Agent" with web search or a "Coder Agent" with a Python REPL).



---

## 2.2 Why Use a Manager?
1.  **Specialization:** You can give worker agents highly specific system prompts. A "Legal Agent" can be told to be pedantic and cautious, while a "Creative Agent" can be told to be expansive.
2.  **Context Management:** Instead of one agent holding the entire history of a 50-step process, the Manager only holds the high-level plan, and workers only hold the context for their specific sub-task.
3.  **Reliability:** By limiting the number of tools available to each worker, you drastically reduce the chance of the LLM picking the wrong tool for the job.

---

## 2.3 The "Routing" Logic
The core of the Manager Pattern is **Routing**. The Manager must decide:
1.  **Who** is best equipped for the next step?
2.  **What** information do they need from the previous steps?
3.  **When** is the task complete?

This is often implemented using a **State Machine**. The Manager outputs the name of the next agent, and the orchestration framework (like LangGraph or CrewAI) triggers that specific worker.

---

## 2.4 Managing the "Recursive Loop"
One risk of the Manager pattern is the "Infinite Loop," where a Manager and Worker keep passing a failing task back and forth. 
* **Self-Correction:** A good Manager pattern includes a "Reviewer" role or a step where the Manager evaluates the worker's output against the original goal.
* **Limiters:** Architects usually implement a `max_iterations` cap to prevent the system from burning API credits if the agents get stuck.

---

## 2.5 Real-World Example: An AI Content Agency
* **Manager Agent:** Receives the topic "The Future of Solar Energy."
* **Worker 1 (Researcher):** Searches for the latest 2026 data on solar cell efficiency.
* **Worker 2 (Writer):** Takes the data and drafts a 500-word article.
* **Worker 3 (Editor):** Reviews the draft for tone and factual consistency.
* **Manager Agent:** Reviews the final version and presents it to the user.

---

## 🛠 Hands-on: Building a Hierarchy
Think about an "AI Travel Agent" system:
1.  **Define the Workers:** What specialized agents do you need? (e.g., Flight Specialist, Hotel Specialist, Weather Specialist).
2.  **The Delegation Prompt:** Write a prompt for the Manager. How should it handle a request like "I want a sunny vacation under $2000"? 
3.  **The Synthesis:** How should the Manager merge the output of the Flight Specialist and the Hotel Specialist into a single coherent itinerary?

---

**Next Up:** Hierarchy provides control, but it can be slow. In **Chapter 03: Choreography (Decentralized) Pattern**, we explore how agents can collaborate as peers without a "Boss" agent directing every move.
