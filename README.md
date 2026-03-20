<div align="center">

# 🏡 Personalized Real Estate Agent — HomeMatch

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/OpenAI-GPT--4-412991?style=for-the-badge&logo=openai" />
  <img src="https://img.shields.io/badge/ChromaDB-Vector%20DB-1572B6?style=for-the-badge" />
  <img src="https://img.shields.io/badge/LangChain-RAG-1C3C3C?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" />
</p>

<p align="center">
  <strong>An AI real estate agent that transforms generic property listings into deeply personalized narratives — matching homes to buyers using LLMs, vector databases, and semantic search.</strong>
</p>

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Running the App](#running-the-app)
- [How It Works](#-how-it-works)
- [Example](#-example)
- [Project Structure](#-project-structure)
- [License](#-license)
- [Author](#-author)

---

## 🧠 Overview

**HomeMatch** is a Personalized Real Estate Agent that reinvents property discovery. Instead of surfacing raw listings, it uses a **RAG (Retrieval-Augmented Generation)** pipeline to:

1. Understand a buyer's lifestyle, preferences, and requirements through natural language
2. Semantically search a vector database of property listings
3. Generate **personalized, buyer-specific property descriptions** that highlight what matters most to that individual

The result: every buyer sees the same listing described differently - tailored to their unique priorities.

---

## ✨ Features

- 💬 **Natural language buyer intake** — capture preferences through conversational prompts
- 🔍 **Semantic property search** — vector similarity matching beyond keyword filters
- ✍️ **Personalized listing generation** — LLM rewrites listings to match buyer personality
- 🗄️ **Vector database storage** — ChromaDB for fast embedding retrieval
- 📊 **Synthetic listing generation** — LLM-generated realistic property data for testing
- 🖥️ **Notebook-based workflow** — clean, reproducible end-to-end pipeline

---

## 🏗️ Architecture

```
Buyer Preferences (Natural Language Input)
           │
           ▼
┌─────────────────────────┐
│   LLM Preference        │  ◄── Parse & extract structured buyer needs
│   Extractor             │       (location, size, budget, amenities)
└────────┬────────────────┘
         │  Structured Query
         ▼
┌─────────────────────────┐
│   Semantic Search       │  ◄── ChromaDB + OpenAI Embeddings
│   (Vector Retrieval)    │       Top-K matching listings retrieved
└────────┬────────────────┘
         │  Relevant Listings
         ▼
┌─────────────────────────┐
│   LLM Description       │  ◄── GPT-4 personalizes each listing
│   Personalizer          │       Tailored narrative per buyer profile
└────────┬────────────────┘
         │
         ▼
  Personalized Property Recommendations
```

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Language | Python 3.10+ |
| LLM | OpenAI GPT-4 / GPT-3.5-turbo |
| Vector Database | ChromaDB |
| Embeddings | OpenAI `text-embedding-ada-002` |
| LLM Framework | LangChain |
| Data Handling | pandas |
| Notebook | Jupyter |
| Environment | python-dotenv |

---

## 🚀 Getting Started

### Prerequisites

- `Python 3.10` or higher
- OpenAI API key
- pip or conda

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/YeshwanthrajG/Personalized-Real-Estate-Agent.git
cd Personalized-Real-Estate-Agent

# 2. Create a virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

**Core dependencies [`requirements`](./requirements.txt):**
```
langchain=0.0.305
openai=0.28.1
pydantic>=1.10.12
pytest>=7.4.0
sentence-transformers>=2.2.0
transformers>=4.31.0
chromadb==0.4.12
jupyter==1.0.0
tiktoken==0.4.0
```

### Configuration

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

### Running the App

```bash
# Launch Jupyter Notebook
jupyter notebook

# Open the main notebook and run all cells
```

---

## 🔍 How It Works

**Step 1 — Generate Listings**
The LLM generates a synthetic dataset of realistic real estate listings with attributes: bedrooms, bathrooms, neighborhood, price, features, and description.

**Step 2 — Embed & Store**
Listings are embedded using OpenAI's embedding model and stored in a ChromaDB vector collection for semantic retrieval.

**Step 3 — Capture Buyer Preferences**
The system prompts the buyer with structured questions:
- What neighborhood or city?
- Preferred property size?
- Must-have amenities?
- Lifestyle priorities (quiet street, walkability, pet-friendly)?

**Step 4 — Semantic Retrieval**
Buyer preferences are embedded and matched against the listing vectors — retrieving the top-K most semantically relevant properties.

**Step 5 — Personalized Description**
GPT-4 rewrites each retrieved listing's description to emphasize the features most relevant to that specific buyer's stated preferences — making every recommendation feel tailor-made.

---

## 💡 Example

**Buyer Input:**
> _"I'm a remote worker looking for a quiet 3-bedroom home near good coffee shops and parks. I have a dog and value natural light. Budget around $500K."_

**Personalized Output (for a matching listing):**
> _"This sun-drenched 3-bedroom retreat on Maple Avenue was made for the modern remote professional. Floor-to-ceiling windows bathe every workspace in natural light, while your dog will love direct access to Riverside Park just two blocks away. Artisan coffee at Blue Bottle is a 4-minute walk — your morning commute just got a lot shorter..."_

---

## 📁 Project Structure

```
Personalized-Real-Estate-Agent/
├── HomeMatch.ipynb             # Main project notebook
├── listings.csv                # Generated property listings (optional)
├── requirements.txt            # Python dependencies
├── .env.example                # Environment variable template
├── LICENSE               
└── README.md                   # Project documentation
```

---

## 📄 License

This project is licensed under the [`LICENSE`](./LICENSE).

---

## 👤 Author

[@YeshwanthrajG](https://github.com/YeshwanthrajG)
