# Chapter 4: Reasoning Patterns (CoT & ReAct)

In your introductory notes, you identified **Decision-Making Logic** as the mechanism responsible for evaluating options. In the world of Large Language Models, we don't just want the answer; we want the agent to "think out loud." This is known as **Reasoning**.

Without a structured reasoning pattern, an agent acts like a person who speaks before they think. Reasoning patterns force the agent to slow down and plan.

---

## 4.1 Chain-of-Thought (CoT)
**Chain-of-Thought** is a technique where the agent is instructed to break down a complex problem into a series of intermediate logical steps.

* **Why it works:** LLMs are "Next Token Predictors." If you ask for a final answer immediately, the model might guess. If you force it to write out the steps, the "correct" final answer becomes the most likely next token based on its own logical trail.
* **Example Prompting:** "Think step-by-step. First, identify the error. Second, check the dependencies. Third, suggest a fix."

---

## 4.2 The ReAct Pattern (Reason + Act)
The **ReAct** pattern is the gold standard for Agentic AI. It combines reasoning with the ability to take actions in the environment. It follows a specific loop:

1.  **Thought:** The agent describes what it believes is happening and what it should do next.
2.  **Action:** The agent selects a tool to use (e.g., searching a database).
3.  **Observation:** The agent reads the output of that tool (the sensor data).
4.  **Repeat:** Based on the observation, the agent creates a new **Thought**.



---

## 4.3 Multi-Step Planning
As agents move from "Reflex" to "Goal-Based" (as noted in Chapter 2), they must perform **Planning**.
* **Static Planning:** The agent creates a 5-step plan and follows it blindly. (High failure rate).
* **Dynamic Planning:** The agent creates a plan but re-evaluates it after every single action. If step 1 fails, it rewrites steps 2 through 5.

---

## 4.4 External Validation Systems
As your notes highlighted, an agent’s analysis should often be double-checked against a pre-existing logic layer. 
* **The "Critic" Pattern:** One LLM (the Actor) proposes a solution, and a second LLM (the Critic) looks for flaws in the reasoning. 
* **Hard-Coded Validation:** Before the agent's decision is turned into an action, a traditional script (Python/RegEx) checks if the output follows the required safety rules.

---

## 4.5 Managing "Hallucinated" Logic
Sometimes an agent will "reason" its way into a lie. It might claim it checked a server that doesn't exist.
* **Grounding:** You can prevent this by forcing the agent to provide "citations" for its thoughts. 
* **Example:** "For every 'Thought' you have, you must reference a specific log entry or API response that supports it."

---

## 🛠 Hands-on: Tracing a ReAct Loop
Imagine an agent tasked with "Updating an outdated Python library." Write out the **Thought/Action/Observation** loop it might go through:

1.  **Thought:** "I need to check the current version of the `requests` library."
2.  **Action:** Run `pip show requests`.
3.  **Observation:** "Version 2.25.1 is installed. Latest is 2.31.0."
4.  **Thought:** "The version is outdated. I should check if the new version has breaking changes for our code."
5.  **Action:** [What would the next action be?]

---

> **Note:** Reasoning is the "Brain," but a brain without hands can't change the world. In **Chapter 5: Tool Use & Function Calling**, we will learn how to connect this reasoning to **Virtual Actuators**.
