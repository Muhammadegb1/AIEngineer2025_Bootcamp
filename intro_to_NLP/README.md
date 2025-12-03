# AI Engineer Course 2025 - NLP Exercises

This repository contains **learning exercises** from the **AI Engineer Course 2025: Complete AI Engineer Bootcamp** on Udemy.
The exercises are designed to help understand **Python for AI, NLP, and foundational AI concepts**.

---

## Repository Structure

```
/exercises
    ├── tokenization.py            # Exercises on text tokenization and splitting
    ├── stopwords_and_lemmatization.py  # Removing stopwords and lemmatization exercises
    ├── sentiment_analysis.py      # Using TextBlob, VADER, and Transformers for sentiment
    ├── ner_examples.py            # Named Entity Recognition (NER) examples
    ├── text_classification.py     # Simple text classification exercises
    ├── word2vec_gensim.py         # Word embeddings and similarity with Gensim
    ├── visualization.ipynb        # Data and text visualization exercises
    └── utils.py                   # Helper functions for NLP tasks
README.md
```

---

## What I Learned

These exercises helped me understand and practice:

* **Text Preprocessing**:

  * Tokenization, stopwords removal, lemmatization
  * Cleaning and normalizing text
* **Sentiment Analysis**:

  * Using TextBlob for polarity and subjectivity
  * VADER sentiment analysis for social media text
  * Transformers pipeline for more advanced sentiment tasks
* **Named Entity Recognition (NER)**:

  * Using spaCy to detect entities like names, organizations, locations
* **Text Representation**:

  * Word embeddings with Gensim (Word2Vec)
  * Simple text classification
* **Data Visualization**:

  * Visualizing token counts, sentiment distributions, and named entities with Matplotlib and Seaborn

---
## Topics Learned / Key Concepts

- **Lowercasing**: Converting all text to lowercase to standardize data for NLP tasks.  
- **StopWords**: Removing common words (like "the", "and") that do not add meaning to text analysis.  
- **Regular Expressions**: Using patterns to find, match, or clean text efficiently.  
- **Tokenizing Text**:  
  - **Sentence Tokenization**: Splitting text into sentences.  
  - **Word Tokenization**: Splitting sentences into individual words or tokens.  
- **Stemming (PorterStemmer)**: Reducing words to their root form (e.g., "running" → "run").  
- **Lemmatization (WordNetLemmatizer)**: Reducing words to their base or dictionary form while considering context.  
- **N-grams**: Sequences of N consecutive words used for text analysis and feature extraction.  
- **POS Tagging (spaCy, NLP)**: Identifying parts of speech (noun, verb, adjective, etc.) in text.  
- **NER (Named Entity Recognition)**: Detecting entities like names, locations, organizations in text.  
- **Rule-Based Sentiment**:  
  - **TextBlob**: Lexicon-based approach for polarity and subjectivity.  
  - **VADER**: Sentiment analysis optimized for social media text.  
- **Pre-trained Transformer Models (pipeline)**: Using Hugging Face Transformers for advanced NLP tasks like sentiment analysis and text classification.  
- **Bag of Words (CountVectorizer)**: Representing text as a matrix of token counts.  
- **TF-IDF (TfidfVectorizer)**: Weighting words by importance, reducing the impact of common words.  
- **LDA (Latent Dirichlet Allocation, gensim)**: Topic modeling to discover hidden topics in text.  
- **LSA (Latent Semantic Analysis)**: Dimensionality reduction technique to capture semantic meaning of words.  
- **Custom Classifier (Combined)**: Building a custom text classifier combining multiple preprocessing and modeling techniques.  

---
## Getting Started

### Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/your-username/ai-engineer-nlp.git
cd ai-engineer-nlp
```

### Conda Environment

Using a virtual environment is recommended to manage packages without affecting other projects.

Create and activate the environment:

```bash
conda create --name nlp_course_env python=3.11
conda activate nlp_course_env
```

Install the required packages:

```bash
pip install nltk==3.9.1 pandas==2.2.3 matplotlib==3.10.0 spacy==3.8.3 textblob==0.18.0.post0 vaderSentiment==3.3.2 transformers==4.47.1 scikit-learn==1.6.0 gensim==4.3.3 seaborn==0.13.2 torch==2.5.1 ipywidgets==8.1.5
python -m spacy download en_core_web_sm
pip install ipykernel jupyterlab notebook
python -m ipykernel install --user --name=nlp_course_env
```

Now you can run Jupyter Notebook or JupyterLab to explore the exercises.

---

## How to Run the Exercises

1. Activate the `nlp_course_env` environment.
2. Open Jupyter Notebook:

```bash
jupyter notebook
```

3. Navigate to the `/exercises` folder and open any `.py` or `.ipynb` file to run the exercises.

---
