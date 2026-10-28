# Multimodal RAG classroom project

This beginner project answers questions using three forms of evidence:

- text extracted from a PDF;
- factual captions that represent charts and diagrams;
- timestamped text from a video transcript.

It matches the practical path in `Multimodal_RAG.pptx`: create searchable representations, attach source metadata, store them in one Chroma collection, retrieve relevant evidence, optionally inspect the best retrieved image with vision, and produce a cited answer.

## Setup on Windows PowerShell

The project already has its own `.venv` and `.env`. From this folder:

```powershell
.venv\Scripts\Activate.ps1
python test_code.py
```

To recreate the environment:

```powershell
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
```

Never display or commit `.env`. `.env.sample` contains safe placeholders.

## Classroom run order

```powershell
.venv\Scripts\python.exe test_code.py
.venv\Scripts\python.exe reset_local_db.py
.venv\Scripts\python.exe build_index.py
.venv\Scripts\python.exe ask.py
.venv\Scripts\python.exe evaluate.py
```

Press Enter in `ask.py` to use the cross-modal demo question. It requires evidence from both the chart and the transcript.

## What was intentionally left out

There is no notebook, web UI, live YouTube download, keyword router, fake embedding fallback, LangSmith setup, or live image-caption generation. These additions hide the core RAG flow or create unreliable classroom dependencies. Prepared captions and a prepared transcript keep the practical repeatable. The answer step still demonstrates late vision by sending at most one retrieved image to the model.

Read `STUDENT_GUIDE.md` for the design and every function. Read `TRAINER_README.md` for the teaching script and rehearsal checklist.

