# LangChain vs LangGraph

A comparison between **LangChain** and **LangGraph**, two popular frameworks used to build Generative AI applications and complex Agentic AI systems.

---

## LangChain

LangChain is widely used for building **LLM-powered applications** such as chatbots, RAG systems, and automation tools. It provides utilities for prompts, LLMs, tools, and vector datastores.

---

### 🔧 Core Pipeline

A LangChain application typically involves **three main components**:

1. **Retrieve**
2. **Summarize**
3. **Answer / Output**

---

### 🔍 1. Retrieve

Handles bringing data into the system and preparing it for context retrieval.

- **Data Ingestion**  
  Load data from:  
  - PDFs  
  - Web scraping  
  - CSV / Excel  
  - 3rd-party APIs (Wikipedia, ArXiv)  
  Uses **document loaders** to parse the content.

- **Text Splitting**  
  Splits data into smaller chunks to fit within LLM context windows.

- **Vector Databases**  
  - Converts text into **vector embeddings**  
  - Stores them for **semantic search**  
  - Retrieves the most relevant context for LLM input.

---

### 🧠 2. Summarize (Chaining)

LangChain follows a **sequential execution model (DAG – Directed Acyclic Graph)**.

Common chains include:

- **Prompt Chain** – instructions for the LLM  
- **LLM Chain** – integrates the model  
- **Context Chain** – supplies retrieved context  

Execution is **strictly forward**, no loops or backtracking.

---

### 🟢 3. Output

It might use:

- Persistent memory  
- Passing prompts to a separate LLM  
- Generating the final response

<p align="center">
  <img src="https://github.com/GitMeP/GenAI-Foundations/blob/aa28cce0c24e89aabebb7bfa151ba8a986c5c1e3/images/Sequential.png" width="600">
</p>

---

## LangGraph

LangGraph is designed to build **stateful, multi-agent, agentic AI applications** where multiple agents cooperate to complete complex workflows.

---

### 🧩 Key Concepts

- Tasks  
- Nodes  
- Edges  
- Graph structure  

Unlike LangChain, LangGraph **does not have to follow a DAG**.  
It supports **backtracking, loops, iterative refinement**, and more.

---

### 🔁 Feedback & Multi-Agent Control

- Agents can move back and forth between tasks  
- Output from one agent can feed another  
- Full support for **feedback loops**  
- Supports **human-in-the-loop** workflows  

This makes LangGraph ideal for building advanced **Agentic AI systems**.

<p align="center">
  <img src="https://github.com/GitMeP/GenAI-Foundations/blob/aa28cce0c24e89aabebb7bfa151ba8a986c5c1e3/images/Agentic.png" width="700">
</p>

---

## 🆚 Summary Comparison

| Feature | LangChain | LangGraph |
|--------|-----------|-----------|
| Execution Model | Sequential (DAG) | Non-linear / loop-capable graph |
| Typical Use Case | RAG, LLM apps, simple workflows | Multi-agent, complex workflows |
| Supports Loops | ❌ No | ✔️ Yes |
| Human Feedback | Basic | Strong support |
| Architecture | Chains | Nodes + Edges |

---

