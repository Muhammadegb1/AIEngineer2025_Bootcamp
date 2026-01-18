# LangGraph

This repository demonstrates how to build a **stateful chatbot** using **LangGraph**, with conditional routing, and graph-based logic.
The chatbot can remember previous conversations, summarize them, and manage branching flows.

---

## 📌 Graph Concepts

A **LangGraph** conversation graph consists of three main components:

1. **State** – holds all conversation info (`messages`, `summary`) and is passed between nodes.  
2. **Node** – a function that receives and updates the `State` (e.g., ask question, respond, summarize).  
3. **Edge** – connects nodes; can be linear or conditional (`path_map` / `Literal`).

---

## 💡 Conditional Routing & Graph Logic

- Example flow:  
  `START → ask_question → chatbot → ask_another_question → END`  
- Nodes can decide the next step dynamically.
- Enables **branching conversations** instead of linear flows.

---

## 🧠 Adding Memory to the Chatbot

### Problem
- Regular graph updates replace old messages with new ones.
- The chatbot “forgets” previous conversations.

### Solution
- Append new messages instead of replacing them.
- Use `add_messages` from `langgraph.graph`:

```python
from langgraph.graph import add_messages
state.messages = add_messages(state.messages, new_messages)
```

---

## 🛠️ Managing Messages Efficiently

### 1. Trim Messages
- keep only the last N messages.
- Use `RemoveMessage` to delete older messages while keeping the recent context.

### 2. Summarizing Messages
- Instead of storing all messages, maintain a summary of the conversation.
- Delete old messages from the state; only the summary persists.
- Maintains long-term context with minimal resources.

### 💾 Thread-Level Persistence
LangGraph allows saving conversation state per **thread_id**, so the chatbot remembers context across sessions or restarts.

- After each node, a **StateSnapshot** is created containing:
  - `messages`, `summary`
  - `step` (current node)
  - `next_node` (next node to run)
- Snapshots are grouped by thread; each thread represents one continuous conversation.
- Running the graph again with the same thread_id:
  1. Retrieves the last checkpoint.
  2. Uses it as input for the graph.
  3. Resumes the conversation from where it left off.

**Memory types:**

- **Short-term memory** – via `MemorySaver`, stored in memory only, cleared on restart.  
- **Long-term memory** – via `SQLiteSaver`, stored on disk, survives restarts.

## Getting Started

### Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/Muhammadegb1/AIEngineer2025_Bootcamp.git
cd langchain
```

### Conda Environment

Using a virtual environment is recommended to manage packages without affecting other projects.

Create and activate the environment:

```bash
conda create --name langgraph_env python=3.11.11
conda activate langgraph_env
```

Install the required packages:

```bash
pip install ipykernel jupyterlab notebook
python -m ipykernel install --user --name=langgraph_env

pip install langchain==0.3.25
pip install langchain_text_splitters==0.3.8
pip install langchain_core==0.3.60
pip install langsmith==0.3.42

pip install langgraph==0.4.8
pip install langgraph_prebuilt==0.2.2
pip install langgraph_checkpoint==2.0.26
pip install langgraph_sdk==0.1.70

pip install langchain_openai==0.3.17
pip install openai==1.81.0
pip install langgraph-checkpoint-sqlite
pip install python-dotenv
pip install mypy-ipython
pip install grandalf


```
Environment Variables:
Create a .env file and define your OpenAI API key:
```bash
OPENAI_API_KEY=your_api_key_here

```

