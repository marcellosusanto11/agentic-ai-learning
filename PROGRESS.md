# PROGRESS.md

## Feb 22, 2026

### EssayMaker — Baseline Research Analysis

Analyzed the baseline EssayMaker (no memory) output across 2 research iterations to quantify redundant work.

#### Duplicate / Similar Queries

4 out of 5 queries in Iteration 2 are near-duplicates or topically very similar to Iteration 1. Only 1 is genuinely new.

| Iter 1 Query | Iter 2 Query | Similarity |
|---|---|---|
| `duration-indexed causal effects temporal dynamics treatment impact` | `duration-indexed causal effects temporal treatment dynamics econometrics` | **Near-duplicate** — only swapped trailing words |
| `quantile treatment effects QTE heterogeneity outcome distribution` | `quantile treatment effects QTE recent research econometrics 2023 2024` | **Similar topic** — same core, different modifiers |
| `heavy-tailed distributions causal inference extreme value theory` | `heavy-tailed distributions causal inference extreme value theory policy` | **Near-duplicate** — identical except appending "policy" |
| `average treatment effects limitations heterogeneity bias` | `average treatment effect heterogeneity distributional methods modern causal inference` | **Similar topic** — both ATE heterogeneity |
| *(none)* | `job training programs temporal effects long-term impact evaluation` | **Genuinely new** |

#### Duplicate URLs

3 exact duplicate URLs + 1 near-duplicate (same paper, `.full` vs `.pdf` format) across iterations.

| URL | Iter 1 | Iter 2 |
|---|---|---|
| `projecteuclid.org/.../Causal-discovery-in-heavy-tailed-models/10.1214/20-AOS2021.pdf` | ✅ | ✅ |
| `pmc.ncbi.nlm.nih.gov/articles/PMC10423152/` | ✅ | ✅ |
| `ncbi.nlm.nih.gov/books/NBK126188/` | ✅ | ✅ |
| `projecteuclid.org/.../10.1214/20-AOS2021.full` | — | ✅ (same paper as .pdf above) |

~16% of Iteration 2 results were wasted on already-retrieved content.

#### Takeaway

Without memory, the reflect node's feedback drives the research node to search similar topics with slightly reworded queries, producing overlapping results. This is the problem the ChromaDB-backed research memory version is designed to solve.

---

## Feb 21, 2026

### EssayMaker Agent
- Pushed EssayMaker notebook (`main_llm_essay_maker.ipynb`) via PR #2
- Replaced basic `main_llm_agent_memory.ipynb` with full multi-node agent
- Features: LangGraph StateGraph (plan → research → generate → reflect), ChromaDB-backed research memory, user preference learning, Tavily search tool integration, configurable revision loops, HTML output
- Updated CLAUDE.md architecture table to reflect notebook change

### Claude Code Skills
- Published `claude-code-skills` repo to GitHub with 4 skills + 2 agents
- Comprehensive README with install instructions and output examples
