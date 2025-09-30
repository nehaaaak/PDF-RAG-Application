# 📄 PDF RAG Application

A **Retrieval-Augmented Generation (RAG)** application for ingesting PDFs, chunking their content, embedding them into **Qdrant**, and querying them via an **event-driven pipeline with Inngest**.  
The project provides a **Streamlit interface** for PDF upload and ingestion.

---

## 🚀 Features
- 📥 Upload PDFs through a **Streamlit app**  
- ✂️ Chunk documents into manageable sections  
- 🔍 Generate embeddings and store them in **Qdrant vector DB**  
- ⚡ Event-driven ingestion workflow using **Inngest**  
- 🎯 Ready for integration with LLMs (Gemini / OpenAI)  

---

## 🛠️ Tech Stack
- [Python 3.12+](https://www.python.org/)  
- [Streamlit](https://streamlit.io/) – UI for uploading PDFs  
- [Qdrant](https://qdrant.tech/) – Vector database for storing embeddings  
- [Inngest](https://www.inngest.com/) – Event-driven ingestion pipeline  
- [uv](https://github.com/astral-sh/uv) – Fast Python package/environment manager

---

## ⚙️ Setup

### 1. Clone the repo
```bash
git clone https://github.com/nehaaaak/PDF-RAG-Application.git
cd PDFRAGApplication
```

### 2. Setup a new project structure
```bash
uv init
```

### 3. Install dependencies
```bash
uv pip install -r pyproject.toml
```

### 4. Start Qdrant (Docker recommended)
```bash
docker run -p 6333:6333 -p 6334:6334 qdrant/qdrant
```

### 5. Configure .env
Create a .env file in the project root to put your GeminiAPI key.

### 6. Run Streamlit app
```bash
streamlit run streamlit_app.py
```

---

## ▶️ Usage
- Open the Streamlit UI in your browser (usually at http://localhost:8501).
- Upload a PDF.
- The file is chunked, embedded, and ingested into Qdrant.
- Events are sent through Inngest to manage background workflows.

---

## 🧹 Development Notes
- .env, .venv/, qdrant_storage/, and __pycache__/ are excluded from version control via .gitignore.
- Embedding model dimension is set to 768 (compatible with Gemini embeddings).
- Default chunking: 1000 tokens with 200 overlap.
