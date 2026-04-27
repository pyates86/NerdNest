# Chapter 10: Capstone Project - The Autonomous "Log-to-Fix" Agent

We have covered the brain, the hands, the memory, and the brakes of an AI system. In this final chapter, we will bring all these components together to design a production-ready agent. 

**The Mission:** Build an "On-Call Assistant" that can detect a server error, investigate the cause, and propose a documented fix.

---

## 10.1 Phase 1: Environment & Sensors (Perception)
First, we define where our agent lives and how it "sees."
* **Environment:** A Linux-based web server running a Python application.
* **Sensors:** 1. A file-watcher tool that monitors `/var/log/syslog`.
    2. An API connection to the application's GitHub repository.
* **Trigger:** The agent remains idle until a "Sensor" detects the string `ERROR` or `CRITICAL`.

---

## 10.2 Phase 2: The Model & Persona (Reasoning)
We need a persona that is analytical and cautious.
* **Role:** Senior Site Reliability Engineer (SRE).
* **Expertise:** Linux system administration, Python debugging, and Git workflows.
* **Decision Logic:** The agent must use a **ReAct** pattern. It cannot suggest a fix until it has successfully "Read" the error log and "Searched" the code for the relevant line number.

---

## 10.3 Phase 3: Actuators & Tools (Action)
Our agent needs "Virtual Actuators" to interact with the environment.
* **Tool 1:** `grep_logs(keyword)` – To search for related errors.
* **Tool 2:** `read_source_code(file_path)` – To examine the buggy code.
* **Tool 3:** `git_create_branch(branch_name)` – To prepare a fix.
* **Tool 4:** `submit_pull_request(title, body)` – To present the solution to a human.

---

## 10.4 Phase 4: Memory & Feedback (Reflection)
To ensure the agent doesn't get stuck, we implement memory and loops.
* **Short-Term Memory:** Stores the current terminal outputs so the agent doesn't run the same failing command twice.
* **Long-Term Memory (Vector DB):** Stores a "Knowledge Base" of previous resolved incidents. The agent queries this to see if a similar error has happened before.
* **Feedback Loop:** If the agent's proposed code change fails a `Linter` check, it must **Reflect** (Chapter 7) and rewrite the code before submitting the PR.

---

## 10.5 Phase 5: Security & HITL (Guardrails)
Since this agent can create Git branches and read logs, we must secure it.
* **Sandboxing:** The agent runs its investigation inside a restricted Docker container, not on the production host.
* **HITL (Human-in-the-Loop):** The agent is **never** allowed to merge code to the `main` branch. It can only submit a Pull Request for a human engineer to review and approve.

---

## 🛠 Hands-on: Building the Logic Flow

Using everything you have learned, draw a flowchart (or write a pseudo-code sequence) for the following scenario:

**Scenario:** The sensor detects a `Database Connection Timeout`.

1. **Observation:** Sensor sees the error.
2. **Thought:** "I need to check if the database service is running."
3. **Action:** Call `check_service_status(service_name="postgresql")`.
4. **Observation:** Service is "Active."
5. **Thought:** "If the service is up, maybe the credentials in the `.env` file are wrong. I should check the recent changes to that file."
6. **Action:** [What is the next step?]
7. **Final Goal:** Submit a PR with the fix or a report explaining the connectivity issue.

---

## 🚀 The Future of Your Agentic Journey
You have moved from understanding the basic components (Sensors, Models, Actuators) to architecting a complex, autonomous system. The next step is implementation. 

Use frameworks like **LangChain**, **CrewAI**, or **Ollama** to turn this Capstone design into a working piece of software. Remember: Start with **Simple Reflex** logic and slowly build toward a **Learning Agent**.

---

> **Congratulations!** You have completed the Agentic AI Section. You are now equipped to build systems that don't just answer questions, but solve problems. 
> 
> Check **Chapter 11: Agent Resources** for the best libraries and tools to start coding today.
