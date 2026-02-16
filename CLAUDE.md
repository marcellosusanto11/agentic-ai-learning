# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Rules
Always save all open files before making any edits

## Project Overview
Agentic AI Learning, this repository used to store code that I made to learn about how to build agentic AI design and system. It's my reimagination of making the task provided by online course more challenging and cohesive

## Development Setup

- **Python environment**: `uv` venv at `.venv/` (Python 3.9.6)
- **Activate**: `source .venv/bin/activate`
- **Install deps**: `uv pip install -r requirements.txt`
- **Run notebooks**: `jupyter notebook` or use VS Code notebook interface

## Architecture

All code lives in `code/` as Jupyter notebooks. There are no standalone Python modules or packages.

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

## Source of Learning

#### DONE

- https://youtu.be/J7j5tCB_y4w?si=nNJK7IcWHDeMZaXs
  **LangChain Full Crash Course - AI Agents in Python** (Tina Huang)
  Crash course covering LangChain fundamentals for building AI agents. Walks through agent creation, tool usage, RAG with FAISS, PDF document loading, image input processing, and multi-agent collaboration patterns.
  *Learn: LangChain basics, create_agent wrapper, tool binding, vector similarity search, retriever tools, middleware/dynamic prompts, adaptive model selection*

- https://www.anthropic.com/engineering/building-effective-agents
  **Building Effective Agents** (Anthropic Engineering Blog)
  Anthropic's guide arguing for simple, composable patterns over complex frameworks. Covers the distinction between workflows (predefined code paths) and agents (LLM-directed processes), and presents foundational patterns: prompt chaining, routing, parallelization, orchestrator-workers, and evaluator-optimizer.
  *Learn: When to use agents vs workflows, agent design patterns, keeping systems simple and transparent, agent-computer interface design*

- https://www.deeplearning.ai/short-courses/ai-agents-in-langgraph/
  **AI Agents in LangGraph** (DeepLearning.AI — Harrison Chase & Rotem Weiss)
  Build controllable AI agents using LangGraph. Covers constructing agents from scratch, agentic search with Tavily, state persistence, and human-in-the-loop oversight. Includes building an essay-writing agent as the main project.
  *Learn: LangGraph StateGraph, AgentState with TypedDict, conditional edges, checkpointing, interrupt/Command for human approval, multi-node graph pipelines*

- https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/
  **ChatGPT Prompt Engineering for Developers** (DeepLearning.AI — Andrew Ng & Isa Fulford)
  Practical prompt engineering techniques for developers. Covers summarizing, inferring, transforming text, expanding, and building custom chatbots.
  *Learn: Delimiter/pointer usage, structured output, criteria/conditions, few-shot prompting, chain-of-thought prompting, iterative prompt refinement*

#### IN PROGRESS

- https://www.deeplearning.ai/short-courses/long-term-agentic-memory-with-langgraph/
  **Long-Term Agentic Memory with LangGraph** (DeepLearning.AI)
  Build AI agents that retain and utilize long-term memory. Covers three memory types — semantic, episodic, and procedural — implemented through LangGraph and memory storage systems. Main project: personal email agent with memory.
  *Learn: Semantic/episodic/procedural memory design, memory storage backends, building memory-aware agents in LangGraph*

- https://www.deeplearning.ai/short-courses/llms-as-operating-systems-agent-memory/
  **LLMs as Operating Systems: Agent Memory** (DeepLearning.AI)
  Build AI agents with autonomous memory management using the Letta framework (based on MemGPT research). Treats LLM agents as operating systems to manage context windows efficiently. Covers memory architecture, multi-agent collaboration, and persistent/editable memory.
  *Learn: MemGPT/Letta framework, context window management, persistent memory systems, multi-agent memory sharing*

#### NOT STARTED YET

- https://www.deeplearning.ai/short-courses/multi-ai-agent-systems-with-crewai/
  **Multi AI Agent Systems with CrewAI** (DeepLearning.AI)
  Design and organize teams of AI agents for complex multi-step tasks using the crewAI library. Covers role-playing, memory, tool assignment, task breakdown, error handling, and agent cooperation. Practical examples: resume tailoring, article writing, customer support, event planning.
  *Learn: Multi-agent orchestration, role-based agent design, task decomposition, crewAI framework*

- https://www.deeplearning.ai/short-courses/building-evaluating-advanced-rag/
  **Building and Evaluating Advanced RAG** (DeepLearning.AI)
  Advanced RAG techniques for integrating LLMs with organizational data. Covers sentence-window retrieval, auto-merging retrieval, and the RAG evaluation framework (context relevance, groundedness, answer relevance).
  *Learn: Advanced retrieval strategies, RAG evaluation metrics, sentence-window and auto-merging retrieval*

- https://learn.nvidia.com/courses/course-detail?course_id=course-v1:DLI+S-FX-40+V1
  **Building RAG Agents with LLMs** (NVIDIA DLI)
  Hands-on course deploying RAG agent systems at scale with GPU-accelerated cloud workstations. Uses Python, LangChain, NVIDIA AI Foundation Endpoints, FAISS, Gradio, LangServe, and FastAPI.
  *Learn: Production RAG deployment, NVIDIA AI endpoints, LangServe/FastAPI integration, scaling agent systems*

- https://youtu.be/H86z-3vp4I0?si=78eYznqejOs8JQyC
  **n8n Crash Course - Automated AI Workflows**
  Build automated AI workflows using n8n, a no-code/low-code workflow automation platform.
  *Learn: n8n workflow automation, connecting AI models to external services, no-code agent pipelines*

- https://youtu.be/bUkdnYDxYGk?si=KZ8MFAfOvwnpCZ_W
  **Fine-Tuning Local LLMs with Axolotl in Python**
  Fine-tune open-source LLMs locally using the Axolotl library in Python.
  *Learn: Local LLM fine-tuning, Axolotl framework, training configuration, model customization*

- https://youtu.be/I90xJlzAUW0?si=s-46Gk0P2Vzrpwvs
  **CrewAI Tutorial: Multiple Agents Working Together in Python**
  Hands-on tutorial building multi-agent systems with CrewAI in Python.
  *Learn: CrewAI implementation, agent roles/tasks definition, multi-agent collaboration in code*

- https://youtu.be/6w88NVf2_lY?si=nrEiLJm_t3Lo3wvn
  **How I Write My AGENTS.md Files - Best Practices**
  Best practices for writing AGENTS.md files that define agent behavior and instructions.
  *Learn: Agent instruction file design, prompt structuring for agent systems, documentation best practices*

- https://youtu.be/dkisb6FlU-g?si=dXt3pSCGhPCeim2k
  **LlamaIndex Crash Course - AI Agents in Python**
  Crash course on building AI agents with LlamaIndex in Python.
  *Learn: LlamaIndex framework, data connectors, query engines, LlamaIndex agent patterns*

## Small Project
These are the list of small agent that is built by combining all of the thing I learn from the online course, with the current todo for each of them

#### EssayMaker
Agentic AI design that will do planning, research, drafting, and reflect on the topic given by the user and then produced a well written essay draft

Graph flow: Plan → Research (Tavily) → Generate → Reflect → (loop back to Research/Generate up to max revisions) → Human approval

Todo
| EssayMaker: Add RAG to research node                                     |
| EssayMaker: Add slop score                                               |
| EssayMaker: Add Pydantic Validation                                      |
| EssayMaker: Add ability to differentiate essay generation vs content Q&A |
| EssayMaker: Add multi-thread support + cross-thread query                |

#### EmailAgent
Agentic AI design that will scan the email and tag whether the user should ignore/reply/notified. If its' reply than the agent can help make the reply email draft

Graph flow: Router (classify intent) → Persona (ChromaDB lookup) → Triage (IGNORE/NOTIFY/RESPOND) → Respond (draft reply) → Send (Gmail API)

Todo
| EmailAgent: Add ChromaDB integration for user persona       |
| EmailAgent: Add persona summarization → Google Sheet append |
| EmailAgent: Integrate Gmail API for actual sending          |
| Figure out: How to track Human/AI messages per user persona |
| Figure out: How to add new user persona to Google Sheet     |

