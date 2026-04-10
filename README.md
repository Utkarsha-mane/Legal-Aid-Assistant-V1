# ⚖️ Legal Aid Assistant

An AI-powered RAG (Retrieval-Augmented Generation) chatbot that lets legal professionals upload case documents and query them instantly using natural language - fully offline, fully private.

> By Team ImpactIQ 

---


## 🧩 The Problem

Legal professionals - lawyers, investigators, judges, and paralegals, often inherit ongoing cases that span hundreds of pages: FIRs, charge sheets, witness statements, hearing notes, and past judgments. Manually reading and summarizing these is time-consuming, error-prone, and causes real delays in hearings, bail decisions, and investigations.

With over 5 crore cases pending in Indian courts (NJDG, 2024), the need for faster, smarter document review is urgent. Yet existing AI tools can't be used directly because legal documents are sensitive and must stay private.

---


## 💡 The Solution

Legal Aid Assistant is a secure, fully local RAG pipeline that:

- **Ingests** PDF case files (FIRs, charge sheets, judgments, etc.)
- **Chunks and embeds** the content using a local embedding model
- **Stores vectors** in a FAISS index for fast semantic search
- **Answers natural language queries** using a locally-running LLM, strictly grounded in the uploaded document
- **Never sends your data anywhere** — everything runs on your machine

---


## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend API | FastAPI + Uvicorn |
| PDF Parsing | PyMuPDF (fitz) |
| Embeddings | Ollama — `nomic-embed-text` |
| Vector Store | FAISS (faiss-cpu) |
| LLM / Generation | Ollama — `llama3:8b` |
| Data Validation | Pydantic |
| HTTP Client | Requests |
| Numerics | NumPy |

> All AI models run locally via [Ollama](https://ollama.com). No external API calls, no data leaving your machine.

---

## 🗂️ Project Structure
Legal-Aid-Assistant-V1/

├── app.py           # FastAPI app entry point

├── ui.py            # Frontend UI layer

├── chunking.py      # Document chunking logic

├── embeddings.py    # Ollama nomic-embed-text wrapper

├── vector_store.py  # FAISS index management

├── retrieval.py     # Semantic search / retrieval

├── generation.py    # LLaMA3 answer generation via Ollama

└── requirements.txt


---

## ⚙️ Setup & Installation

### Prerequisites

- Python 3.9+
- [Ollama](https://ollama.com) installed and running

### 1. Pull the required models

```bash
ollama pull nomic-embed-text
ollama pull llama3:8b
```

### 2. Clone the repo

```bash
git clone https://github.com/Utkarsha-mane/Legal-Aid-Assistant-V1.git
cd Legal-Aid-Assistant-V1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the app

```bash
uvicorn app:app --reload
```

---

## 🔄 How It Works
<img width="1408" height="768" alt="Gemini_Generated_Image_rby6eorby6eorby6" src="https://github.com/user-attachments/assets/fc9cb53c-359f-4219-8827-3d61296f7882" />


## 🔒 Privacy & Security

- **100% offline**, no data is sent to any external server or API
- All processing happens locally on the user's machine
- Designed for deployment in restricted, air-gapped court/legal environments
- Future versions will include role-based access control (lawyer / police / judge)

---

## 👥 Target Users

- Lawyers managing multi-file cases
- Police officers and investigators reviewing FIRs and charge sheets
- Judges and court officials needing quick case context
- Legal interns and paralegals doing case research

---

## 🚀 Roadmap

- [ ] Role-based login (lawyer, police, judge)
- [ ] Multi-document support with cross-file querying
- [ ] Case timeline auto-extraction
- [ ] Fine-tuned legal embedding model
- [ ] Audit logs for access tracking

---




