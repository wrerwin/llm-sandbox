# OpenAI GPT-4 Repository Setup

This guide walks you through the process of setting up a Conda environment tailored for a project using the OpenAI GPT-4 API.

## Prerequisites

- [Git](https://git-scm.com/)
  
## 1. Installing Conda/Miniconda:

1. **Miniconda:** A minimal installer for conda.
    - [Miniconda Installation Guide](https://docs.conda.io/en/latest/miniconda.html)
    
2. **Anaconda (Optional):** A larger distribution that includes conda, Python, and many scientific packages.
    - [Anaconda Installation Guide](https://www.anaconda.com/products/distribution)
    
For most purposes, Miniconda is sufficient.

## 2. Clone the Repository:

To get a copy of this project, clone the repository to your local machine:

```bash
git clone https://github.com/wrerwin/llm-sandbox
cd llm-sandbox
```

## 3. Creating a Conda Environment:

Create a new Conda environment:

```bash
conda create --name openai_env python=3.8
```

Activate the Conda environment:

```bash
conda activate openai_env
```

## 4. Setting up the `OPENAI_API_KEY`:

For security reasons, it's recommended to set your OpenAI API key as an environment variable. This way, you don't accidentally expose the API key in your scripts or notebooks.

### On macOS and Linux:

```bash
cd $CONDA_PREFIX
mkdir -p ./etc/conda/deactivate.d  
mkdir -p ./etc/conda/activate.d  
touch -p ./etc/conda/activate.d/env_vars.sh 
touch -p ./etc/conda/deactivate.d/env_vars.sh 
```

Navigate to .`/etc/conda/activate.d/env_vars.sh` and edit it: 
```
export OPENAI_API_KEY=`<YOUR_OPENAI_API_KEY>`
```
Navigate to .`/etc/conda/deactivate.d/env_vars.sh` and edit it:
```
unset OPENAI_API_KEY
```

### On Windows (using Command Prompt):

```
setx OPENAI_API_KEY "<YOUR_OPENAI_API_KEY>"
```

## 5. Installing Dependencies:
Navigate to the repo directory, and install requirements.

```
pip install -r requirements.txt
```