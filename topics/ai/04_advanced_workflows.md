# Chapter 4: Advanced Prompting & AI Workflows

Once you master single-shot prompting, the next step is learning how to integrate AI into complex engineering workflows. This chapter focuses on moving from "chatting" to "building systems."

---

## 4.1 Prompt Chaining
In complex engineering tasks, one massive prompt often leads to degraded quality. Instead, we use **Prompt Chaining**: breaking a large task into smaller, linked sub-tasks where the output of one prompt becomes the input for the next.

**Example: Automated Documentation Workflow**
1. **Prompt 1:** "Identify all functions in this source code and list their inputs/outputs."
2. **Prompt 2:** "Using the list from Prompt 1, write a high-level summary for a README file."
3. **Prompt 3:** "Review the README summary for technical accuracy and tone."

---

## 4.2 Introduction to RAG (Retrieval-Augmented Generation)
LLMs have a "cutoff date" for their knowledge and don't know about your private company code or internal wikis. **RAG** solves this by:
1. **Searching:** Looking up relevant snippets from a local database or files.
2. **Augmenting:** Adding those snippets to your prompt as "context."
3. **Generating:** Asking the AI to answer the question *only* using the provided context.



---

## 4.3 Multi-Step Troubleshooting
As an engineer, you can use AI to build "Troubleshooting Trees." By providing the AI with logs and a system architecture description, you can ask it to generate a hypothesis, then a command to test that hypothesis, and finally a fix.

---

## 4.4 Using Tools & Function Calling
Modern AI can do more than just talk; it can **act**. 
* **Function Calling:** You can define a set of tools (e.g., a function that queries a SQL database or a function that pings a URL) and the AI can decide *when* to call them to get real-time data.
* **Browsing:** Allowing the AI to search the web for the latest documentation or library versions.

---

## 4.5 Creating Reusable Prompt Templates
Stop rewriting prompts from scratch. Create a library of reusable `.txt` or `.md` templates for common IT tasks:
* `incident_report_template.md`
* `unit_test_generator.md`
* `regex_explainer.md`

---

## 🛠 Hands-on: Building an AI Workflow

Try to simulate a manual "Chain" using your AI assistant:

1. **Phase 1 (The Extractor):** Paste a long technical article or a log file. 
   * *Prompt:* "Extract the top 5 most critical technical issues mentioned here as a bulleted list."
2. **Phase 2 (The Solutioner):** * *Prompt:* "For each of the 5 issues identified in the previous response, write a 1-line bash command to investigate or fix it."
3. **Phase 3 (The Formatter):**
   * *Prompt:* "Take the issues and the commands and format them into a structured JSON object suitable for a ticketing system."

---

> **Note:** Now that we are thinking like "System Architects," Chapter 5 will introduce the specific **AI Tools for Developers** that implement these workflows directly in your terminal and IDE.
