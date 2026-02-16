# Assessment Rubric

Detailed criteria for evaluating daily progress documentation.

## CLAUDE.md Analysis

Look for and evaluate:

| Element | Good | Needs Improvement |
|---------|------|-------------------|
| Technical approach | Decisions documented with reasoning | Vague descriptions, no rationale |
| Problems encountered | Solutions attempted and outcomes noted | Just listed without resolution steps |
| Questions/uncertainties | Flagged clearly for follow-up | Buried or absent |
| Code details | Key snippets with explanations | Raw code dumps without context |
| Learning captured | Insights noted and applied | No reflection on what was learned |

## PROGRESS.md Analysis

| Element | Good | Needs Improvement |
|---------|------|-------------------|
| Task tracking | Completed vs. planned clearly shown | Unclear what was planned vs. done |
| Time allocation | Activities have rough time estimates | No sense of time spent |
| Challenges | Unexpected issues documented | Surprises not captured |
| Dependencies | Blockers and dependencies listed | Missing dependency tracking |
| Metrics | Measurable progress indicators | Only qualitative descriptions |

## Progress Scoring Guide

Use this mental model to calibrate your assessment:

**Strong Day (8-10/10)**
- Clear goals accomplished
- Blockers documented with attempted solutions
- Technical decisions justified
- Next steps clearly defined
- Learning captured and applied

**Average Day (5-7/10)**
- Some goals met, some deferred
- Partial documentation
- Decisions made but reasoning light
- Next steps exist but vague
- Some learning noted

**Weak Day (1-4/10)**
- Goals unclear or unmet
- Minimal documentation
- No decision rationale
- No clear next steps
- No reflection or learning

## Data Project Specific Criteria

### Data Quality
- Was input data validated before processing?
- Were data types, nulls, and edge cases checked?
- Is there a data quality report or summary?

### Reproducibility
- Can someone else recreate the results from documentation?
- Are environment dependencies captured?
- Are random seeds set for ML work?

### Metrics & Evaluation
- Are baseline metrics established before changes?
- Beyond accuracy — precision, recall, F1 checked?
- Are failure cases examined and documented?

### Production Readiness
- Is error handling in place?
- Are there tests (unit, integration)?
- Is the deployment path considered?
- Are performance/scaling concerns addressed?

## Communication Style Reminders

When delivering your assessment:

- **Acknowledge effort** — Even small progress matters
- **Be constructive** — Frame issues as opportunities
- **Use their language** — Mirror terminology from their docs
- **Give concrete examples** — "Consider adding try-catch to the embedding function" > "Add error handling"
- **Respect their context** — They know their project better than you
