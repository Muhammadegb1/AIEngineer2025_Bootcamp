# Installed Packages and Environment Setup

This document lists all the packages and versions used for this Section, along with instructions to create a virtual environment to run the code properly.

---

## Python Version

- `python=3.11`

---

## Installed Packages

All packages were installed in a conda environment:

| Package          | Version   |
|-----------------|-----------|
| openai           | 0.28      |
| config           | 0.5.1     |
| langchain        | 0.0.297   |
| pydantic         | 1.10.9    |
| tiktoken         | 0.5.1     |
| faiss-cpu        | 1.7.4     |
| transformers     | 4.47.1    |
| torch            | 2.5.1     |
| datasets         | 3.2.0     |
| evaluate         | 0.4.3     |
| accelerate       | 1.2.1     |
| ipywidgets       | 8.1.5     |
| matplotlib       | 3.10.0    |
| seaborn          | 0.13.2    |
| clean-text       | 0.6.0     |
| scikit-learn     | 1.6.0     |
| sentencepiece    | 0.2.0     |
| pandas           | 2.0.0     |

---

## Conda Environment Setup

Virtual environments help manage different package versions for different projects. Follow these steps to set up an environment for this Section:

```bash
# Create the conda environment
conda create --name llms_course_env python=3.11

# Activate the environment
conda activate llms_course_env

# Install required packages
pip install openai==0.28 config==0.5.1 langchain==0.0.297 pydantic==1.10.9 tiktoken==0.5.1 faiss-cpu==1.7.4 transformers==4.47.1 torch==2.5.1 datasets==3.2.0 evaluate==0.4.3 accelerate==1.2.1 ipywidgets==8.1.5 matplotlib==3.10.0 seaborn==0.13.2 clean-text==0.6.0 scikit-learn==1.6.0 sentencepiece==0.2.0 pandas==2.0.0

# Install Jupyter tools
pip install ipykernel jupyterlab notebook
python -m ipykernel install --user --name=llms_course_env

# Regi
