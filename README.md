# Agentic AI — Practical Examples, Projects and Interview Preparation

A hands-on guide to building AI agents in Python, written for beginners and for interview preparation. Every example runs **without an API key** in offline mode, so it works in a classroom lab; set a key to use a real Claude model.

**Author:** Zahida Walayat, Department of Computer Science, COMSATS University Islamabad

## What is inside

| Folder / file | Contents |
| --- | --- |
| `docs/Agentic_AI_Practical_Guide.pdf` (and `.docx`) | The full guide: setup, six examples, three projects, interview preparation, with diagrams |
| `code/` | All example and project code, ready to run |
| `code/test_examples.py`, `code/test_app.py` | 12 tests covering every example and the web service |

### Practical examples

| # | Example | Teaches |
| --- | --- | --- |
| 1 | `ex1_agent_loop.py` | The perceive → think → act → observe loop, with no LLM |
| 2 | `ex2_function_calling.py` | Function calling and the tool loop with a real LLM |
| 3 | `ex3_react.py` | ReAct: Thought → Action → Observation |
| 4 | `ex4_memory_rag.py` | Short-term memory, long-term vector memory, RAG |
| 5 | `ex5_multi_agent.py` | Manager, researcher, writer and reviewer agents |
| 6 | `ex6_guardrails_eval.py` | Input checks, tool allow-list, human approval, evaluation |

### Projects

| Project | File | What it does |
| --- | --- | --- |
| Research assistant | `research_assistant.py` | Plans sub-questions, retrieves from your own files, writes a cited report |
| Customer support agent | `support_agent.py` | Answers only from documents, remembers the session, hands off to a human |
| Agent in production | `app.py`, `Dockerfile` | FastAPI service with health check, logging and a container |

## Quick start

```bash
cd code
python -m venv .venv
# Windows: .venv\Scripts\activate    Linux/macOS: source .venv/bin/activate
pip install -r requirements.txt

pytest -q                         # 12 tests, offline
python ex1_agent_loop.py          # run any example
python research_assistant.py solar energy
uvicorn app:app --reload          # then open http://127.0.0.1:8000/docs
```

**Live mode (optional):** set `ANTHROPIC_API_KEY` in your environment. The model name is read from `AGENT_MODEL` (default `claude-sonnet-5-5`). Never commit your key; `.env` is in `.gitignore`.

**Docker (optional):**

```bash
cd code
docker build -t support-agent .
docker run -p 8000:8000 -e ANTHROPIC_API_KEY support-agent
```

## Notes

- Chapter references in the guide (for example *ch. 5*) point to the concept chapters of a companion set of study notes, which are not part of this repository.
- Sample facts used as data (motorway distance, solar and wind figures) are cited in the guide's *Sources checked* sections.

## Credits

Written by Zahida Walayat with AI assistance (Claude by Anthropic) for drafting, code and diagrams. All code was run and tested before publishing.
