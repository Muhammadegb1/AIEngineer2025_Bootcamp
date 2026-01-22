# 📚 Vector Database with Pinecone

## 🔍 Overview
This repository summarizes key concepts and practical workflows related to **Vector Databases**, with a focus on **Pinecone** as a managed cloud-based vector database. The goal is to demonstrate how vector databases enable **semantic search** and power modern AI applications.

---
## 🧠 Semantic Search
Semantic search retrieves results based on **meaning**, not exact keyword matching.
- Finds conceptually similar content even when different words are used.
- Particularly effective for long texts and vague queries.
- Relies on **embeddings**, which convert data (text, images, audio) into numerical vectors.
---

## ☁️ What is Pinecone
**Pinecone** is a fully managed, cloud-native vector database built for fast and scalable similarity search.

### Key Capabilities
- Efficient storage and management of millions/billions of vectors.
- High-performance similarity search (low latency).
- Automatic scalability.
- Easy integration with AI/ML frameworks (Python, TensorFlow, PyTorch).

### Common Use Cases
- Fashion apps: find visually similar products.
- Music platforms: recommend similar songs.
- Customer support: retrieve relevant past answers.

---
## 📐 Distance Metrics
Vector databases measure similarity using distance metrics:
- **Euclidean Distance** – straight-line distance in space; useful for geometric clustering.
- **Cosine Similarity** – measures angle between vectors; ideal for text and recommendations.
- **Manhattan Distance** – city-block distance; useful when movement is constrained.
- **Dot Product** – computationally efficient similarity measure for high-dimensional data.
---

## 📊 Vector Dimensions
- Vector length = number of dimensions.
- Higher dimensions may improve accuracy but increase storage and compute costs.
- All vectors in an index must have the **same dimensionality**.
---

## 🧱 Index Management in Pinecone

An **index** is the core data structure in Pinecone used to store and search vectors.

### Index Lifecycle Best Practices
1. **Index Creation**  
   - Define index name, vector dimension, and similarity metric.

2. **Pre-creation Validation**  
   - Always check whether an index with the same name already exists to avoid conflicts.

3. **Index Deletion**  
   - Removing obsolete indexes helps maintain a clean and manageable environment.

4. **Operation Verification**  
   - After creating or deleting an index, verify the operation by listing available indexes.

5. **Dynamic Configuration**  
   - Store index name, dimensions, and similarity metric as variables to enable flexible reuse.

6. **Environment Constraints**  
   - Free and Serverless plans may restrict available cloud regions or configurations; parameters must align with these limitations.

### Core Index Operations
- **list_indexes()** – returns all existing indexes.
- **create_index()** – creates a new index with specified dimensions and similarity metric.
- **delete_index()** – deletes an existing index if present.

---

## 🔄 Embeddings & Upsert

### What is Upsert
**Upsert** is an operation that **inserts new vectors or updates existing ones** if they already exist in the index.

### Upsert Workflow
- Convert raw data (e.g., text) into embeddings.
- Each record includes:
  - **ID** – unique identifier.
  - **Vector** – numerical embedding.
  - **Metadata** – optional contextual information (language, category, etc.).
- Data is uploaded in **batches** to improve performance and reduce memory pressure.

Upsert operations form the foundation for building scalable semantic search and recommendation systems.

---
## 🔎 Semantic Search with Pinecone

### What is Semantic Search
Semantic search retrieves results based on **conceptual meaning** rather than exact keyword matching.
- Finds semantically related content even when different words are used.
- Especially effective for long, unstructured, or ambiguous queries.

### Query Embedding
- The search query must be converted into an **embedding** using the same model as the indexed data.
- The embedding dimension **must match** the index dimension exactly.

### Querying the Index
Queries are executed using `index.query()` with key parameters:
- **vector** – the embedding representation of the query.
- **top_k** – number of most similar results to retrieve.
- **include_values** – whether to return the stored vectors as part of the response.

### Result Structure
- The query response is returned as a dictionary containing a `matches` field.
- Each match includes:
  - **id** – unique identifier of the vector (e.g., course or document ID).
  - **score** – similarity score between the query and the result.
  - **values** – the vector itself (if `include_values=True`).
---

## Getting Started

### Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/Muhammadegb1/AIEngineer2025_Bootcamp.git
cd VectorDataBase
```

### Conda Environment

Using a virtual environment is recommended to manage packages without affecting other projects.

Create and activate the environment:

```bash
conda create --name vectorDataBase python
conda activate vectorDataBase
```
Install the required packages:

```bash
pip install python-dotenv ipykernel jupyterlab notebook
python -m ipykernel install --user --name=vectorDataBase

pip install pinecone
pip install datasets
pip install sentence-transformers
```
Environment Variables:
Create a .env file and define your Pinecone API key:
```bash
PINECONE_API_KEY=your_pinecone_api_key_here
```
