# LangChain Study Notes 🚀

This repository contains my **LangChain study notes and practical examples**, covering everything from Model I/O to advanced workflows like LCEL and RAG.  

## Introduction to LangChain
- Learned what **LangChain** is and why it is important for building **stateful, context-aware, and reasoning-capable** applications.
- Understood how LangChain enables chatbots to remember past interactions and respond using external data beyond the model’s training set.

## Core Features of LangChain
- Explored LangChain’s workflow for:
  - Creating **embeddings**
  - Storing data in **vector databases**
  - Retrieving relevant context for user queries
- Learned how **context-aware responses** are generated using embedded document retrieval.

## 🧠 Sections Covered

### 1️⃣ Model I/O

LangChain provides a simple and flexible interface for interacting with language models.

- **ChatOpenAI**  
  Integration with OpenAI chat-based language models.

- **Messages**
  - `SystemMessage` – defines instructions and behavior for the model  
  - `HumanMessage` – represents user input  
  - `AIMessage` – represents model responses  

- **Prompt Templates**  
  Reusable and parameterized templates for generating prompts.

- **Chat Prompt Templates**  
  Prompt templates designed specifically for chat-based workflows.

- **Few-Shot Chat Message Prompt Templates**  
  Providing example inputs and outputs to guide the model toward better responses.

---

### 2️⃣ Output Parsers

Output parsers transform raw LLM outputs into structured and reliable formats.

- **String Parser** – returns plain text output  
- **Comma-Separated List Parser** – converts text into a Python list  
- **DateTime Parser** – parses and validates datetime values as Python `datetime` objects  

---

### 3️⃣ LCEL (LangChain Expression Language)

LCEL enables **composable chains and runnables** for building flexible and readable workflows.

Key features include:

1. Piping a **Prompt → Model → Output Parser**  
2. **Batching** – processing multiple inputs at once  
3. **Streaming** – handling partial outputs in real time  
4. **Runnable & RunnableSequence** – sequential task execution  
5. **RunnablePassthrough** – passing inputs through chains  
6. **Graphing Runnables** – visualizing workflow execution  
7. **RunnableParallel** – executing tasks in parallel  
8. **RunnableParallel with Other Runnables** – combining parallel and sequential logic  
9. **RunnableLambda** – defining inline custom Python logic  
10. **`@chain` Decorator** – simplified syntax for defining reusable chains  

---

### 4️⃣ RAG (Retrieval-Augmented Generation)

RAG combines **retrieval from external knowledge sources** with **language model generation** to produce accurate and context-aware responses.

- **Indexing** – converting documents into embeddings for efficient search  
- **Retrieval** – finding relevant documents based on semantic similarity  
- **Generation** – generating responses grounded in retrieved context  

This approach enables **knowledge-enhanced LLM applications** beyond the model’s pretraining data.
---

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
conda create --name langchain_env python=3.10.10
conda activate langchain_env
```

Install the required packages:

```bash
pip install openai python-dotenv ipykernel jupyterlab notebook
python -m ipykernel install --user --name langchain_env

pip install "langchain>=0.3.0,<0.4.0"
pip install "langchain-openai>=0.3.0,<0.4.0"
pip install "langchain-community>=0.3.0,<0.4.0"
pip install grandalf
pip install pypdf
pip install docx2txt
pip install chromadb
```
Environment Variables:
Create a .env file and define your OpenAI API key:
```bash
OPENAI_API_KEY=your_api_key_here

```

Now you can run Jupyter Notebook or JupyterLab to explore the exercises.

---

## How to Run the Exercises

1. Activate the `langchain_env` environment.
2. Open Jupyter Notebook:

