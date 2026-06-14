# RAG Bot V3.0: Hybrid Retrieval AI Assistant 🤖🧠

An advanced Retrieval-Augmented Generation (RAG) pipeline built using **LangChain**, **Google Gemini**, and **Streamlit**. This project transitions from a basic document search system to an enterprise-grade conversational assistant featuring a hybrid search architecture and dynamic query engineering.

---

## 🚀 Key Features

* **Hybrid Retrieval Pipeline:** Combines lexical keyword matching (**Rank-BM25**) with dense semantic vector search (**ChromaDB**) for high-precision context retrieval.
* **LLM-Powered Query Re-Engineering:** Automatically resolves coreferences and contextualizes vague follow-up questions (e.g., rewriting *"How much does it cost?"* based on the previous conversation history).
* **Persistent Conversational Memory:** Uses Streamlit session state and LangChain's native message schemas (`HumanMessage`, `AIMessage`) to maintain full session context.
* **Caching & Optimization:** Document indexing runs conditionally only upon new file uploads, preventing repetitive computational lag.
* **Clean Streamlit UI:** Features a custom styled dashboard designed for uploading PDFs or TXT documents and seamless chatting.

---

## 🏗️ Architecture Flow

1. **Document Ingestion:** PDF/TXT -> Text Splitting (`RecursiveCharacterTextSplitter`) -> Parallel Indexing (BM25 + ChromaDB Vector Store).
2. **Query Processing:** User Input + Chat History -> Gemini Query Re-writer -> Contextualized Query.
3. **Hybrid Search:** Contextualized Query -> Simultaneous BM25 & Vector DB lookup -> Score Merging & Deduplication -> Final Context Chunks.
4. **Generation:** Merged Context + System Prompt + Re-written Query -> Google Gemini -> Final Answer.

---

## 🛠️ Tech Stack

* **Framework:** LangChain, LangChain-Community, LangChain-Core
* **LLM Ecosystem:** Google Gemini AI Studio (`gemini-1.5-flash`)
* **Vector Database:** ChromaDB
* **Keyword Search:** Rank-BM25
* **Frontend UI:** Streamlit
* **Embeddings:** HuggingFace Sentence-Transformers

---

## 🏃‍♂️ How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/rag_bot_v3.git](https://github.com/YOUR_USERNAME/rag_bot_v3.git)
   cd rag_bot_v3
