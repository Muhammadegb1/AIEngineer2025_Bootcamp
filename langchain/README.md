# LangChain Study Notes 🚀

This repository contains my **LangChain study notes and practical examples**, covering everything from Model I/O to advanced workflows like LCEL and RAG.  
Designed as a personal learning reference, but also useful for anyone starting with **LangChain**.

---

## 📦 Installation

### Conda Environment Setup
```bash
# Create a new environment with Python 3.10
conda create --name langchain_env python=3.10.10

# Activate environment
conda activate langchain_env

# Install basic dependencies
pip install openai python-dotenv ipykernel jupyterlab notebook

# Register the environment as a Jupyter kernel
python -m ipykernel install --user --name langchain_env
