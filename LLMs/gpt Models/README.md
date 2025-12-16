# AI Conversational System & LangChain Mini-Project

This mini-project demonstrates practical use of **OpenAI GPT models** and **LangChain** to build an intelligent conversational system that can answer questions based on documents (RAG).

---

## What I Learned

- **Temperature:** Controls the creativity of model responses (0 = safe, predictable, 1 = highly creative).  
- **LangChain Concepts:**
  - **Documents → Chunks → Embeddings → Vector Store → LLM**
  - Split long texts into chunks for better performance.
  - Convert chunks into embeddings (numerical vectors) for semantic search.
  - Store embeddings in a vector database (FAISS) to retrieve relevant information.
  - LLM uses retrieved chunks to generate accurate, context-aware answers.
- **Prototype Chatbot:**  
  - Maintains conversation context using memory.  
  - Responds to user questions based on document content.  
  - Functions as a conversational system, not yet a full interactive chatbot with UI.

---

## Key Skills Gained
- Text generation, summarization, and keyword extraction with GPT models.
- Few-shot learning using system, user, and assistant roles.
- Using embeddings and FAISS for semantic search.
- Understanding the RAG pipeline and context-aware AI responses.
- Building a prototype conversational system using LangChain.
