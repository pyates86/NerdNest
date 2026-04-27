# Chapter 7: Reflection Loops & Self-Correction

In your notes, you identified **Feedback Mechanisms** as the component that allows an agent to evaluate whether it has successfully achieved its goals. In the world of LLMs, we implement this through **Reflection Loops**. 

Reflection is the difference between an AI that "guesses" and an AI that "verifies." It allows the agent to look at its own output, identify errors, and correct them before the final result reaches the user.

---

## 7.1 The "Self-Critique" Pattern
A reflection loop typically follows a "Critic" architecture. Instead of just producing an answer, the system follows these steps:
1.  **Drafting:** The agent generates an initial solution to the problem.
2.  **Critique:** The agent (or a second "Reviewer" agent) examines the draft for bugs, logical fallacies, or violations of the Persona constraints.
3.  **Refinement:** The agent rewrites the solution based on the critique.



---

## 7.2 Types of Feedback
Agents use two main types of feedback to refine their behavior:

* **Internal Feedback (Self-Correction):** The agent uses its own internal logic to double-check its work. For example, "Does this code I just wrote actually follow the security rules I was given in Chapter 3?"
* **External Feedback (Environmental):** The agent observes the "Updated State" of the environment (as noted in your feedback loop notes). For example, "I tried to run the script, but the terminal returned an `Access Denied` error. I must try a different approach."

---

## 7.3 Verification Layers
To ensure an agent doesn't get stuck in a "hallucination loop," engineers often implement **External Validation Systems**.
* **Code Execution:** If an agent writes a Python script, the system automatically runs it in a sandbox. If it throws an error, that error is fed back to the agent as a "Perception."
* **Linter Integration:** Forcing an agent's code through a tool like `Pylint` or `Flake8`. The agent isn't allowed to "finish" until the external tool gives a passing grade.

---

## 7.4 The "Stop" Condition
One risk with autonomous agents is the **Infinite Loop**. If an agent is too critical of itself, or if the environment keeps returning errors, the agent might loop forever, burning API credits.
* **Maximum Iterations:** Setting a hard limit (e.g., "Reflect a maximum of 3 times").
* **Success Threshold:** Defining exactly what "good enough" looks like so the agent knows when to stop.

---

## 7.5 Learning from Failure
As your notes on **Learning Agents** mentioned, sophisticated systems use the feedback loop to improve future behavior. 
* If an agent fails at a task 3 times but succeeds on the 4th, it should summarize *why* the first three attempts failed.
* This summary is then saved to the **Long-Term Memory** (Chapter 6) so that next time, the agent doesn't repeat the same mistakes.

---

## 🛠 Hands-on: Building a "Critic" Prompt

Try this experiment in your favorite LLM. Paste the following prompt structure:

> **Step 1 (The Worker):** "Write a Python function to calculate the Fibonacci sequence up to $n$."
> 
> **Step 2 (The Critic):** "Now, act as a Senior Code Reviewer. Find three potential issues with that code (e.g., performance, edge cases, or readability)."
> 
> **Step 3 (The Refiner):** "Rewrite the original code to address the three issues identified by the Critic."

**Observation:** Compare the Step 1 code with the Step 3 code. Did the "Reflection" improve the quality?

---

> **Note:** Reflection makes a single agent smarter. But what if we had multiple agents talking to each other? In **Chapter 8: Multi-Agent Teams**, we will explore how to build a digital workforce of specialized agents.
