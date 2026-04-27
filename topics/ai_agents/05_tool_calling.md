# Chapter 5: Tool Use & Function Calling

Reasoning (Chapter 4) is the "Brain," but **Actuators** are the "Hands." In your notes, you defined Actuators as the mechanisms that allow an agent to interact with its environment. In the digital world, we call these **Tools** or **Functions**.

Without tools, an AI can only talk. With tools, an AI can query databases, send emails, restart servers, and write files.

---

## 5.1 What is Function Calling?
Function calling is a structured way for an LLM to tell your application: *"I don't have the answer, but I want to use this specific tool to get it."*

The process works like this:
1. **The Handshake:** You provide the AI with a list of "Tools" (functions) and a description of what they do.
2. **The Request:** The AI realizes it needs information (e.g., "What is the weather?") and outputs a JSON object containing the function name and the required arguments.
3. **The Execution:** Your code runs that function in the real world.
4. **The Response:** You send the result back to the AI so it can finish its thought.

---

## 5.2 Defining Virtual Actuators
To an AI, a tool is only as good as its description. If you don't describe the tool correctly, the AI won't know when to "reach" for it.

**A good Tool Definition includes:**
* **Name:** Clear and descriptive (e.g., `get_system_uptime`).
* **Description:** What the tool does and *when* to use it (e.g., "Use this tool when the user asks about server health or reboot history").
* **Arguments:** The specific data points the tool needs (e.g., `server_id`, `timezone`).

---

## 5.3 The Danger of "Hot" Actuators
In your notes, you mentioned **Physical Actuators** (like a robot arm). In IT, we have **"Hot" Virtual Actuators**—tools that perform destructive actions.

* **Safe Tools (Read-Only):** `list_files()`, `get_user_status()`, `check_inventory()`.
* **Hot Tools (Write/Execute):** `delete_user()`, `reboot_instance()`, `shred_logs()`.

**Golden Rule:** Always wrap "Hot" Actuators in a **Human-in-the-Loop (HITL)** validation layer. The agent should "propose" the action, but a human must click "Confirm" before the actuator triggers.

---

## 5.4 Argument Extraction
One of the most powerful features of modern LLMs is their ability to pull specific data out of messy human conversation to fit a tool's requirements.

* **User says:** "Hey, check the logs for the production-db-01 server from last Tuesday."
* **AI extracts:** * `function`: `query_logs`
    * `target`: `production-db-01`
    * `time_range`: `2024-05-21`

---

## 🛠 Hands-on: Designing a Tool Schema

Imagine you are building an agent to manage a local directory. Write a JSON-style description for a "Virtual Actuator" that creates a new folder.

```json
{
  "name": "create_directory",
  "description": "Creates a new folder on the local file system.",
  "parameters": {
    "type": "object",
    "properties": {
      "path": {
        "type": "string",
        "description": "The full path where the folder should be created."
      },
      "folder_name": {
        "type": "string",
        "description": "The name of the new directory."
      }
    },
    "required": ["path", "folder_name"]
  }
}
```

**Challenge:** If a user says "Make a folder called 'backups' in my home directory," would the AI be able to fill out the schema above?

---

> **Note:** Tools allow an agent to act in the *present*. But for complex goals, the agent needs to remember the *past*. In **Chapter 6: Agent Memory**, we will explore how to build long-term storage for our AI systems.
