# Data Science and Hugging Face Environment Setup

## Overview

This repository contains an environment setup for working with Python, data science tools, and the Hugging Face ecosystem.

The purpose of this project is to create a GitHub repository, set up an isolated Python environment, install the required packages, manage dependencies using a `requirements.txt` file, and document the setup clearly so that it can be recreated on another computer.

The environment created for this project is named `venv` and uses Python 3.12.

---

## Objectives

The main objectives of this project are to:

- Create a GitHub repository.
- Create an isolated Python environment.
- Install basic data science and machine learning packages.
- Install Hugging Face-related libraries (transformers, datasets, huggingface_hub, accelerate, evaluate).
- Install embedding, fine-tuning, and RAG tooling.
- Store project dependencies in a `requirements.txt` file.
- Document the environment setup and installation process.
- Make the project setup easy to reproduce.

---

## Repository Structure

```
ml-hf-project/
│
├── README.md
├── requirements.txt
├── requirements-lock.txt
├── .gitignore
├── notebooks/
└── src/
```

### `README.md`

Provides a detailed description of the project, environment setup, packages used, and instructions for recreating the environment.

### `requirements.txt`

Contains the Python packages required for the project environment, grouped by purpose.

### `requirements-lock.txt`

Contains the exact pinned versions of every package (and sub-dependency) from the last successful install, for byte-for-byte reproducibility.

### `notebooks/`

Exploration and experimentation notebooks.

### `src/`

Scripts and modules.

---

## Prerequisites

Before recreating this environment, the following should be available on the computer:

- Git
- Python 3.10+ (this workspace used Python 3.12)
- `pip` and `venv` (both ship with Python)
- Visual Studio Code or another code editor
- Internet connection for downloading packages
- A free Hugging Face account and access token (for authentication)

---

## Development Environment

A separate virtual environment was created for this project using Python's built-in `venv` module (a Conda environment works equally well if preferred — see the alternative commands below).

Environment name:

```
venv
```

Python version:

```
Python 3.12
```

The environment was created using:

```bash
python3 -m venv venv
```

The environment can be activated using:

macOS / Linux:

```bash
source venv/bin/activate
```

Windows (PowerShell):

```powershell
.\venv\Scripts\Activate.ps1
```

The Python version can be checked using:

```bash
python --version
```

**Conda alternative**, if you prefer Conda over venv:

```bash
conda create -n hf_project python=3.12 -y
conda activate hf_project
conda env list
```

When the environment is active, its name is shown at the start of the terminal prompt.

---

## Why a Separate Environment Was Used

A separate Python environment keeps the packages for this project isolated from packages used by other projects.

Different projects may require different Python versions or different versions of the same library. Using an isolated environment reduces the chance of dependency conflicts and makes the setup easier to reproduce on another machine.

---

## Package Installation

The packages required for the project are stored in:

```
requirements.txt
```

All dependencies can be installed using:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

After installation, the installed packages can be checked using:

```bash
pip list
```

This helps confirm that the required libraries were installed inside the active `venv` environment.

---

## Main Packages

The environment contains packages for data analysis, visualization, machine learning, notebooks, deep learning, Hugging Face workflows, embeddings, fine-tuning, RAG, and deployment.

| Package                | Purpose                                                        |
| ----------------------- | --------------------------------------------------------------- |
| NumPy                  | Numerical computing and array operations                       |
| Pandas                 | Data manipulation and analysis                                 |
| Matplotlib             | Data visualization                                              |
| Scikit-learn           | Machine learning and preprocessing tools                       |
| Jupyter / ipykernel    | Interactive notebook environment                                |
| PyTorch                | Deep learning framework                                         |
| Transformers           | Access to pretrained Hugging Face Transformer models            |
| Datasets               | Access to datasets hosted on Hugging Face                       |
| Hugging Face Hub       | Interaction with Hugging Face models and datasets                |
| Accelerate             | Simplified multi-device / mixed-precision training               |
| Evaluate               | Standardized metrics for model evaluation                        |
| Sentence-Transformers  | Sentence and text embeddings                                     |
| PEFT                   | Parameter-efficient fine-tuning (e.g. LoRA)                      |
| TRL                    | Transformer reinforcement learning / fine-tuning utilities       |
| LangChain / LangChain-Community | Building LLM-powered applications and RAG pipelines     |
| ChromaDB               | Vector database for embeddings and retrieval                     |
| pypdf                  | PDF reading/parsing, used in RAG document ingestion               |
| Modal                  | Cloud deployment and serverless compute for ML workloads          |

---

## Package Descriptions

### NumPy

NumPy is used for numerical computing and working with arrays. It is commonly used as a foundation for data science and machine learning tasks.

### Pandas

Pandas is used for data manipulation and analysis. It provides structures such as DataFrames for working with tabular data.

### Matplotlib

Matplotlib is used for creating plots, charts, and other data visualizations.

### Scikit-learn

Scikit-learn provides tools for machine learning, including preprocessing, data splitting, model evaluation, and traditional machine learning algorithms.

### Jupyter

Jupyter provides an interactive environment for writing and running Python code in notebooks. `ipykernel` registers the environment as a selectable notebook kernel.

### PyTorch

PyTorch is a deep learning framework used for building and running neural networks. It is also the underlying framework for most Hugging Face Transformer models.

### Transformers

The Hugging Face `transformers` library provides access to pretrained Transformer models.

These models can be used for tasks such as:

- Text classification
- Sentiment analysis
- Question answering
- Text generation
- Translation
- Summarization

### Datasets

The Hugging Face `datasets` library provides tools for downloading, loading, and working with datasets available on the Hugging Face Hub.

### Hugging Face Hub

The `huggingface_hub` package provides tools for interacting with models, datasets, and other resources hosted on Hugging Face, including authentication and file uploads/downloads.

### Accelerate

`accelerate` simplifies running PyTorch training code across different hardware setups (CPU, single GPU, multi-GPU) without changing the training loop.

### Evaluate

`evaluate` provides a standard interface for computing common ML metrics (accuracy, F1, BLEU, ROUGE, etc.).

### Sentence-Transformers

Used to generate dense vector embeddings of sentences and paragraphs, commonly used for semantic search and retrieval.

### PEFT

`peft` (Parameter-Efficient Fine-Tuning) enables fine-tuning large models with methods like LoRA, reducing compute and memory requirements.

### TRL

`trl` provides utilities for fine-tuning transformer models with reinforcement learning and supervised fine-tuning techniques.

### LangChain / LangChain-Community

Frameworks for chaining LLM calls, tools, and retrieval steps together into applications, including RAG pipelines.

### ChromaDB

An open-source vector database used to store and query embeddings for retrieval-augmented generation.

### pypdf

Used to extract text from PDF files, typically as a document-loading step before chunking and embedding for RAG.

### Modal

A cloud platform for running Python code (including ML training/inference) on remote compute without managing servers directly.

---

## Hugging Face Preparation

The environment includes the main packages required to begin working with Hugging Face.

These include:

```
transformers
datasets
huggingface_hub
torch
accelerate
evaluate
```

**Authentication**

To access gated models/datasets or push to the Hub, authenticate with a personal access token from https://huggingface.co/settings/tokens:

```bash
huggingface-cli login
```

Or, programmatically:

```python
from huggingface_hub import login
login(token="YOUR_TOKEN")
```

**Quick smoke test** once authenticated and connected:

```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")
print(classifier("Hugging Face makes NLP accessible."))
```

At this stage, the main focus is on preparing the working environment correctly. The installed Hugging Face packages support future practical work involving pretrained models and datasets — for example, exploring open model families such as Qwen or Gemma.

---

## Using `requirements.txt`

The `requirements.txt` file is used to record the Python dependencies needed for the project, grouped by category (general data science, Jupyter, Hugging Face, embeddings, fine-tuning, RAG, deployment).

Instead of installing each package manually, all required packages can be installed using:

```bash
pip install -r requirements.txt
```

This improves reproducibility because another user can recreate the required package setup using the same file.

The virtual environment itself is not uploaded to GitHub (it's excluded via `.gitignore`). The `requirements.txt` file and setup instructions provide everything needed to recreate it.

---

## Environment Verification

The environment can be verified using the following commands.

Check the Python version:

```bash
python --version
```

Check the installed packages:

```bash
pip list
```

Run an import check to confirm critical packages load correctly:

```bash
python -c "import numpy, pandas, matplotlib, sklearn, torch, transformers, datasets, huggingface_hub; print('imports OK')"
```

The expected result is an active `venv` environment running Python 3.12 with all required packages installed and importable.

---

## Recreating the Environment

The project environment can be recreated on another computer by following these steps.

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd ml-hf-project
```

### Step 2: Create the Virtual Environment

```bash
python3 -m venv venv
```

### Step 3: Activate the Environment

```bash
source venv/bin/activate      # macOS/Linux
.\venv\Scripts\Activate.ps1   # Windows PowerShell
```

### Step 4: Install the Dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Step 5: Authenticate with Hugging Face

```bash
huggingface-cli login
```

### Step 6: Verify the Setup

```bash
python --version
pip list
python -c "import torch, transformers; print('OK')"
```

The environment should now be ready for use.

---

## Git and GitHub

Git is used for version control, while GitHub is used to store the repository online.

A typical Git workflow is:

```bash
git status
git add .
git commit -m "Update project setup"
git push origin main
```

This allows changes to the project files to be tracked and synchronized with GitHub.

---

## Tools Used

- Python 3.12
- `venv` (Conda supported as an alternative)
- Git
- GitHub
- Visual Studio Code
- Hugging Face libraries (transformers, datasets, huggingface_hub, accelerate, evaluate)
- PyTorch
- Jupyter
- LangChain / ChromaDB (RAG)
- Modal (deployment)

---

## Expected Outcome

After completing the setup, the project has:

- A working GitHub repository.
- A virtual environment named `venv`.
- Python 3.12 installed in the environment.
- The required data science, Hugging Face, embedding, fine-tuning, RAG, and deployment packages installed.
- A `requirements.txt` file containing the project dependencies, and a `requirements-lock.txt` with exact pinned versions.
- Clear documentation explaining how to recreate the setup.

---

## Notes & Tips

- If you plan to use a GPU for PyTorch, ensure the appropriate CUDA/cuDNN drivers are installed and install a matching `torch` wheel from the official instructions: https://pytorch.org/get-started/locally/
- Some packages (`chromadb`, `modal`, GPU-enabled `torch`) may require system-level dependencies or optional extras.
- For large-model training and fine-tuning, consider cloud instances with sufficient RAM/GPU, or a service like Modal or Hugging Face Inference Endpoints.
- For reproducible, pinned dependency locking beyond `requirements-lock.txt`, tools like `pip-tools`, `poetry`, or `pipenv` are good options.

---

## Conclusion

This project sets up a Python development environment for data science and Hugging Face-related work. A GitHub repository was created, a dedicated virtual environment named `venv` was prepared using Python 3.12, the required packages were installed, and the dependencies were recorded in `requirements.txt` and `requirements-lock.txt`.

The completed setup provides a clean foundation for future practical work involving data analysis, machine learning, Hugging Face models, embeddings, fine-tuning, and RAG.
