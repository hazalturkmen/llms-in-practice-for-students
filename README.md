# LLMs in Practice — From Prompt to Pipeline

Hands-on course materials for second-year computer engineering students. This course takes you from your first API call to building a fully autonomous NER pipeline using an AI agent — in two focused modules.

---

## What you will learn

**Module 1 — Prompt Engineering**
Understand how LLMs work and learn the techniques that make the difference between a prompt that kind of works and one that reliably produces the output you need.

**Module 2 — Agentic AI Coding**
Move beyond the chatbox. Learn how agents work, how tools give models access to the real world, and how to use Claude Code to build a complete NLP project from scratch using only natural language.

---

## Course structure

```
Module 1 — Prompt Engineering
├── 00_introduction.ipynb       — setup, API key, course overview
├── 01_getting_started.ipynb    — first API call, roles, get_completion helper
├── 02_prompting_tips.ipynb     — 5 essential tips every NLP engineer needs
└── 03_prompting_examples.ipynb — zero-shot, few-shot, chain-of-thought

Module 2 — Agentic AI Coding
└── Covered in the live classroom session using Claude Code CLI
    - What is an agent
    - The agent loop: perceive → plan → act → observe
    - Tool use and how models interact with the real world
    - CLAUDE.md: giving the agent memory
    - Live demo: building an NER pipeline from scratch
```

---

## Prerequisites

- Basic Python (functions, loops, dictionaries, working with JSON)
- No prior NLP or AI experience required
- No machine learning background needed

---

## Stack

| Tool | Purpose |
|---|---|
| Python 3.11 | Language used throughout |
| [OpenRouter](https://openrouter.ai) | Unified API gateway — one key for all models |
| `openai` SDK | Client library (OpenRouter is OpenAI-compatible) |
| `python-dotenv` | Loading environment variables |
| `pytest` | Testing in Module 2 |

> **Why OpenRouter?**
> One API key gives access to Claude, GPT-4, Llama, Mistral and more.
> You can switch models by changing a single line: `MODEL = "anthropic/claude-sonnet-4-5"`

---

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/llms-in-practice-for-students.git
cd llms-in-practice
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Get an OpenRouter API key

1. Go to [openrouter.ai](https://openrouter.ai) and create a free account
2. Navigate to **Keys → Create Key**
3. Copy the key — it starts with `sk-or-...`

### 4. Set your environment variable

**Mac / Linux**
```bash
export OPENROUTER_API_KEY="sk-or-your-key-here"
```

**Windows**
```
Variable name:  OPENROUTER_API_KEY
Variable value: sk-or-your-key-here
```

### 5. Verify setup

```bash
python -c "import os; print('Key found' if os.environ.get('OPENROUTER_API_KEY') else 'Key NOT found')"
```

---

## Module 1 — Quick start

Open the notebooks in order:

```bash
jupyter notebook
```

Start with `00_introduction.ipynb` and work through to `03_prompting_examples.ipynb`. Each notebook is self-contained and runnable.

---

## Module 2 — Claude Code setup

Install Claude Code:

```bash
npm install -g @anthropic-ai/claude-code
```

Authenticate:

```bash
claude
```

Follow the prompts to log in with your Anthropic account.

---

## What you build in Module 2

By the end of the live session you will have built this from scratch using only natural language instructions:

```
ner_project/
├── CLAUDE.md               ← rules the agent follows every session
├── requirements.txt
├── data/                   ← input .txt files
├── src/
│   ├── ner_pipeline.py     ← core entity extraction
│   └── batch_process.py    ← processes all files at once
└── tests/
    └── test_pipeline.py    ← pytest test suite
```

Entity schema used throughout: `PER` · `ORG` · `LOC` · `DATE` · `MED`

---

## Key concepts covered

| Concept | Module | Notebook / Session |
|---|---|---|
| What is an LLM | 1 | `00_introduction.ipynb` |
| First API call | 1 | `01_getting_started.ipynb` |
| System prompts & roles | 1 | `01_getting_started.ipynb` |
| 5 prompting tips | 1 | `02_prompting_tips.ipynb` |
| Zero-shot prompting | 1 | `03_prompting_examples.ipynb` |
| Few-shot prompting | 1 | `03_prompting_examples.ipynb` |
| Chain-of-thought | 1 | `03_prompting_examples.ipynb` |
| What is an agent | 2 | Live session |
| Tool use | 2 | Live session |
| CLAUDE.md memory | 2 | Live session |
| Building an NER pipeline | 2 | Live session |

---

## License

MIT — free to use, adapt, and share for educational purposes.
