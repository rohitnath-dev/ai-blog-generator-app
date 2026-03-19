# AI Blog Generation Engine (LangGraph Powered)

An agentic, multi-stage AI system that **plans, researches, and generates high-quality technical blogs** using structured workflows.

Unlike simple LLM wrappers, this project implements a **graph-based reasoning pipeline** with routing, research augmentation, and modular execution.

---

## Why this project matters

Most AI blog generators:
- ❌ hallucinate
- ❌ lack structure
- ❌ produce generic content

This system solves that using:

- ✅ **Intent-aware routing**
- ✅ **Optional real-time research (Tavily)**
- ✅ **Structured planning (Pydantic schemas)**
- ✅ **Multi-step generation pipeline**
- ✅ **Evidence-backed writing**
- ✅ **Image generation + placement**

---

## Architecture

> **User Input**
>       ↓
> **Router** (Decides research vs direct)
>       ↓
> **Research** (Tavily API)
>       ↓
> **Planner** (Structured blog plan)
>       ↓
> **Workers** (Section-wise generation)
>       ↓
> **Reducer** (Merge + Images)
>       ↓
> **Final Blog Output**

---

## Core Components

### 1. Router
- Decides:
  - closed_book vs open_book vs hybrid
- Generates:
  - search queries
  - research need

---

### 2. Research Module
- Uses Tavily API
- Filters:
  - relevant sources
  - recent data
- Produces structured `Evidence`

---

### 3. Planner (Orchestrator)
- Creates full blog structure:
  - title
  - audience
  - tone
  - sections
- Uses strict schema → no random outputs

---

### 4. Workers
- Each worker:
  - writes ONE section
  - follows constraints
  - uses evidence when required

---

### 5. Reducer + Image Engine
- Merges all sections
- Decides:
  - where images are needed
- Generates:
  - diagrams using Gemini
- Injects into markdown

---

## Features

- Agentic workflow (LangGraph)
- Schema-driven outputs (Pydantic)
- Optional real-time research
- Evidence-backed content
- Modular node-based architecture
- Automatic image generation
- Export:
  - Markdown
  - ZIP (images + content)
- Streaming execution support

---

## Tech Stack

- Python
- LangGraph
- LangChain
- OpenAI / Gemini APIs
- Tavily Search API
- Pydantic
- Streamlit (UI)

---

## Setup

### 1. Clone repo

```bash
git clone https://github.com/your-username/ai-blog-generator-app.git
cd ai-blog-generator-app
```

---

2. Install dependencies

pip install -r requirements.txt


---

3. Setup environment variables

Create .env file:

OPENAI_API_KEY=your_key_here
GOOGLE_API_KEY=your_key_here
TAVILY_API_KEY=your_key_here


---

4. Run app

streamlit run frontend.py


---

Example Workflow

Input:

"Explain Retrieval Augmented Generation in detail"

System will:

1. Decide if research needed


2. Fetch latest info


3. Create structured plan


4. Generate sections


5. Add diagrams


6. Output complete blog


2. Install dependencies

pip install -r requirements.txt

---

3. Setup environment variables

Create .env file:

OPENAI_API_KEY=your_key_here
GOOGLE_API_KEY=your_key_here
TAVILY_API_KEY=your_key_here

---

4. Run app

streamlit run frontend.py

---

Example Workflow

Input:

"Explain Retrieval Augmented Generation in detail"

System will:

1. Decide if research needed

2. Fetch latest info

3. Create structured plan

4. Generate sections

5. Add diagrams

6. Output complete blog

---

Project Structure

.
├── backend.py        # LangGraph pipeline
├── frontend.py       # Streamlit UI
├── .env.example      # Env template
├── requirements.txt
└── README.md

---

Key Design Decisions

1. Graph-based architecture

Instead of linear pipelines -> flexible execution

2. Structured outputs

Prevents:
* hallucination
* randomness
* inconsistency

3. Research gating

Not every query needs internet -> cost optimized

---

Future Improvements

[ ] Fine-tuned planning model
[ ] RAG over custom knowledge base
[ ] Multi-language blog generation
[ ] SEO optimization module
[ ] Feedback loop (RLHF-style)
[ ] Evaluation pipeline (auto scoring)

---

Positioning

This is not just a blog generator.

It is a:

> Modular AI content generation engine with reasoning, retrieval, and orchestration

---

Contribution

Feel free to:
* Open issues
* Suggest improvements
* Extend modules

---

License

MIT License
