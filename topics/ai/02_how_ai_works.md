# Chapter 2: Under the Hood - Tokens, Transformers, and Intuition

To build effectively with AI, you don't need a PhD in Mathematics, but you do need a solid **mental model** of what is happening behind the scenes. Modern AI isn't "thinking"; it is calculating probabilities.

---

## 2.1 Tokens: The Currency of AI
AI models don't "read" letters or words like humans do. They process text in chunks called **Tokens**. 

* A token can be a whole word, a part of a word (like "ing"), or even a single punctuation mark.
* **The Rule of Thumb:** 1,000 tokens is roughly equal to 750 words.
* **Why it matters:** Most AI APIs charge you per token, and every model has a "Context Window" (a limit on how many tokens it can remember at one time).



---

## 2.2 Embeddings: Mapping Meaning to Math
How does a computer understand that "King" is related to "Queen" or that "Python" is closer to "Java" than it is to "Banana"? It uses **Embeddings**.

Every token is converted into a long list of numbers (a vector). These numbers act as coordinates in a multi-dimensional space. 
* Words with similar meanings are placed close together in this "map."
* When you ask a question, the AI looks for tokens that are mathematically nearby your query.



---

## 2.3 The Transformer: The Secret Sauce
Before 2017, AI processed text one word at a time (like reading a sentence through a straw). The **Transformer architecture** changed everything by introducing **Attention**.

* **Self-Attention:** This allows the model to look at every word in a sentence simultaneously to decide which ones are most important. 
* *Example:* In the sentence "The **bank** of the river was muddy," the word "river" tells the AI that "bank" refers to land, not a financial institution.

---

## 2.4 Next Token Prediction (The "Auto-Complete" on Steroids)
At its core, a Large Language Model (LLM) is a world-class guessing machine. Given a string of text, its only job is to predict the **next most likely token**.

1.  **Input:** "The best programming language for beginners is..."
2.  **Calculation:** The model looks at its training data and calculates probabilities.
3.  **Result:** * Python (85%)
    * JavaScript (10%)
    * C++ (2%)
4.  **Action:** It picks "Python" and then repeats the process for the next word.

---

## 2.5 Limitations: Hallucinations and Logic
Because LLMs are probabilistic, not deterministic, they have two major "features" you must account for:

* **Hallucinations:** If the model doesn't have a high-probability answer, it might still pick a token that *sounds* right but is factually false. It prioritizes "sounding human" over "being correct."
* **No Active "Thinking":** The AI doesn't have a world model or a "brain" that checks for truth. It only knows what token usually comes next in a sequence based on its training.

---

## 🛠 Hands-on: Visualizing the Logic

1.  **Tokenization:** Visit [OpenAI's Tokenizer](https://platform.openai.com/tokenizer). Paste a snippet of your code and see how it is broken down. Notice how common code syntax (like `unsigned int`) might be fewer tokens than a weirdly spelled variable name.
2.  **The "Next Word" Game:** Go to your AI tool and give it an incomplete sentence: *"In the history of computer science, the most influential person was..."*
    * Ask it to give you the top 3 possibilities it considered for the next word.
3.  **Context Test:** Give it a long paragraph of text, then ask it a question about a tiny detail in the middle. This tests its "Attention" mechanism.

---

> **Note:** Now that you know how AI "reads," Chapter 3 will show you how to write to it using **Prompt Engineering Fundamentals**.
