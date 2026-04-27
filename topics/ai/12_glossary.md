# Chapter 12: Extended Glossary of AI Terms

This glossary is categorized to help you navigate the different "languages" of AI, from data science to production deployment.

---

## 12.1 Core Concepts & Architectures
| Term | Definition |
| :--- | :--- |
| **Attention Mechanism** | The math that allows a model to "focus" on specific parts of the input when generating an output. |
| **Deep Learning** | A subset of ML using multi-layered neural networks to learn complex patterns. |
| **Foundation Model** | A large-scale model (like GPT-4) trained on vast data that can be adapted to many different tasks. |
| **LLM** | Large Language Model. A transformer-based model trained on trillions of words. |
| **Multimodal** | AI that can "see," "hear," and "speak"—processing text, images, and audio in one system. |
| **Neural Network** | A computing system inspired by biological brains, composed of interconnected "neurons" or nodes. |
| **Parameters** | The internal variables (weights/biases) the model learns. GPT-4 has over 1 trillion parameters. |
| **Transformer** | The specific architecture (released in 2017) that uses "attention" to process sequences of data in parallel. |

---

## 12.2 Data & Training
| Term | Definition |
| :--- | :--- |
| **Backpropagation** | The primary algorithm used to train neural networks by calculating the "error" and adjusting weights. |
| **Bias** | Systematic errors in a model's output, usually caused by skewed or non-representative training data. |
| **Dataset** | The collection of information used to train (training set) or evaluate (test set) a model. |
| **Epoch** | One complete pass of the entire training dataset through the neural network. |
| **Fine-Tuning** | Taking a pre-trained model and training it further on a small, high-quality, task-specific dataset. |
| **Labeling** | The process of humans "tagging" data (e.g., drawing a box around a car) so the AI can learn from it. |
| **LoRA** | Low-Rank Adaptation. A method for fine-tuning models by only updating a tiny fraction of the weights. |
| **Loss Function** | A mathematical formula that measures how "wrong" the model's prediction was. |
| **Overfitting** | When a model memorizes the training data too perfectly and fails to work on new, real-world data. |
| **RLHF** | Reinforcement Learning from Human Feedback. Training a model based on human rankings of its answers. |
| **Synthetic Data** | Data created by an AI to be used for training other AI models. |
| **Weights** | Values that determine the importance of an input signal in a neural network. |

---

## 12.3 LLMs & Prompting
| Term | Definition |
| :--- | :--- |
| **Chain-of-Thought** | A prompting technique asking the AI to "think step-by-step" before providing a final answer. |
| **Context Window** | The "short-term memory" limit of a model, measured in tokens. |
| **Embeddings** | Turning text into a list of numbers (vectors) so a computer can calculate the "distance" between meanings. |
| **Few-Shot** | Providing 2-3 examples of a task within the prompt to help the AI understand the pattern. |
| **Hallucination** | When an AI generates a response that is factually incorrect but sounds highly confident. |
| **Next Token Prediction** | The core logic of an LLM: guessing the most likely next piece of text based on what came before. |
| **Prompt Injection** | A security hack where a user tricks the AI into ignoring its rules or revealing secrets. |
| **RAG** | Retrieval-Augmented Generation. Connecting an LLM to a search engine or database to provide factual context. |
| **System Message** | The hidden "hidden instructions" that tell an AI how to behave (e.g., "You are a helpful assistant"). |
| **Token** | A chunk of text (approx. 4 characters). The basic unit of "currency" in AI processing. |
| **Zero-Shot** | Asking an AI to do something without giving it any examples or special training. |

---

## 12.4 Deployment & MLOps
| Term | Definition |
| :--- | :--- |
| **Agent** | An LLM wrapped in code that can use tools (web search, API calls) to solve a goal autonomously. |
| **Compute** | The raw processing power (usually GPUs like the H100) required to train or run an AI. |
| **GPU** | Graphics Processing Unit. The hardware chip optimized for the parallel math used in AI. |
| **Inference** | The act of "running" the model to get an answer (as opposed to "training" the model). |
| **Latent Space** | The multi-dimensional "map" where a model stores all the concepts it has learned. |
| **Quantization** | Compressing a model to make it run faster and use less RAM, often by reducing the precision of its numbers. |
| **Temperature** | A setting (0.0 to 1.0) that controls how "creative" or random the AI's response is. |
| **Vector Database** | A specialized database (like Pinecone or Chroma) designed to store and search through embeddings. |

---

> **Final Note:** The world of AI creates new terms almost every day. If you find a term not listed here, use a model like Claude or GPT to ask: *"Explain [term] to me in the context of a Software Engineer."*
