# 📄 Retrieval-Augmented Generation (RAG)

A hands-on implementation of a **Document-Based RAG system** with a dedicated notebook for evaluating output quality.

---

## 📌 Overview

Retrieval-Augmented Generation (RAG) combines the power of large language models (LLMs) with information retrieval — allowing models to answer questions grounded in your own documents rather than relying solely on pre-trained knowledge.

This repository contains two Jupyter notebooks:

| Notebook | Description |
|---|---|
| `Document_Based_RAG_system.ipynb` | End-to-end pipeline for building a document-based RAG system: loading documents, chunking, embedding, indexing, and querying |
| `RAG_Output_Quality.ipynb` | Evaluation framework for assessing RAG output quality using metrics such as faithfulness, answer relevancy, and context recall |

---

## 🏗️ How RAG Works

```
User Query
    │
    ▼
[Retriever] ──▶ Vector Store ──▶ Relevant Document Chunks
    │
    ▼
[Generator] ──▶ LLM + Retrieved Context ──▶ Grounded Answer
```

1. **Ingestion** — Documents are loaded, split into chunks, and embedded into a vector store.
2. **Retrieval** — At query time, the most semantically similar chunks are retrieved.
3. **Generation** — The LLM generates an answer conditioned on the retrieved context.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab
- An `claude-4.5-sonnet` API key (or your preferred LLM provider such as Anthropic models, Gemini or Open AI)
    - In this project, Replicate platform was used to generate a API key for the `sonnet4.5` model.

### Installation

```bash
# Clone the repository

git clone https://github.com/Faridacoding/Retrieval-Augmented-Generation-RAG.git
cd Retrieval-Augmented-Generation-RAG

# Install dependencies
install core packages manually:

```bash
pip install langchain replicate faiss-cpu tiktoken pypdf sentence-transformers
```

### Set your API key

Add your API key to a `secrets` file in the Jupyter Notebook:

```
REPLICATE_API_TOKEN=your-api-key-here
```

---

## 📓 Notebooks

### 1. `Document_Based_RAG_system.ipynb`

Walks through building a complete RAG pipeline:

- **Document Loading** — Ingest PDFs, text files, or other document types
- **Text Splitting** — Chunk documents into manageable pieces
- **Embedding & Indexing** — Convert chunks into vector embeddings and store them
- **Retrieval** — Perform semantic search over the vector store
- **Generation** — Pass retrieved context to an LLM to produce answers

### 2. `RAG_Output_Quality.ipynb`

Evaluates the quality of RAG outputs across key dimensions:

- **Faithfulness** — Are the answers grounded in the retrieved context?
- **Answer Relevancy** — Does the answer address the question asked?
- **Context Recall** — Is the relevant information being retrieved?
- **Context Precision** — Is the retrieved context focused and free of noise?

---

## 🛠️ Tech Stack

- **LLM** — `sonnet4.5` (or compatible model)
- **Embeddings** — Sentence Transformers (`all-MiniLM-L6-v2`)
- **Vector Store** — FAISS
- **Framework** — LangChain Community
- **Evaluation** — custom metrics (Choose top 3 ranked results)
- **Language** — Python (Jupyter Notebooks)

---

## 📂 Project Structure

```
Retrieval-Augmented-Generation-RAG/
│
├── Document_Based_RAG_system.ipynb   # RAG pipeline implementation
├── RAG_Output_Quality.ipynb          # RAG evaluation metrics
└── README.md
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to open a pull request or raise an issue.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Built by [Faridacoding](https://github.com/Faridacoding)*
