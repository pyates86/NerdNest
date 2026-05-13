# Chapter 07: Multi-Agent Glossary

Designing and implementing **Multi-Agent Systems (MAS)** requires a precise vocabulary. Because these systems blend software architecture with LLM reasoning, terms often overlap with traditional distributed systems and cognitive science. Use this glossary as your technical reference for building and scaling agentic workflows.

---

## A - C
* **Agentic Workflow:** A design pattern where an LLM is placed in a loop (Iterative) rather than a single-shot prompt/response.
* **Autonomous Agent:** An AI system capable of choosing its own sequence of actions to achieve a goal without constant human intervention.
* **Blackboard Pattern:** A centralized "Shared State" where multiple agents read and write information to collaborate.
* **Breakpoint:** A deliberate pause in a graph or chain that persists the state and waits for an external signal (often from a human) to resume.
* **Chain of Thought (CoT):** A prompting technique that encourages the LLM to output its reasoning process before providing a final answer or tool call.
* **Choreography:** A decentralized architectural pattern where agents pass tasks to one another based on predefined rules (a "Relay Race").
* **Context Window:** The maximum amount of text (tokens) an LLM can process in a single turn.

---

## D - H
* **Delegation:** The process where a Manager Agent assigns a specific sub-task and context to a Worker Agent.
* **Entity Memory:** A persistent record of specific facts about a user, project, or object stored outside the immediate conversation history.
* **Function Calling:** (See Tool-Calling) The mechanism where an LLM outputs structured data (JSON) to signal it wants to run a specific piece of code.
* **Hallucination (Agentic):** When an agent invents a tool that doesn't exist or provides plausible-sounding but incorrect arguments to a function.
* **Handoff:** The transition of state and control from one agent to another.
* **Human-in-the-Loop (HITL):** A pattern where human intervention is required for approval, correction, or direction within an agentic process.

---

## L - O
* **Long-Term Memory:** Information stored in a database (often Vector-based) that an agent can retrieve via search to inform current reasoning.
* **Manager Pattern:** A centralized architecture where a "Supervisor" agent orchestrates the work of specialized "Worker" agents.
* **Multi-Agent System (MAS):** A system where multiple independent agents interact to solve problems that are beyond the individual capabilities of a single agent.
* **Observation:** The data or feedback returned to an LLM after it executes a tool call.
* **Orchestration:** The management of agent interactions, state transitions, and task execution order.

---

## R - S
* **RAG (Retrieval-Augmented Generation):** The process of fetching relevant documents from a database and injecting them into the agent's prompt to provide grounded knowledge.
* **ReAct (Reason + Act):** A logic framework where agents follow a cycle of Thought -> Action -> Observation.
* **Router:** A simple agent or logic gate that determines which specialized agent should handle a specific incoming request.
* **Short-Term Memory:** The active conversation history currently held in the LLM's context window.
* **State Management:** The practice of tracking and persisting the "current situation" of a workflow across multiple turns or agents.

---

## T - Z
* **Task Decomposition:** The act of breaking a complex user goal into smaller, manageable sub-tasks that can be handled by individual agents.
* **Tool-Calling:** The ability of an LLM to request the execution of external functions to interact with databases, APIs, or the web.
* **Tracing:** The process of logging every step of an agent’s reasoning and tool-calling for the purpose of debugging and observability.
* **Trajectory:** The sequence of thoughts and actions an agent took to arrive at a final answer.
* **Vector Database:** A specialized database used for storing "Memories" as numerical embeddings to allow for semantic search.

---

## 🛠 Using this Glossary
In the world of AI Engineering, precision prevents expensive errors. By using these terms correctly, you can design systems that are **Observable** (you can trace the trajectory), **Reliable** (you use HITL breakpoints), and **Scalable** (you choose the right Choreography vs. Manager pattern). 

**Congratulations!** You have completed the **Advanced AI Agent Patterns** section. You are now ready to move from simple prompt engineering to architecting complex, autonomous software systems.
