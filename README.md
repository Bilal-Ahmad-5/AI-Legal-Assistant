# AI Legal Assistant (Law GPT)

> An AI-powered legal assistant that answers legal questions and augments responses with information from uploaded documents.

---

## 🚀 Overview

**AI Legal Assistant (Law GPT)** is designed to help users get fast, clear answers to legal questions. It combines pre-loaded legal knowledge with context pulled from user-uploaded documents (PDFs), using a retriever + language model pipeline and an Agentic RAG (Retrieval-Augmented Generation) setup to improve accuracy and relevance.

The app exposes a friendly Gradio interface so users can ask questions, upload files for context, and receive well-sourced, explainable responses.

---

## 🔑 Key Features

- **Answer legal questions** using pre-loaded legal data and knowledge sources.
- **PDF uploads**: Users can upload one or more PDFs to provide extra context for queries.
- **Retriever + LLM**: Uses a vector-based retriever to find relevant passages and an LLM to generate answers.
- **Agentic RAG**: Orchestrates retrieval and model reasoning to improve answer relevance and reduce hallucinations.
- **Gradio UI**: Simple and accessible web interface for interacting with the assistant.

---

## 🧩 Components

### 1. Data Loading

- Load pre-built legal corpora and documents uploaded by users.
- Preprocess text and metadata (title, author, date, source).

### 2. Text Splitting

- Break long documents into chunks (windows with overlap) suitable for embedding and retrieval.
- Ensure semantic coherence of chunks to improve retrieval quality.

### 3. Vector Database

- Embed chunks with a sentence-transformer or other embedding model.
- Store embeddings in a vector store (Chroma or compatible DB) for similarity search.

### 4. Retriever

- Semantic search over the vector DB to find the most relevant chunks for a given query.
- Optionally apply filtering by document metadata or source.

### 5. Agentic RAG

- Orchestrates retrieval, evidence selection, and LLM prompting.
- Applies safety checks and sources citations for generated answers.
- Uses chain-of-thought-style reasoning when appropriate while keeping answers concise for the user.

### 6. Gradio Interface

- Upload area for PDFs
- Query input box
- Response area that includes the answer, confidence, and cited excerpts from documents

---

## 📦 Dependencies

Minimum required Python packages (add to your `requirements.txt`):

```
langchain
langchain_core
langchain-community
langgraph
langchain-groq
langchain-chroma
chroma-db
langchain-huggingface
sentence-transformers
gradio
langchain-tavily
pypdf
```

## ⚙️ Installation & Quick Start

1. **Clone the repo**

```bash
git clone https://github.com/Bilal-Ahmad-5/AI-Legal-Assistant.git
cd AI-Legal-Assistant
```

2. **Set up virtual environment & install**

```bash
python -m venv venv
# macOS / Linux
source venv/bin/activate
# Windows
venv\Scripts\activate

pip install -r requirements.txt
```

3. **Set environment variables** (if needed for embedding/LLM providers)

```bash
export YOUR_LLM_API_KEY="your_api_key"
```

4. **Run the app**

```bash
python app.py
# or
streamlit run app.py  # if using Streamlit variant
```

---

## 📌 Usage Tips

- Keep uploaded PDFs reasonably sized for faster processing.
- If answers reference documents, the UI will show the exact excerpt used as evidence—review those snippets when accuracy is critical.
- Use clear, specific questions (e.g., "What are the notice requirements for eviction in State X?") to get more actionable results.

---

## 🔒 Security & Privacy

- Do **not** upload privileged or highly sensitive documents unless you control the hosting environment.
- Consider encrypting uploads at rest or using ephemeral storage for extra privacy.
- Include disclaimers: this tool provides informational assistance and does **not** replace qualified legal advice.

---

## 🛠 Customization & Extensions

- Swap embedding models depending on your compute and accuracy needs.
- Add role-based authentication for multi-user deployments.
- Integrate official legal datasets or government APIs to expand the knowledge base.

---

## 🤝 Contributing

Contributions are welcome. Please fork the repo, add tests for new features, and submit a pull request with clear documentation.

---

## 📜 License

This project is licensed under the **MIT License**.

---

*Built to assist — not to replace a licensed attorney.*

