# Chapter 3: Prompt Engineering Fundamentals

Now that you understand that AI is a "Next Token Predictor," you can see why the input you provide—the **Prompt**—is the most critical variable in the equation. Prompt Engineering is the craft of optimizing that input to get the most accurate, useful, and structured output possible.

---

## 3.1 The "Golden Rule" of Prompting
**Context is King.** A model cannot read your mind; it can only read your tokens. If you provide a vague prompt, you will get a vague (and likely hallucinated) answer.

* **Bad Prompt:** "Write a script to check server status."
* **Good Prompt:** "Write a Python script for a Linux sysadmin that checks if Nginx is running. If it's down, attempt to restart it and log the result to `/var/log/server_monitor.log`. Use the `subprocess` library."

---

## 3.2 The R-I-S-E Framework
When building a complex prompt, follow this structure:

1. **Role:** Assign a persona. (*"Act as a Senior DevOps Engineer."*)
2. **Input:** Provide the raw data or code. (*"Here is my current `docker-compose.yml` file..."*)
3. **Steps:** Give a numbered list of tasks. (*"1. Identify security risks. 2. Optimize image sizes."*)
4. **Expectation:** Define the output format. (*"Output the result as a Markdown table."*)

---

## 3.3 Core Techniques

### Few-Shot Prompting
Instead of describing what you want, **show** it. Provide 2-3 examples of the input/output pair before asking your actual question. This drastically improves the model's ability to follow a specific pattern.

### Chain-of-Thought (CoT)
Ask the model to **"Think step-by-step."** By forcing the AI to output its reasoning process before the final answer, you allow it to use more tokens for "thinking," which significantly reduces logic errors in math and coding.

### Delimiters
Use clear markers like `---`, `###`, or `"""` to separate instructions from the data you want the AI to process. 
* *Example:* "Summarize the text delimited by triple quotes: \"\"\" [Your Text Here] \"\"\""

---

## 3.4 Handling Output Formats
For engineers, raw text is often useless. You can force the AI to return structured data by explicitly requesting it:

* **JSON:** "Return the results in a valid JSON object with keys `bug_found` (boolean) and `fix_suggestion` (string)."
* **Tables:** "Compare React and Vue in a Markdown table focusing on learning curve and bundle size."

---

## 🛠 Hands-on: Prompting Exercises

Complete these 3 tasks in your AI tool of choice:

1. **The Role-Play:** Tell the AI it is a "Skeptical Code Reviewer." Paste a simple function and ask for a critique. Notice how the tone and depth change.
2. **The Chain-of-Thought:** Ask: "If I have 3 servers, and each can handle 100 requests per second, but one server is at 80% capacity and the others are at 20%, how many total additional requests can I handle before hitting 100% across the board? **Think step-by-step.**"
3. **The Formatter:** Give the AI a messy list of names and emails. Ask it to: "Extract these into a CSV format, sorted alphabetically by last name."

---

> **Note:** Prompting is just the beginning. In Chapter 4, we will learn how to build **Advanced Workflows** by chaining these prompts together and introducing external data.
