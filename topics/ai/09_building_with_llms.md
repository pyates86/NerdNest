# Chapter 9: Generative AI & Building with LLMs

We have reached the "implementation" phase. In this chapter, we explore how to move from being a user of AI to an architect who integrates Large Language Models (LLMs) into applications. We will cover the two primary ways to work with LLMs: **Cloud APIs** and **Local Models**.

---

## 9.1 The API Economy: OpenAI, Anthropic, and Groq
The fastest way to build an AI app is to use a hosted API. You send text (and a credit card payment) to a provider, and they return the "intelligence."

* **OpenAI (GPT-4o):** Excellent all-rounder, massive ecosystem.
* **Anthropic (Claude 3.5 Sonnet):** Renowned for superior coding ability and a more "human" writing tone.
* **Groq:** A specialized hardware provider that serves open-source models (like Llama 3) at blistering speeds.

---

## 9.2 Running Local Models with Ollama
For many engineering tasks, you don't want to send your data to the cloud. **Ollama** allows you to run powerful open-source models directly on your laptop or private server.

* **Privacy:** Your data never leaves your machine.
* **Cost:** It’s free (no per-token fees).
* **Speed:** No network latency, though performance depends on your GPU/RAM.

---

## 9.3 Orchestration Frameworks: LangChain & LlamaIndex
As your app gets complex, managing raw strings becomes difficult. Orchestration frameworks provide the "glue" to connect AI to the real world.

* **LangChain:** The "Swiss Army Knife." It helps you chain prompts together and gives the AI "memory" (history of the chat).
* **LlamaIndex:** Optimized for **Data Retrieval**. If you want to build a bot that "talks to your PDFs," start here.

---

## 9.4 Agents: AI with Tools
The next evolution of LLMs is **Agents**. An Agent is an LLM that is given a set of tools (like a Python interpreter, a Web Search, or a Database query) and the autonomy to decide which tool to use to solve a goal.

* *Example:* "Find the latest stock price for Apple and compare it to its 5-year average." 
* *Agent Logic:* Search Web -> Get Price -> Calculate Average -> Summarize.

---

## 🛠 Hands-on: Building a Simple AI CLI Tool

In this exercise, we will use a Python script to call an LLM. You will need an API key (OpenAI/Anthropic) or **Ollama** running locally.

```python
import os
import requests

# Example using a local Ollama instance
def ask_ai(prompt):
    url = "http://localhost:11434/api/generate"
    payload = {
        "model": "llama3",
        "prompt": prompt,
        "stream": False
    }
    
    response = requests.post(url, json=payload)
    return response.json()['response']

user_input = input("Enter a technical question: ")
print("AI is thinking...")
print(ask_ai(user_input))
```

---

> **Note:** Now that you have the power to build, you have a responsibility to build safely. Our final chapter, Chapter 10, covers **AI Ethics, Security, and Future Trends**.
