# Google Colab and local Jupyter setup — instructors only

## Two different computers

Google Colab runs code on **Google's cloud computer**, not on your laptop. Ollama started on your laptop is **not** reachable as `localhost` from a Colab notebook. For the simplest and most reliable live demonstration, run all notebooks and Ollama on the **same teacher computer** using Jupyter, or provision Ollama inside the Colab runtime.

## Option A — Local teacher computer (recommended for stable demos)

1. Install Python 3.10+ and Ollama from [ollama.com](https://ollama.com/) according to school IT policy.
2. Install requirements: `python -m pip install -r requirements.txt`.
3. In a terminal, start the Ollama server using `ollama serve` if it is not already running.
4. In another terminal, download the model **before class** with `ollama pull llama3.2:3b`. This needs free disk space and an internet connection. Model inference can be slow without sufficient RAM/GPU.
5. Start Jupyter (`jupyter notebook`), open `student_track/03_evidence_bot.ipynb`, run cells from top to bottom, ask a real question, and check that status is `GENERATED`.

## Option B — Teacher-managed Google Colab runtime

1. Confirm Colab is approved by school IT and the available runtime can handle a local model.
2. In a **teacher-only Colab cell**, install Ollama from the official documented installer and start its server *inside the Colab runtime*; do not assume a service on the teacher's laptop is shared with Colab.
3. Download `llama3.2:3b` within that same runtime. Installing the Python `ollama` package from pip **does not** install the Ollama server or the model.
4. Run the notebook's setup cells and then send a real question. Verify `GENERATED` and examine its supporting passages.
5. Free Colab resources, internet connections and background processes may be constrained or reset; recheck at the start of each session. If this is unreliable, use Option A for the live model and students' Colab for Phase 1–2.

**Do not ask students to paste API keys or login credentials** into the notebook. The course is based on fictional data; review your district policies before using any cloud services.

## Checkpoints

- PDF reading: four fictional pages extracted.
- Chunks: multiple page-labeled passages produced.
- Embeddings: a matrix with 384 columns.
- FAISS: indexed passage count equals chunk count.
- Chatbot: response status `GENERATED`, model answer visible, cited passage IDs available.
- Error behavior: if Ollama is down, status `MODEL_NOT_READY` — do not call that a successful chat answer.
