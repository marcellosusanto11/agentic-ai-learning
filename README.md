# Agentic AI Learning

A repository of code I built while learning how to design and build agentic AI systems. It's my reimagination of making the tasks provided by online courses more challenging and cohesive.

## Development Setup

- **Python**: 3.12 (matches Google Colab runtime 2026.01)
- **Environment**: `.venv/`
- **Activate**: `source .venv/bin/activate`
- **Install deps**: `pip install -r requirements.txt`
- **Run notebooks**: `jupyter notebook` or use VS Code notebook interface
- **API keys**: Create a `.env` file with `OPENAI_API_KEY`, `GOOGLE_API_KEY`, `ANTHROPIC_API_KEY`, and `TAVILY_API_KEY`

## Architecture

All code lives in `code/` as Jupyter notebooks.

### Notebooks (learning progression)

| Notebook | Topic | Primary LLM | Key Frameworks |
|---|---|---|---|
| `main_crash_course_youtube.ipynb` | Agent fundamentals, RAG, tools, image input | Gemini + Claude | LangChain, FAISS |
| `main_course_prompt_eng.ipynb` | Prompt engineering tactics, few-shot, chain-of-thought | Claude Haiku | LangChain |
| `main_course_ai_agent_in_langgraph.ipynb` | LangGraph StateGraph, human-in-the-loop, multi-node agents | Claude Haiku | LangGraph, Tavily |
| `main_llm_agent_memory.ipynb` | Persistent agent memory, ChromaDB, Google Sheets/Gmail integration | Claude Haiku | LangGraph, ChromaDB, Google APIs |

### Common patterns across notebooks
- Agent creation via `langchain.agents.create_agent` wrapper or manual `langgraph.graph.StateGraph`
- Conversation memory via `langgraph.checkpoint.memory.InMemorySaver`
- API keys set via `os.environ` (originally written for Google Colab)
- Primary model: `claude-haiku-4-5-20251001`; complex tasks use `claude-sonnet-4-5-20250929`

## Small Projects

### EssayMaker
Agentic AI that does planning, research, drafting, and reflection on a given topic, then produces a well-written essay draft.

**Graph flow:** Plan → Research (Tavily) → Generate → Reflect → (loop back to Research/Generate up to max revisions) → Human approval

### EmailAgent
Agentic AI that scans emails and tags whether the user should ignore/reply/be notified. If it's a reply, the agent helps draft the reply email.

**Graph flow:** Router (classify intent) → Persona (ChromaDB lookup) → Triage (IGNORE/NOTIFY/RESPOND) → Respond (draft reply) → Send (Gmail API)

## Source of Learning

### Completed

- [LangChain Full Crash Course - AI Agents in Python](https://youtu.be/J7j5tCB_y4w?si=nNJK7IcWHDeMZaXs) (Tina Huang)
- [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) (Anthropic Engineering Blog)
- [AI Agents in LangGraph](https://www.deeplearning.ai/short-courses/ai-agents-in-langgraph/) (DeepLearning.AI)
- [ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) (DeepLearning.AI)

### In Progress

- [Long-Term Agentic Memory with LangGraph](https://www.deeplearning.ai/short-courses/long-term-agentic-memory-with-langgraph/) (DeepLearning.AI)
- [LLMs as Operating Systems: Agent Memory](https://www.deeplearning.ai/short-courses/llms-as-operating-systems-agent-memory/) (DeepLearning.AI)

### Planned

- [Multi AI Agent Systems with CrewAI](https://www.deeplearning.ai/short-courses/multi-ai-agent-systems-with-crewai/) (DeepLearning.AI)
- [Building and Evaluating Advanced RAG](https://www.deeplearning.ai/short-courses/building-evaluating-advanced-rag/) (DeepLearning.AI)
- [Building RAG Agents with LLMs](https://learn.nvidia.com/courses/course-detail?course_id=course-v1:DLI+S-FX-40+V1) (NVIDIA DLI)
- [n8n Crash Course - Automated AI Workflows](https://youtu.be/H86z-3vp4I0?si=78eYznqejOs8JQyC)
- [Fine-Tuning Local LLMs with Axolotl](https://youtu.be/bUkdnYDxYGk?si=KZ8MFAfOvwnpCZ_W)
- [CrewAI Tutorial: Multiple Agents Working Together](https://youtu.be/I90xJlzAUW0?si=s-46Gk0P2Vzrpwvs)
- [How I Write My AGENTS.md Files](https://youtu.be/6w88NVf2_lY?si=nrEiLJm_t3Lo3wvn)
- [LlamaIndex Crash Course - AI Agents in Python](https://youtu.be/dkisb6FlU-g?si=dXt3pSCGhPCeim2k)
