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
```

Other providers include:

Anthropic (Claude)

Cohere

Google (Gemini)

Mistral via Hugging Face

### 2. Running a Local LLM

You can also run models like LLaMA or Mistral on your own machine using libraries such as:

llama.cpp

text-generation-webui

transformers (Hugging Face)

Python Example using Transformers:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
import torch

model_name = "TheBloke/Mistral-7B-Instruct-v0.1-GGUF"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

inputs = tokenizer("Hello, how are you?", return_tensors="pt")
outputs = model.generate(**inputs)
print(tokenizer.decode(outputs[0]))
```
Note: Running large models locally may require significant RAM or a GPU.

## ⚖️ Hosted vs Local LLMs

# ⚖️ Hosted LLM vs Local LLM

| Feature             | Hosted LLM (e.g., OpenAI, Anthropic) | Local LLM (e.g., LLaMA, Mistral)       |
|---------------------|--------------------------------------|----------------------------------------|
| **Setup**           | Simple, requires only API access     | Needs local setup and model download   |
| **Ease of Use**     | Very user-friendly                   | Requires technical knowledge           |
| **Performance**     | High performance, cloud-scaled       | Depends on local CPU/GPU               |
| **Cost**            | Pay-per-use or subscription          | Free to run after setup                |
| **Data Privacy**    | Data leaves your environment         | 100% local and private                 |
| **Customization**   | Limited (no fine-tuning)             | Full control, supports fine-tuning     |
| **Latency**         | Network-dependent                    | Low (on-device, no network delay)      |
| **Internet Access** | Required                             | Not required (offline-capable)         |
| **Scalability**     | Easy to scale via cloud              | Limited by local hardware              |

