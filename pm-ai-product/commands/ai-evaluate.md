---
description: AI quality evaluation — metrics framework, eval pipelines, and launch readiness checklist
argument-hint: "<AI feature to evaluate>"
---

# /ai-evaluate — AI Evaluation & Launch Readiness

Design AI quality evaluation systems and assess launch readiness for AI features.

## Invocation

```
/ai-evaluate Pika's AI speech assessment engine
/ai-evaluate [upload current AI metrics or test results]
/ai-evaluate                    # asks about your AI feature
```

## Workflow

### Step 1: Understand What to Evaluate

Accept context from:
- AI feature spec and quality requirements
- Current evaluation practices and metrics
- Known quality issues
- Launch timeline

Ask key questions:
- What AI features need evaluation?
- What does "good enough" look like for users?
- Do you have existing evaluation data or test sets?
- When is the launch target?

### Step 2: Design Evaluation Framework

Apply the **ai-evaluation-framework** skill:

1. Define quality metrics per feature (accuracy, safety, latency, etc.)
2. Create metric hierarchy (North Star → supporting metrics)
3. Design offline evaluation pipeline (golden test sets, automated scoring)
4. Design online evaluation (A/B testing, implicit signals)
5. Create human evaluation rubric and sampling plan
6. Set up dashboard and alerting specifications

### Step 3: Assess Launch Readiness

Apply the **ai-launch-readiness** skill:

1. Review quality gates (accuracy, safety, latency targets)
2. Check monitoring and observability setup
3. Verify rollback and incident response plans
4. Assess scaling and performance readiness
5. Confirm compliance and legal requirements
6. Design staged rollout plan

### Step 4: Generate Evaluation & Readiness Report

```markdown
## AI Evaluation & Launch Readiness: [Feature Name]

**Date**: [today]
**Author**: [user]
**Verdict**: [GO / GO WITH CONDITIONS / NOT READY]

### Part 1: Evaluation Framework

#### Quality Metrics
| Feature | Metric | Target | Current | Status |
|---------|--------|--------|---------|--------|

#### Metric Hierarchy
[North Star → supporting metrics tree]

#### Evaluation Pipeline
- **Offline**: [Golden test set size, automated scoring approach]
- **Online**: [A/B testing plan, signal collection]
- **Human**: [Rubric, sampling rate, reviewer count]

#### Dashboard Specifications
[Key metrics, refresh rate, alert thresholds]

### Part 2: Launch Readiness

#### Readiness Scorecard
| Category | Status | Blockers |
|----------|--------|----------|
| Quality Gates | | |
| Monitoring | | |
| Rollback Plan | | |
| Scaling | | |
| Compliance | | |

#### Rollout Plan
| Stage | % Users | Duration | Success Criteria | Rollback Trigger |
|-------|---------|----------|-----------------|-----------------|

#### Open Items
| Item | Priority | Owner | ETA |
|------|----------|-------|-----|

### Verdict & Recommendations
[GO / NO-GO with clear reasoning and conditions]
```

Save as markdown.

### Step 5: Offer Next Steps

- "Want me to **run a responsible AI review** before launch?"
- "Should I **design the prompt testing framework** in more detail?"
- "Want me to **model post-launch monitoring costs**?"
- "Should I **create the incident response playbook**?"

## Notes

- Evaluation before launch is table stakes — continuous evaluation after launch is what separates great AI products
- If you can't measure it, you can't improve it — invest in eval infrastructure early
- Launch readiness is a checklist, not a feeling — go through every item
- For children's products: safety gates are non-negotiable blockers, not "nice to have"
- When in doubt about readiness, delay launch — AI trust is hard to rebuild once lost
