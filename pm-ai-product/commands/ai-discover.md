---
description: Discover and validate AI use cases — map opportunities, assess feasibility, and audit data readiness
argument-hint: "<product or AI feature idea>"
---

# /ai-discover — AI Use Case Discovery

Discover where AI adds real value to your product, assess technical feasibility, and audit data readiness before committing to build.

## Invocation

```
/ai-discover Pika's English speaking practice feature
/ai-discover [upload product brief or PRD]
/ai-discover                    # asks about your product
```

## Workflow

### Step 1: Understand the Product

Accept context from:
- Product description, PRD, or feature brief
- Current feature set and user problems
- Existing AI usage (if any)
- Uploaded documents

Ask key questions:
- What does the product do? Who are the users?
- What problems are hardest to solve with traditional software?
- Do you already use AI anywhere? How is it performing?
- What data do you collect from users?

### Step 2: Map AI Opportunities

Apply the **ai-use-case-mapping** skill:

1. Map the product's feature landscape
2. For each area, evaluate whether AI meaningfully improves it
3. Score each candidate on Value x Feasibility
4. Flag anti-patterns ("AI for the sake of AI")
5. Produce a prioritized AI use case map

### Step 3: Assess Feasibility

For top 3-5 use cases, apply the **ai-feasibility-assessment** skill:

1. Evaluate model capability, data needs, latency, infrastructure
2. Score each feasibility dimension (1-5)
3. Identify the binding constraint per use case
4. Deliver GO / PROTOTYPE FIRST / NOT NOW verdict

### Step 4: Audit Data Readiness

For feasible use cases, apply the **ai-data-readiness** skill:

1. Map data requirements for each AI feature
2. Audit existing data against requirements
3. Assess quality, volume, labeling, and privacy
4. Recommend data strategy (build, buy, collect, synthetic)

### Step 5: Generate Discovery Report

```markdown
## AI Discovery Report: [Product Name]

**Date**: [today]
**Author**: [user]

### Executive Summary
[1-2 paragraphs: key findings and recommendations]

### AI Use Case Map
| Use Case | AI Technique | Value | Feasibility | Data Ready? | Recommendation |
|----------|-------------|-------|-------------|-------------|----------------|

### Top Opportunities (Detailed)
[For each recommended use case: problem, solution, value, feasibility, data needs, risks]

### Anti-patterns Identified
[Features where AI is NOT the right approach]

### Data Readiness Summary
[Overall data maturity and key gaps]

### Recommended Next Steps
1. [Most impactful action]
2. [Second action]
3. [Third action]
```

Save as markdown.

### Step 6: Offer Next Steps

- "Want me to **build an AI product strategy** based on these opportunities?"
- "Should I **design the prompt architecture** for the top use case?"
- "Want me to **model the AI costs** for these features?"
- "Should I **assess AI risks** before committing?"

## Notes

- This is a discovery exercise — the goal is to learn, not to commit
- Be honest about what AI CAN'T do well — saving teams from bad AI bets is high value
- For EdTech products: consider learning efficacy, not just engagement, when evaluating AI value
- Always check data readiness — the best AI idea fails without the right data
