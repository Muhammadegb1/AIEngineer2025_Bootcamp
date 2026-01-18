# LangGraph - Stateful Chatbot with Long-Term Memory

This repository demonstrates how to build a **stateful chatbot** using **LangGraph**, with long-term memory, conditional routing, and graph-based logic. The chatbot can remember previous conversations, summarize them, and manage branching flows.

---

## 📌 Graph Concepts

A **LangGraph** conversation graph consists of three main components:

### 1. State
- Holds all conversation information.
- Passed between nodes so each node can read and update it.
- Typical fields:
  - `messages` – the list of all exchanged messages.
  - `summary` – a condensed summary of the conversation.

### 2. Node
- Represents a single step in the flow (a function).
- Receives a `State` and returns an updated `State`.
- Performs one action: ask a question, provide an answer, or summarize messages.

### 3. Edge
- Connects nodes.
- Determines the next node to execute.
- Can be:
  - Linear (simple flow)
  - Conditional using `path_map` or `Literal` (recommended)

---

## 🔹 Key Components

- **TypedDict** – defines the structure of the `State`.
- **StateGraph** – builds the graph structure.
- **START / END** – marks entry and exit points.
- **ChatOpenAI** – LLM used as the chatbot.
- **HumanMessage** – user input.
- **BaseMessage** – base class for all messages.
- **Runnable** – functions used as nodes.
- **Sequence** – type for storing multiple messages.
- **Literal** – restricts a variable to predefined values only.

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
- Keep only the last N messages (e.g., 5) to reduce token usage.
- Use `RemoveMessage` to delete older messages while keeping the recent context.

### 2. Summarizing Messages
- Instead of storing all messages, maintain a summary of the conversation.
- Delete old messages from the state; only the summary persists.
- Maintains long-term context with minimal resources.

### 💾 Thread-Level Persistence
- Saves conversation state per `thread_id`.
- The chatbot remembers context between sessions or page reloads.
- Implemented via Checkpoints:
  - Each snapshot includes:
    - `state` (messages, summary)
    - `thread_id`
    - `checkpoint_id`
    - `step` (node index)
    - `next_node`
- Restores conversation from the last snapshot.

