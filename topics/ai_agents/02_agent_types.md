# Chapter 2: Types of Agent Structures

Not all agents are created equal. Depending on the goal and the complexity of the environment, an agent's internal "wiring" can range from a simple "if-this-then-that" script to a highly sophisticated system that learns from its own failures.

In this chapter, we categorize AI Agents into five distinct structures based on their complexity and functionality.

---

## 2.1 The Simple Reflex Agent
The **Simple Reflex Agent** is the most basic type. it acts only on the basis of the *current* perception, ignoring the rest of the perceptual history. 

* **Logic:** Condition-Action Rules (e.g., "If $A$, then do $B$").
* **Example:** A simple server monitor that sends a Slack alert the moment CPU usage exceeds 90%. It doesn't care what the CPU was doing five minutes ago; it only cares about the "now."
* **Limitation:** It only works if the environment is fully observable and the rules are perfect.

---

## 2.2 The Model-Based Reflex Agent
A **Model-Based Reflex Agent** maintains an internal "state" that tracks parts of the environment it cannot see right now. It has a "memory" of how the world works.

* **Logic:** "How the world evolves" + "What my actions do."
* **Example:** A self-driving car approaching a blind intersection. Even if a pedestrian is temporarily hidden by a parked truck (lost perception), the internal "model" remembers the pedestrian was there and maintains safety.
* **Key Feature:** It handles partial observability by maintaining history.

---

## 2.3 The Goal-Based Agent
A **Goal-Based Agent** acts to achieve a specific target. It doesn't just react to inputs; it evaluates different sequences of actions to see which one leads to the desired goal.

* **Logic:** Search and Planning.
* **Example:** A Shopping Assistant AI. If you say, "I need a high-end laptop for under $1500 by Friday," the agent doesn't just click the first link. It searches, compares prices, checks shipping speeds, and plans the purchase to meet the specific "Goal."
* **Key Feature:** It is proactive rather than reactive.

---

## 2.4 The Utility-Based Agent
Sometimes "reaching the goal" isn't enough—you want to reach the goal in the *best* way possible. A **Utility-Based Agent** uses a "utility function" to measure how "happy" or "efficient" a particular state is.

* **Logic:** Optimization (Trade-offs).
* **Example:** A Cloud Infrastructure Agent tasked with scaling servers. It has to balance two conflicting goals: High Performance (Goal A) and Low Cost (Goal B). It calculates the "Utility" of different configurations to find the most efficient balance.
* **Key Feature:** It handles complex trade-offs and multiple competing goals.

---

## 2.5 The Learning Agent
The **Learning Agent** is the most sophisticated structure. It can operate in initially unknown environments and become more competent than its initial programming allowed.

* **Components:**
    * **Learning Element:** Makes improvements based on experience.
    * **Performance Element:** Selects external actions.
    * **Critic:** Provides feedback to the learning element based on a fixed performance standard.
    * **Problem Generator:** Suggests actions that will lead to new and informative experiences.
* **Example:** An AI Cybersecurity Agent that watches network traffic. Over time, it learns what "normal" looks like for your specific company and begins to identify new, never-before-seen attack patterns without being explicitly programmed for them.

---

## 2.6 Five Key Characteristics of Sophisticated Agents
As you move toward building the more advanced agents (Goal, Utility, and Learning), you must ensure they possess these five traits:

1.  **Profile & Persona:** A defined identity and set of boundaries.
2.  **Memory:** The ability to store and retrieve past experiences.
3.  **Reasoning:** The logic used to plan and make decisions.
4.  **Actions:** A set of tools (actuators) to interact with the world.
5.  **Learning & Capabilities:** The ability to acquire new skills or improve existing ones.

---

## 🛠 Hands-on: Identifying the Structure
Take three tools you use daily (e.g., an Email Spam Filter, a Thermostat, and GitHub Copilot). 

* Which of the 5 categories do they fall into?
* Why? (Does it have a goal? Does it learn? Is it just a reflex?)

---

> **Note:** Now that we understand the structures, we need to give our agents an identity. In **Chapter 3: Persona Design**, we will learn how to build the "Profile" of an agent to keep its behavior consistent.
