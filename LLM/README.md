# 🧠 Introduction to Large Language Models (LLMs)

This repository provides a simple introduction to **Large Language Models (LLMs)**, how they can be used both locally and through hosted APIs, and the key differences between the two approaches.

---

## 🔍 What is an LLM?

A **Large Language Model** is an advanced type of AI trained on massive amounts of text data to understand, generate, and interact in natural language.

Popular LLMs include:

- [GPT-4 (OpenAI)](https://openai.com/)
- [Claude (Anthropic)](https://www.anthropic.com/)
- [LLaMA (Meta)](https://ai.meta.com/llama/)
- [Mistral](https://mistral.ai/)
- [Gemini (Google)](https://deepmind.google/technologies/gemini)

LLMs power chatbots, coding assistants, summarizers, and many other AI-driven tools.

---

## ⚙️ Examples of Using LLMs

### 1. Using a Hosted LLM (API-Based)

You can access models like GPT-4 using a hosted API service:

**Python Example with OpenAI:**
```python
import openai

openai.api_key = "your-api-key"

response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[{"role": "user", "content": "Tell me a joke."}]
)

print(response['choices'][0]['message']['content'])
