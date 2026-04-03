---
description: Design AI experiences — prompt architecture, UX patterns, and human-in-the-loop systems
argument-hint: "<AI feature to design>"
---

# /ai-design — AI Experience Design

Design the complete AI experience: prompt architecture, UX patterns for AI interactions, and human oversight systems.

## Invocation

```
/ai-design Pika's AI conversation partner for kids
/ai-design [upload feature spec or wireframes]
/ai-design                    # asks about your AI feature
```

## Workflow

### Step 1: Understand the AI Feature

Accept context from:
- Feature spec, PRD, or user stories
- AI strategy document (from `/ai-strategy`)
- Wireframes or prototypes
- Current implementation (if iterating)

Ask key questions:
- What does the AI feature do from the user's perspective?
- What AI model/approach is being used?
- What are the known failure modes?
- Who are the users? (age, technical level, context)

### Step 2: Design Prompt Architecture

Apply the **ai-prompt-strategy** skill:

1. Design system prompts (role, rules, guardrails, format)
2. Create prompt templates with context injection points
3. Define few-shot examples for consistency
4. Build a golden test set for evaluation
5. Establish versioning and A/B testing strategy

### Step 3: Design AI UX Patterns

Apply the **ai-ux-patterns** skill:

1. Select loading/progress patterns (streaming, skeleton, etc.)
2. Design confidence and transparency displays
3. Plan error states and graceful degradation
4. Design user control mechanisms (edit, regenerate, opt-out)
5. Plan feedback collection UI

### Step 4: Design Human-in-the-Loop Systems

Apply the **ai-human-in-the-loop** skill:

1. Assign automation level per decision type
2. Design escalation triggers and paths
3. Build feedback loop architecture
4. Define quality control and sampling
5. Plan the human reviewer experience

### Step 5: Generate Design Spec

```markdown
## AI Experience Design: [Feature Name]

**Date**: [today]
**Author**: [user]

### Feature Overview
[What the AI feature does, who uses it, why it matters]

### Prompt Architecture
#### System Prompt
[Full system prompt with role, rules, guardrails]

#### Template Structure
[How dynamic context is injected]

#### Versioning Strategy
[How prompts are versioned, tested, and deployed]

### UX Patterns
#### Loading & Progress
[Selected patterns with rationale]

#### Confidence & Transparency
[How AI certainty is communicated]

#### Error & Recovery
[What happens when AI fails]

#### User Control
[Edit, regenerate, opt-out capabilities]

### Human-in-the-Loop
#### Automation Levels
| Decision Type | AI Autonomy | Human Role | Escalation Trigger |
|--------------|-------------|-----------|-------------------|

#### Feedback Loop
[How user feedback improves AI over time]

### Test Plan
[Golden test set, edge cases, evaluation criteria]
```

Save as markdown.

### Step 6: Offer Next Steps

- "Want me to **assess AI risks** for this feature?"
- "Should I **build an evaluation framework** to measure quality?"
- "Want me to **check AI launch readiness**?"
- "Should I **review this for responsible AI practices**?"

## Notes

- Prompt design IS product design for LLM features — treat it with the same rigor
- Always design the failure experience first — AI will fail, and users need a good experience when it does
- For children: simplify AI interactions, maximize safety guardrails, minimize open-ended generation
- Test with real AI output (including bad ones), not mocked perfect responses
