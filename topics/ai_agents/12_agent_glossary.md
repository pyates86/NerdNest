# Chapter 12: Agentic AI Glossary

This glossary focuses on the specialized terminology used when building autonomous and multi-agent systems. Use this as a reference when reading documentation for frameworks like LangGraph, CrewAI, or AutoGen.

---

## 12.1 Architectural Terms
| Term | Definition |
| :--- | :--- |
| **Actuator** | The mechanism (physical or virtual) that allows an agent to affect its environment (e.g., an API call or a robot arm). |
| **Agentic Loop** | The continuous cycle of Perception → Reasoning → Action → Observation. |
| **Environment** | The world (digital or physical) in which the agent operates and receives sensor data from. |
| **Function Calling** | A protocol where the LLM outputs structured data (JSON) to signal it wants to use a specific tool. |
| **Human-in-the-Loop (HITL)** | A safety pattern where a human must approve or oversee an agent's action before it executes. |
| **Sensor** | The means by which an agent receives input or data from its environment (e.g., log files, webhooks, or cameras). |
| **State** | A snapshot of the agent's current knowledge, memory, and environmental conditions at a specific point in time. |

---

## 12.2 Reasoning & Planning
| Term | Definition |
| :--- | :--- |
| **Chain-of-Thought (CoT)** | A prompting technique that encourages the LLM to write out intermediate logical steps before a final answer. |
| **Critic** | A secondary agent or logic layer tasked with evaluating the "Actor" agent's output for errors or bias. |
| **Dynamic Planning** | The ability of an agent to rewrite its future steps based on the results of its previous actions. |
| **ReAct** | (Reason + Act) A framework where the agent interleaves reasoning "Thoughts" with environmental "Actions." |
| **Self-Reflection** | A process where an agent critiques its own previous output to find and fix errors (Self-Correction). |
| **Trajectory** | The sequence of thoughts, actions, and observations an agent takes to complete a task. |

---

## 12.3 Multi-Agent Systems (MAS)
| Term | Definition |
| :--- | :--- |
| **Collaboration** | When two or more agents work together as peers to solve a problem. |
| **Delegation** | The process of a "Manager Agent" assigning a specific sub-task to a "Worker Agent." |
| **Handoff** | The transition of a task and its context from one specialized agent to another. |
| **Orchestration** | The coordination and management of multiple agents to ensure they work toward a common goal without looping. |
| **Shared Whiteboard** | A common memory space where multiple agents can read and write information to stay synchronized. |

---

## 12.4 Memory & Data
| Term | Definition |
| :--- | :--- |
| **Context Window** | The "Working Memory" limit of the agent (measured in tokens). |
| **Episodic Memory** | A record of "what happened" in previous steps of the current task. |
| **Long-Term Memory** | Stored information (usually in a Vector Database) that persists across different sessions. |
| **Semantic Search** | Looking up "memories" based on meaning rather than exact keyword matches using embeddings. |
| **Vector Database** | A specialized database designed to store and retrieve high-dimensional embeddings for agent memory. |

---

## 12.5 Security & Reliability
| Term | Definition |
| :--- | :--- |
| **Agentic Drift** | When an agent loses focus on its original goal over a long sequence of actions. |
| **Guardrail** | A hard-coded rule or secondary check that prevents an agent from performing unauthorized actions. |
| **Prompt Injection** | A security hack where a user or an external document tricks an agent into ignoring its system instructions. |
| **Sandboxing** | Running an agent's actuators in an isolated environment (like a Docker container) to prevent system damage. |
| **Tool Saturation** | When an agent is given too many tools to choose from, causing it to become "confused" or pick the wrong one. |

---

> **Note:** The "Language of Agents" is still being written. If you encounter a new term in a 2026 research paper, try to map it back to the core concepts of **Perception, Reasoning, and Action**!
