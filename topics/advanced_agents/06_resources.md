# Chapter 06: Multi-Agent Resources

Building multi-agent systems is significantly harder than building a basic chatbot. You have to handle concurrency, state persistence, error recovery, and tool orchestration. Fortunately, several powerful frameworks have emerged to handle the "Heavy Lifting" of agentic architecture.

---

## 6.1 Framework Comparison
Different frameworks prioritize different patterns (Manager vs. Choreography).

| Framework | Best For | Core Philosophy |
| :--- | :--- | :--- |
| **LangGraph** | Complex, Cyclic Workflows | Treats agents as nodes in a **State Machine**. Offers the best control over "Time Travel" and persistence. |
| **CrewAI** | Role-Based Collaboration | Uses a **Manager Pattern** by default. Very easy to assign "Jobs" to specific "Crews" of agents. |
| **AutoGen** | Conversational Agents | Developed by Microsoft. Focuses on agents "talking" to each other to solve problems. |
| **PydanticAI** | Type-Safe Agents | Built on top of Pydantic. Best for developers who want strict data validation for every tool call and handoff. |

---

## 6.2 The "Standard Library" of Tools
Agents are only as good as their tools. These are the "Connectors" you should know:
* **LangChain Community Tools:** A massive repository of pre-built tools (Google Search, Wikipedia, SQL, Shell, etc.).
* **Tavily / Exa:** Search engines specifically designed for AI agents to retrieve clean, structured data for RAG.
* **MultiOn:** A web-agent tool that allows your agents to interact with websites that don't have APIs.

---

## 6.3 Infrastructure & Observability
Because agents can be "Black Boxes," you need tools to see what they are thinking:
* **LangSmith / LangFuse:** Essential for **Tracing**. You can see exactly which thought led to which tool call and how much it cost.
* **AgentOps:** Specifically for monitoring the health, success rate, and "loops" of multi-agent teams.
* **Docker / E2B:** **Sandboxing** tools. Never let an agent run code directly on your local machine; run it in a secure, isolated container.

---

## 6.4 Learning & Research
The field of MAS is moving fast. These are the "Must-Watch" repositories:
* **The "ReAct" Paper:** Understand the academic foundation of Thought/Action/Observation.
* **DeepLearning.AI (AI Agentic Workflows):** Andrew Ng’s courses are the industry standard for learning these patterns.
* **OpenAI Assistants API:** A managed service for those who want the "Easy Button" for building simple agents with tool-calling.

---

## 🛠 Hands-on: Choosing Your Stack
Evaluate your next project:
1.  **Complexity Check:** Is it a simple linear chain (Choreography) or a complex loop with human approval (HITL)?
2.  **Tool Selection:** Do you need pre-built tools (LangChain), or are you building custom internal APIs?
3.  **Observability Setup:** Choose one tracing tool (e.g., LangSmith) and integrate it into a basic script to see the "Thought" process visualized.

---

**Next Up:** We wrap up this deep dive with the "Dictionary of Autonomy." In **Chapter 07: Multi-Agent Glossary**, we define the terms that will help you communicate like a lead AI Architect.
