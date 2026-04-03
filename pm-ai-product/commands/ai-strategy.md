---
description: AI product strategy — vision, build-vs-buy decisions, model selection, and cost modeling
argument-hint: "<product or AI capability>"
---

# /ai-strategy — AI Product Strategy

Define your AI product strategy: how AI creates defensible value, what to build vs. buy, which models to use, and what it will cost.

## Invocation

```
/ai-strategy Pika's AI-powered learning companion
/ai-strategy [upload AI discovery report or product brief]
/ai-strategy                    # asks about your product
```

## Workflow

### Step 1: Understand Context

Accept context from:
- AI Discovery Report (from `/ai-discover`)
- Product brief, PRD, or strategy documents
- Current AI capabilities and tech stack
- Competitive landscape

Ask key questions:
- What AI capabilities are you building?
- What's your current AI stack? (models, infra, team)
- Who are your AI-powered competitors?
- What's your timeline and budget?

### Step 2: Define AI Product Strategy

Apply the **ai-product-strategy** skill:

1. Define the AI vision — what AI uniquely enables
2. Map the AI value chain (data → model → features → feedback)
3. Design the AI flywheel
4. Identify AI differentiation vs. competitors
5. Create a phased AI roadmap

### Step 3: Make Build vs. Buy Decisions

Apply the **ai-build-vs-buy** skill for each AI capability:

1. Classify as core differentiator vs. commodity
2. Evaluate build / fine-tune / API / open-source options
3. Score on cost, performance, time, risk, privacy
4. Recommend with migration paths

### Step 4: Select Models

Apply the **ai-model-selection** skill:

1. Define requirements per use case
2. Compare candidate models on capability, cost, latency, safety
3. Recommend primary + fallback models
4. Design multi-model architecture if needed

### Step 5: Model Costs

Apply the **ai-cost-modeling** skill:

1. Calculate per-request costs
2. Project monthly costs across growth scenarios
3. Analyze impact on unit economics
4. Identify optimization levers and break-even points

### Step 6: Generate Strategy Document

```markdown
## AI Product Strategy: [Product Name]

**Date**: [today]
**Author**: [user]

### 1. AI Vision
[How AI transforms the product — 2-3 sentences]

### 2. AI Value Chain
Data Acquisition → Processing → Intelligence → Features → Feedback Loop

### 3. AI Differentiation
| Dimension | Our Advantage | Competition | Defensibility |
|-----------|--------------|-------------|---------------|

### 4. AI Flywheel
[How usage compounds into better AI]

### 5. Build vs. Buy Decisions
| Capability | Decision | Rationale | Migration Path |
|-----------|----------|-----------|----------------|

### 6. Model Architecture
| Use Case | Primary Model | Fallback | Cost/Request |
|----------|--------------|----------|-------------|

### 7. Cost Projections
| Timeline | Monthly AI Cost | Cost/User | Gross Margin Impact |
|----------|---------------|-----------|-------------------|

### 8. AI Roadmap
- **Phase 1**: [Foundation]
- **Phase 2**: [Differentiation]
- **Phase 3**: [Compounding moat]

### 9. Strategic Risks
[Top 3 risks and mitigations]
```

Save as markdown.

### Step 7: Offer Next Steps

- "Want me to **design the AI UX experience** for these features?"
- "Should I **assess responsible AI requirements**?"
- "Want me to **design the prompt architecture**?"
- "Should I **create an AI launch readiness checklist**?"

## Notes

- AI strategy should serve product strategy, not the other way around
- The real moat is data + feedback loops, not model choice
- Don't over-invest in model selection — models commoditize, switch cost is lower than you think
- For EdTech: AI strategy must serve learning outcomes, not just engagement metrics
