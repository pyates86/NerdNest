# Chapter 03: Choreography (Decentralized) Pattern

While the Manager Pattern (Chapter 02) relies on a central authority to delegate tasks, the **Choreography Pattern**—also known as a **Chain** or **Sequential Mesh**—allows agents to work as a relay team. In this decentralized structure, each agent performs its specialized task and passes the result directly to the next agent in the sequence.

---

## 3.1 The "Relay Race" Logic
In Choreography, the "intelligence" is embedded in the handoff. There is no central supervisor watching over the entire process. Instead, each agent is programmed with a specific "Trigger" and a "Recipient."

* **The Trigger:** An agent starts its work based on the output of the previous agent.
* **The Handoff:** Once the work is done, the agent "publishes" its result to the next node in the chain.



---

## 3.2 Why Use Choreography?
1.  **Lower Latency:** Without a Manager agent constantly reviewing and "thinking" between every step, the workflow moves faster.
2.  **Simpler Prompts:** You don't need a complex "Supervisor" prompt that understands every possible sub-task. You only need agents that understand their specific input and output.
3.  **Predictable Flows:** This pattern is ideal for standard operating procedures (SOPs) where the steps never change (e.g., a "Security Audit Pipeline").

---

## 3.3 Common Topologies
Decentralized systems usually follow one of three shapes:

* **Linear Chain:** Agent A -> Agent B -> Agent C. (e.g., Translator -> Summarizer -> Formatter).
* **Cyclic Loop:** Agent A -> Agent B -> Agent A. This is used for **Self-Correction**. A "Coder" passes to a "Reviewer," who passes it back if errors are found.
* **Joint Mesh:** Multiple agents work in parallel and their outputs are combined at the final node.

---

## 3.4 The "State Handoff" Problem
The biggest challenge in a decentralized system is **Context Drift**. As information passes from Agent 1 to Agent 5, the original user intent can get lost or "mutated"—similar to a game of "Telephone."

**Solutions:**
* **The Shared Blackboard:** Instead of passing the whole history, agents write their results to a shared "State Object" that all agents can reference.
* **Strict Output Schemas:** Force every agent to output JSON. This ensures that Agent B always receives exactly what it expects from Agent A.

---

## 3.5 Manager vs. Choreography: When to use which?

| Feature | Manager (Centralized) | Choreography (Decentralized) |
| :--- | :--- | :--- |
| **Best For** | Open-ended, complex problem solving | Structured, repeatable workflows |
| **Flexibility** | High (Manager can pivot the plan) | Low (The path is usually fixed) |
| **Cost** | Higher (More LLM calls for reasoning) | Lower (Direct execution) |
| **Failure Handling** | Manager can decide to retry a step | Requires hardcoded logic or loops |

---

## 🛠 Hands-on: Designing the Relay
Imagine a "Github Issue Auto-Responder":
1.  **Agent 1 (Triage):** Categorizes the issue (Bug, Feature, Question).
2.  **Agent 2 (Labeler):** Applies the correct tags based on Agent 1's category.
3.  **Agent 3 (Responder):** If it's a "Question," it writes a polite reply. If it's a "Bug," it asks the user for logs.
4.  **Handoff Logic:** How does Agent 3 know what Agent 1 decided? Design the "JSON Packet" that travels from Agent 1 to Agent 3.

---

**Next Up:** Whether you have a Boss or a Relay team, the agents need to remember what happened ten steps ago. In **Chapter 04: State Management & Memory**, we look at how to give AI a "Long-Term Memory."
