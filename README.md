# Special Topics in Data Science

A Python environment for hands-on training in modern data science and large language model workflows. The included dependencies support exploratory notebooks, Hugging Face models and datasets, embeddings, fine-tuning, retrieval-augmented generation (RAG), and Modal-based cloud execution.

## Topics

- Data science with NumPy, pandas, matplotlib, and scikit-learn
- Interactive notebook development with Jupyter and IPython kernels
- Model and dataset workflows with PyTorch and Hugging Face
- Sentence embeddings with Sentence Transformers
- Parameter-efficient fine-tuning with PEFT and TRL
- RAG applications with LangChain, ChromaDB, and PDF ingestion
- Cloud execution with Modal

## Setup

Prerequisites: Python 3.10 or later and `pip`.

```
git clone https://github.com/steveprempeh23/Special_Topics_DataScience.git
Set-Location "Special_Topics_DataScience"
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

On macOS or Linux, activate the virtual environment with:

```
source .venv/bin/activate
```

## Use Jupyter

After activating the environment, launch Jupyter Lab:

```
jupyter lab
```

When creating a notebook, select the Python kernel associated with this project's `.venv` environment.

## Dependencies

```
# General Data Science
numpy
pandas
matplotlib
scikit-learn

# Jupyter
jupyter
ipykernel

# Hugging Face
torch
transformers
datasets
huggingface_hub
accelerate
evaluate

# Embeddings
sentence-transformers

# Fine-Tuning
peft
trl

# RAG
langchain
langchain-community
chromadb
pypdf

# Modal
modal
```

The full list is also maintained in [requirements.txt](requirements.txt). Install or update the environment whenever that file changes:

```
python -m pip install -r requirements.txt
```

Exact pinned versions from the last successful install are kept in [requirements-lock.txt](requirements-lock.txt).

## Optional Services

Some workflows require their own authentication before use:

- Hugging Face: authenticate with `huggingface-cli login` when accessing gated models or publishing assets.
- Modal: authenticate with `modal setup` before running cloud functions.