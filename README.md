# Enterprise-Secure-RAG-Intelligence-System



## Overview

A production-style Enterprise Retrieval-Augmented Generation (RAG) system designed to securely retrieve and generate grounded responses from multi-format enterprise datasets while enforcing strict Role-Based Access Control (RBAC).

This project simulates how large organizations can build secure AI assistants that interact with disconnected enterprise data silos including:

* PDFs & internal documents
* Structured CSV/SQL-style datasets
* JSON logs & audit trails
* Compliance records
* Operational datasets

The system intelligently retrieves context-aware information while preventing unauthorized data exposure.

---

# Key Features

## Multi-Format Enterprise Data Ingestion

* PDF document parsing
* CSV structured data ingestion
* JSON log ingestion
* Unified document representation

## Intelligent Semantic Retrieval

* Vector embeddings using Sentence Transformers
* FAISS vector database
* Semantic similarity search
* Query-aware routing

## Enterprise Security (RBAC)

* Role-Based Access Control
* Department-level authorization
* Restricted document retrieval
* Prevention of unauthorized context exposure

## Grounded Answer Generation

* Gemini-powered response generation
* Context-grounded answers
* Hallucination minimization
* Citation support

## Explainability

* Source attribution
* Retrieval traceability
* Confidence scoring
* Authorized department visibility

---

# Architecture

```text
User Query
    ↓
Query Routing
    ↓
Semantic Retrieval (FAISS)
    ↓
RBAC Filtering
    ↓
Authorized Context
    ↓
Gemini Response Generation
    ↓
Citations + Confidence Score
```

---

# Tech Stack

| Component               | Technology                 |
| ----------------------- | -------------------------- |
| Language                | Python                     |
| Development Environment | VS Code + Jupyter Notebook |
| Vector Database         | FAISS                      |
| Embeddings              | Sentence Transformers      |
| Framework               | LangChain                  |
| LLM                     | Google Gemini 2.5 Flash    |
| Data Processing         | Pandas                     |
| PDF Parsing             | PyPDF                      |

---

# Project Structure

```text
enterprise_rag_challenge/
│
├── data/
│   ├── pdfs/
│   ├── csv/
│   ├── json/
│
├── notebooks/
│   └── rag.ipynb
│
├── outputs/
│
├── users.json
├── access_policies.json
├── requirements.txt
```

---

# Dataset

Synthetic enterprise datasets were created to simulate realistic enterprise environments.

## Included Data Sources

### PDF Documents

* HR policies
* Finance audit reports
* Engineering architecture documents
* Compliance & security policies

### CSV Data

* Employee datasets
* Finance transactions
* Operational inventory records

### JSON Logs

* Security alerts
* Audit trails
* API/system logs

---

# RBAC Design

The system enforces strict access control using:

* User-role mapping
* Department-level authorization
* Retrieval filtering before LLM generation

Example:

| User    | Role        | Accessible Departments |
| ------- | ----------- | ---------------------- |
| Alice   | HR          | HR                     |
| Bob     | Finance     | Finance                |
| Charlie | Engineering | Engineering            |
| Admin   | Admin       | All Departments        |

Unauthorized enterprise data is never exposed to the language model.

---

# Retrieval Pipeline

## Step 1 — Data Ingestion

Enterprise data from PDFs, CSVs, and JSON files is loaded into unified LangChain documents.

## Step 2 — Chunking

Documents are split into semantic chunks using RecursiveCharacterTextSplitter.

## Step 3 — Embeddings

SentenceTransformer embeddings are generated using:

```python
all-MiniLM-L6-v2
```

## Step 4 — Vector Database

Embeddings are stored in FAISS for efficient semantic retrieval.

## Step 5 — Secure Retrieval

Retrieved chunks are filtered through RBAC policies before answer generation.

## Step 6 — Grounded Generation

Gemini generates answers strictly from authorized retrieved context.

---

# Hallucination Prevention

The system minimizes hallucinations using:

* Context-grounded prompting
* Restricted retrieval
* Explicit answer constraints
* Source-based generation

---

# Explainability Features

* Source citations
* Confidence indicators
* Retrieval traceability
* Authorized department tracking

---

# Installation

## Clone Repository

```bash
git clone <your-github-repo-link>
```

## Create Virtual Environment

```bash
python -m venv venv
```

## Activate Environment

### Windows

```bash
venv\Scripts\activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Running The Project

Open:

```text
notebooks/rag.ipynb
```

Run notebook cells sequentially.

---

# Future Improvements

* Hybrid search (BM25 + Vector Search)
* SQL database integration
* Multi-agent query routing
* Streamlit enterprise dashboard
* Real-time enterprise ingestion pipelines
* Advanced policy-based access control
* Document-level encryption

---

# Learning Outcomes

This project demonstrates practical understanding of:

* Retrieval-Augmented Generation (RAG)
* Semantic search systems
* Vector databases
* Enterprise AI architecture
* RBAC security enforcement
* Explainable AI systems
* LLM grounding strategies
* Multi-source enterprise retrieval

---

# Author

Ridhi P

AI/ML • Data Science • Generative AI
