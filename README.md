AI Blog Generator App

An agentic AI-powered application that automatically plans, researches, and generates structured technical blog posts using a multi-step LLM workflow.

This project implements a modular blog-writing pipeline built with LangGraph and modern LLM tooling. It routes topics, optionally performs web research, orchestrates a writing plan, generates sectioned content, and enhances the final output with AI-generated diagrams.

---

Features

- Agentic blog-writing pipeline (Router → Research → Orchestrator → Workers → Reducer)
- Schema-driven structured outputs using Pydantic
- Optional web research via Tavily integration
- Automatic multi-section blog generation
- AI-assisted diagram planning and image placement
- Modular graph architecture using LangGraph
- Environment-based API configuration with ".env"
- Markdown blog export with embedded images

---

Tech Stack

- Python
- LangGraph (agent orchestration)
- LangChain
- OpenAI / Gemini APIs
- Tavily Search API
- Pydantic
- python-dotenv

---

Installation

1. Clone the repository

git clone https://github.com/your-username/ai-blog-generator-app.git
cd ai-blog-generator-app

2. Install dependencies

pip install langgraph langchain langchain-openai langchain-community python-dotenv google-genai tavily-python

3. Create a ".env" file

OPENAI_API_KEY=your_key_here
GOOGLE_API_KEY=your_key_here
TAVILY_API_KEY=your_key_here

---

Usage

Run the backend script and invoke the app with a topic:

result = app.invoke({
    "topic": "Understanding Self Attention in Transformers",
    "as_of": "2026-02-01",
})

The system will:

1. Decide if research is required
2. Collect external evidence (if needed)
3. Create a structured blog plan
4. Generate sections in parallel
5. Merge content and add diagrams
6. Export a final Markdown blog file

Generated blogs and images are saved locally.

---

Example Workflow

Topic → Router
      → (Research if needed)
      → Orchestrator Plan
      → Worker Sections
      → Reducer + Images
      → Final Blog Markdown

---

Future Improvements

- Web UI dashboard
- Blog publishing integrations
- Streaming generation
- Custom style templates
- Multi-language support

---

Conclusion

This project demonstrates a scalable agentic architecture for automated technical blog generation. It showcases structured LLM workflows, modular orchestration, and practical integration of research and image generation into a unified pipeline.
