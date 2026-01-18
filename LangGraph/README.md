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
