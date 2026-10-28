# Instructor guide — 6 Friday sessions (60 minutes each)

Audience: grade 4–6 beginners. **Goal:** Students should understand *why* each stage is needed, rather than copy code without reasoning.

## Keep the technical outcome, simplify the teaching

- **Phase 1 (Weeks 1–2):** FAQs, keyword search, TF–IDF. Ask students to invent synonyms to break the matching engine.
- **Phase 2 (Weeks 3–4):** Real MiniLM embeddings, cosine similarity, nearest-example intent classification. The 384 numbers are machine-readable, not a probability of correctness.
- **Phase 3 (Weeks 5–6):** Read a PDF; split into overlapping chunks; create embeddings; index with FAISS; retrieve top passages; call a *live local LLM* using Ollama; interact through the notebook chatbot widget. Explain why retrieval alone is NOT an AI-generated answer.

## Before the first class

1. Confirm Chromebook/network policy, age requirements, approved accounts, student privacy and access to Google Colab. Use fictional documents and no names, grades, private student records or authentic sensitive school policies.
2. Test **all** notebook cells in the actual classroom environment; have a teacher-owned device and projected demonstration available as fallback.
3. Install the required Python libraries (`requirements.txt`). Download the MiniLM embedding model before students arrive. Internet is needed on first use.
4. For the **real chatbot**, configure an Ollama server and pull `llama3.2:3b` on the notebook runtime. See `COLAB_TEACHER_SETUP.md`. This is not optional to meeting the stated chatbot outcome.
5. Test at least these questions, then inspect evidence and citations: “When does the library close?”, “Can I use AI on homework?”, “Can I fly a drone for a supervised robotics project?”, “Does the school have a swimming pool?”. The last should be treated as **unknown**; show students if a model falsely claims otherwise.
6. Because Ollama models can be computationally intensive, consider teacher-hosted demonstrations or pairs. Allocate time for downloads *before* class, not during the one-hour lesson.

## Week 5–6 pacing suggestion

**Week 5:** 0–10 introduce RAG; 10–25 PDF and chunking; 25–40 embedding and FAISS; 40–55 retrieval challenge and exceptions; 55–60 exit ticket.

**Week 6:** 0–10 retrieval review; 10–25 prompt instructions and citations; 25–45 real live chatbot experimentation; 45–55 evaluate unsupported questions and hallucinations; 55–60 showcase and reflection.

## Scoring student learning

Award 0–2 points each for: explaining keyword vs. meaning matching; correctly describing chunk/index/retrieve; showing a real generated answer and the evidence it used; identifying a hallucination or out-of-scope question; explaining a limitation and a concrete improvement. Maximum 10 points. **Completion is not measured by whether they can install the model themselves.**

## Failure protocol

When the notebook says `MODEL_NOT_READY`, don't substitute fabricated answers or imply the chatbot works. Check Ollama installation, server health, installed model tag, and whether notebook and server run on the same machine/runtime. Keep a teacher-owned working demo as contingency.
