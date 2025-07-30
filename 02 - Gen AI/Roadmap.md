# 🧠 The 4-Week AI Research & Learning Accelerator Roadmap

This roadmap is designed to build a single, impressive project that demonstrates mastery of **Model Context Protocols (MCPs)** — the complete strategy of providing an LLM with the right context (through **RAG**, agentic memory, tool use, and prompt structuring) to achieve a complex goal.

---

## 📅 Week 1: The Core RAG Engine & MCP Foundations

**🎯 Goal:** Build the heart of our accelerator — the ability to deeply understand and answer questions about a document.

### ✅ Topics

- **1. The 10-Min Setup**
  - Get Llama 3 running locally with Ollama.
  - 💡 *Pro Tip:* Run `ollama run llama3` to confirm it’s working.
  - 🎥 [Video by Fireship](https://www.google.com/search?q=https://www.youtube.com/playlist%3Flist%3DPL-7oF_I_4qD-Y3ASJ8qrjI4C22d2S4Fb_)

- **2. MCP 1: Advanced RAG**
  - Learn RAG using LlamaParse to parse PDFs smartly.
  - 💡 *Pro Tip:* Handles tables/figures well, great for research papers.
  - 📚 [LlamaParse Tutorial](https://www.google.com/search?q=https://docs.llamaindex.ai/en/latest/module_guides/loading/file/llamaparse.html)

- **3. LlamaIndex Intro**
  - Learn `VectorStoreIndex`, the core RAG component.
  - 💡 *Pro Tip:* Faster and easier than LangChain for many cases.
  - 🎥 [Rabbit Hole Video](https://www.google.com/search?q=https://www.youtube.com/playlist%3Flist%3DPL-7oF_I_4qD-W_i5W_12S4oG-B9Y2k_2Z)

- **4. Build the Q&A Engine**
  - Upload a PDF and ask it questions via Streamlit UI.
  - 💡 *Pro Tip:* Cache index to avoid reprocessing on each query.
  - 🎥 [Chanin Nantasenamat Video](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3Ds_gIorw4EXM)

### 🔥 Weekly Outcome:
> A working web app that lets you upload a PDF and interact with it using Q&A powered by LlamaParse + RAG.

---

## 📅 Week 2: The Agentic Layer & Automated Content Generation

**🎯 Goal:** Add agentic intelligence that auto-generates flashcards from the document (our second MCP).

### ✅ Topics

- **1. Intro to Agents**
  - Learn about agents and the loop: *Thought → Action → Observation → Thought*
  - 🎥 [AssemblyAI Playlist](https://www.google.com/search?q=https://www.youtube.com/playlist%3Flist%3DPLpdmBGJ6ELUIQ-nSzwf_2tK2e-9T1M7bA)

- **2. Learn CrewAI**
  - Understand Agents, Tasks, and Crews.
  - 🎥 [Dave Ebbelaar Playlist](https://www.google.com/search?q=https://www.youtube.com/playlist%3Flist%3DPLjoJJakf992AL235gqHyXBvHh1a9oDb2k)

- **3. Design the Crew**
  - **Term Agent:** Extracts keywords
  - **Definition Agent:** Writes context-aware definitions

- **4. Build the Feature**
  - Integrate agents in Streamlit and output flashcards as CSV.
  - 📚 [CrewAI Custom Tools Guide](https://www.google.com/search?q=https://docs.crewai.com/how-to/Creating-Custom-Tools/)

### 🔥 Weekly Outcome:
> Your app can now auto-generate flashcards from a document using agents, downloadable as CSV.

---

## 📅 Week 3: Advanced Data Sources & Multi-Modal Context

**🎯 Goal:** Expand your tool to support YouTube and GitHub sources.

### ✅ Topics

- **1. Chat with YouTube**
  - Use `youtube-transcript-api` to get transcripts.
  - 🎥 [Leon van Zyl Video](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3D9T00tATEYj4)

- **2. Chat with Code**
  - Load GitHub repos and ask questions about the code.
  - 💡 *Pro Tip:* Use smart chunking along class/function boundaries.

- **3. Integrate New Loaders**
  - Add support in your app for YouTube and GitHub links.
  - 💡 *Pro Tip:* Use URL check like `if "youtube.com" in url:` for routing.

### 🔥 Weekly Outcome:
> Your app becomes multi-source: accepts PDFs, YouTube URLs, GitHub repos for full Q&A and flashcard generation.

---

## 📅 Week 4: Final Polish, Optimization & Deployment

**🎯 Goal:** Make the project ready for real-world users and job-ready portfolio.

### ✅ Topics

- **1. Add Caching**
  - Use Streamlit’s `@st.cache_data` to speed up repeated queries.
  - 📚 [Streamlit Caching Docs](https://docs.streamlit.io/library/advanced-features/caching)

- **2. Write a Killer README**
  - Include a clear overview, setup guide, features, and a demo GIF.
  - 🎥 [Super-charge Your Career](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3DwI3h_1fssyY)

- **3. Deploy to the World**
  - Deploy the app on Hugging Face Spaces.
  - 💡 *Pro Tip:* A clean `requirements.txt` avoids 90% of errors.
  - 🎥 [Misra Turp Deployment Guide](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3DS36034qjC0E)

### 🔥 Weekly Outcome:
> A fully polished, deployed GenAI app supporting PDFs, YouTube, GitHub with Q&A + agent flashcards. Great for portfolios and interviews.

---

# 🛠 Tech Stack Summary

- **LLMs:** Llama 3 (via Ollama), OpenAI, or Hugging Face
- **Frameworks:** LlamaIndex, CrewAI, LangChain (optional)
- **Frontend:** Streamlit
- **Storage:** FAISS or ChromaDB (if needed)
- **Deployment:** Hugging Face Spaces

---

# ✅ What You Will Learn
- RAG-based pipelines
- Context-aware LLM memory (MCPs)
- Building AI agents
- Multimodal input handling
- Streamlit integration
- Real-world GenAI deployment

---

# 🔗 Helpful Tags
`#GenAI` `#RAG` `#MCP` `#CrewAI` `#LLM` `#LangChain` `#ObsidianNotes` `#ProjectRoadmap`

