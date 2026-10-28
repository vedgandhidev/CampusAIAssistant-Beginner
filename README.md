# Campus AI Assistant — Beginner Track (real chatbot)

A simplified, **functionally faithful** teaching edition of [Matthew's Campus AI Assistant Pipeline](https://github.com/mattjunior039/CampusAIAssistantTutorial).

**Same core technologies:** TF–IDF lexical search → sentence embeddings and intent labels → PDF ingestion → overlapping chunks → 384D MiniLM embeddings → **FAISS** index → **Ollama-generated answers** with evidence citations. This is **not a mock-only chatbot**. When Ollama is configured, students ask their own questions in a chat widget in notebook 3.

## What students use

| File | What students actually do | Suggested duration |
|---|---|---|
| `student_track/01_keyword_detective.ipynb` | Build and deliberately fool a TF–IDF search engine | 2 × 60 minutes |
| `student_track/02_meaning_mapper.ipynb` | Explore real MiniLM embeddings and classify the intent of questions | 2 × 60 minutes |
| `student_track/03_evidence_bot.ipynb` | **Build and talk to a real Ollama + FAISS + PDF chatbot** | 2 × 60 minutes |

`student_track/data/Example_School_Handbook.pdf` provides an additional classroom example. Notebook 3 recreates its own PDF so it can run without uploading any data file to Google Colab.

## Quick start

**Instructor, before class:** Read `TEACHER_GUIDE.md` and `COLAB_TEACHER_SETUP.md`. Test all three notebooks on the intended student device/network. The third notebook needs a running **Ollama server** and a downloaded `llama3.2:3b` model in the **same runtime**, in addition to its Python package dependencies. Google Colab is a remote computer, so it cannot automatically access an Ollama installation on your laptop.

**Students:** Run the notebooks in order. Read the question prompts, change only variables marked `CHANGE ME` or `STUDENT EXPERIMENT`, and explain the result. Under school policy, use teacher-approved accounts and fictional information only.

**Important limits:** An LLM may still hallucinate even with RAG. Similarity thresholds are heuristics and source IDs are not independently verified citations. Do not use fictional school policies as real rules. No standalone public website is included: the chat interface runs inside the Jupyter notebook.

**Project status:** PDF parsing and core pipeline structure have been reviewed; real MiniLM + FAISS + Ollama execution must be completed in a properly provisioned environment before classroom deployment.
