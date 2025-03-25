
# 🐍 Conda Environment Setup Guide for Your Python Project

This guide will walk you through creating a Conda environment and installing all required libraries for your project.

---

## 📦 Step 1: Create `requirements.txt`

Create a file named `requirements.txt` in your project directory and paste the following:

```
requests
beautifulsoup4
python-dotenv
openai
langchain
langchain-community
faiss-cpu
streamlit
```

> 💡 *Optional additions:*
> - `tqdm` if you want progress bars
> - `pydantic` (sometimes required by LangChain or OpenAI dependencies)

---

## 💻 Step 2: Open VS Code Terminal

1. Open **Visual Studio Code**.
2. Open your project folder (where `requirements.txt` is located).
3. Open the terminal:  
   **View → Terminal** or press `` Ctrl + ` ``

---

## 🏗️ Step 3: Create a Conda Environment

In the terminal, run:

```bash
conda create -n condo-env python=3.10
```

> ✅ When prompted, type `y` to proceed.

---

## ⚙️ Step 4: Activate the Environment

```bash
conda activate condo-env
```

You should now see `(condo-env)` in your terminal prompt.

---

## 📥 Step 5: Install Requirements

```bash
pip install -r requirements.txt
```

> ⚠️ Note: We use `pip` here because some libraries (like `langchain-openai` or `faiss-cpu`) are not available via `conda`.

---

## ✅ Step 6: Verify Installation

Start Python:

```bash
python
```

Then test the imports:

```python
import streamlit as st
import requests
from bs4 import BeautifulSoup
from langchain.text_splitter import RecursiveCharacterTextSplitter
```

No errors? You're all set! 🚀

---

## ▶️ Optional: Run Your Streamlit App

```bash
streamlit run main.py
```

---

Happy Coding! 🧑‍💻✨
