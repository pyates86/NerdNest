# Chapter 6: Agent Memory (Short-Term vs. Long-Term)

In Chapter 1, we established that a model interprets perceptions. However, as you noted in your Five Key Characteristics, a sophisticated agent needs **Memory**. Without memory, an agent is "stateless"—it treats every interaction as if it's the first time it has ever met you, even if you’ve been talking for an hour.

In Agentic AI, we mirror human biology by splitting memory into two distinct systems: **Short-Term** and **Long-Term**.

---

## 6.1 Short-Term Memory (Working Memory)
**Short-Term Memory** is the agent's immediate context. It consists of the current conversation history and the intermediate steps of a task.

* **How it works:** This is usually stored in the **Context Window** of the LLM. Every time you send a new message, the previous few messages are "re-sent" along with it so the AI remembers what was just said.
* **The "Goldfish" Problem:** Context windows are finite. If a conversation goes on too long, the oldest messages "drop off" the top to make room for new ones. The agent literally "forgets" how the conversation started.

---

## 6.2 Long-Term Memory (The Library)
**Long-Term Memory** allows an agent to recall information from days, weeks, or even years ago. It survives session resets and system reboots.

* **How it works:** Instead of shoving everything into the context window, we store information in an external database—most commonly a **Vector Database**.
* **Use Cases:**
    * **User Preferences:** Remembering that a user prefers Python over Java.
    * **Past Lessons:** Remembering that "The last time I tried to reboot server-01, it required a manual override."
    * **Domain Knowledge:** Storing 1,000 pages of technical manuals that the agent can "look up" when needed.

---

## 6.3 Vector Embeddings: How AI "Remembers"
Computers don't store "memories" as text; they store them as **Embeddings** (lists of numbers).



When an agent "remembers" something, it performs a **Semantic Search**:
1. It turns your question into a vector (a coordinate in a multi-dimensional map).
2. It looks for the "memories" that are mathematically closest to that coordinate.
3. It pulls those memories back into the Short-Term context to answer your question.

---

## 6.4 The Memory Types (AIOps Perspective)
From an engineering standpoint, you will deal with three types of stored content:
1. **Episodic Memory:** "What happened?" (The log of past actions and outcomes).
2. **Semantic Memory:** "What is true?" (Facts about your infrastructure or code).
3. **Procedural Memory:** "How do I do it?" (Learned workflows or specialized scripts).

---

## 6.5 Garbage Collection for AI
You cannot store *everything* forever, or the agent’s "brain" will become cluttered with irrelevant data. Sophisticated agents use **Memory Management**:
* **Summarization:** Every 10 messages, the agent creates a "summary" of the chat and clears the raw history.
* **Importance Scoring:** The agent only saves a memory to the Long-Term database if it deems the information "highly important" for the future.

---

## 🛠 Hands-on: Building a Memory Map

Imagine you are building a **Personal Onboarding Agent** for new developers. Categorize the following data points: Should they be in **Short-Term** (Context) or **Long-Term** (Vector DB) memory?

1. The developer's name (provided in the first message).
2. The company's 50-page "Security Standards" document.
3. The specific error message the developer just pasted 2 seconds ago.
4. The fact that this developer struggled with "Git Rebase" three weeks ago.

**Reflection:** Why would putting the 50-page document in "Short-Term" memory be a bad idea for performance and cost?

---

> **Note:** Memory gives an agent a past. Now we need to give it a way to improve its future. In **Chapter 7: Reflection Loops**, we will explore how agents can "critique" their own work to fix mistakes before you ever see them.
