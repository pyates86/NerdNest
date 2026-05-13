# Chapter 01: Agentic Reasoning & Tool-Use

The difference between a "Chatbot" and an "Agent" is the ability to **reason** and **act**. While a chatbot only predicts the next token, an agent uses an LLM as a reasoning engine to decide which actions to take to achieve a goal. This process is powered by two core concepts: **Agentic Reasoning Loops** and **Tool-Calling**.

---

## 1.1 The ReAct Pattern (Reason + Act)
Most modern agents follow the **ReAct** framework. Instead of providing a single answer, the agent goes through a cycle:
1.  **Thought:** The agent analyzes the user request and determines what it needs to know or do.
2.  **Action:** The agent selects a "Tool" to use (e.g., searching the web or checking a database).
3.  **Observation:** The agent reads the output of that tool.
4.  **Repeat:** The agent updates its thought process based on the observation until the task is complete.



---

## 1.2 Mechanics of Tool-Calling
"Tool-Calling" (sometimes called Function Calling) is the bridge between the LLM and your code. It is **not** the LLM actually running a function; it is the LLM generating a structured request for *your* application to run one.

**The Workflow:**
1.  **Declaration:** You provide the LLM with a list of "Tools" (JSON definitions of function names, descriptions, and parameters).
2.  **Selection:** The LLM realizes it can't answer a question (e.g., "What is the stock price of Apple?") with internal data, so it outputs a JSON object: `{"function": "get_stock_price", "symbol": "AAPL"}`.
3.  **Execution:** Your backend code sees this request, executes the actual code, and gets the result.
4.  **Integration:** You send the result back to the LLM. The LLM then uses that "Observation" to formulate its final response.



---

## 1.3 Chain of Thought (CoT)
To improve tool-calling accuracy, agents use **Chain of Thought**. By prompting the agent to "think step-by-step," you force the LLM to map out its logic before it calls a tool. This significantly reduces "Hallucinations"—where an agent might try to use a tool that doesn't exist or pass incorrect arguments.

---

## 1.4 Why This Matters for Architects
As an engineer, you are no longer just writing code that runs linearly. You are building an **Environment** for an agent.
* **Prompt Engineering:** You must write clear tool descriptions so the LLM knows *when* to use them.
* **Error Handling:** What happens if a tool fails? You must teach the agent how to handle "exceptions" (e.g., "The database is down; tell the user you will try again in 5 minutes").
* **Security:** You must ensure the agent only has access to tools it is authorized to use (The "Principle of Least Privilege").

---

## 🛠 Hands-on: Defining a Tool
Imagine you are building an agent to manage a Todo list.
1.  **Define the Tool:** Write a JSON schema for a `create_task` function. It should require a `title` and an optional `due_date`.
2.  **The Reasoning Test:** If you tell the agent "I need to buy milk tomorrow," does your tool definition provide enough context for the LLM to extract "Buy Milk" as the title and calculate "tomorrow's date" correctly?
3.  **Observation Handling:** If the `create_task` function returns a `task_id`, how will you prompt the agent to confirm the success to the user?

---

**Next Up:** Once an agent can use tools, we can start grouping them together. In **Chapter 02: Manager (Centralized) Pattern**, we look at how one agent can lead a team of others.
