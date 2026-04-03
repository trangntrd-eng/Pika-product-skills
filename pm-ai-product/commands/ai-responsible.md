---
description: Responsible AI — ethics review, bias detection, risk assessment, and safety guardrails
argument-hint: "<AI feature or product>"
---

# /ai-responsible — Responsible AI Review

Comprehensive responsible AI review: ethics, bias detection, risk assessment, and safety guardrails design.

## Invocation

```
/ai-responsible Pika's AI tutor for children aged 6-12
/ai-responsible [upload AI feature spec or risk register]
/ai-responsible                    # asks about your AI feature
```

## Workflow

### Step 1: Understand the AI Feature & Context

Accept context from:
- AI feature spec or product documentation
- AI strategy or design documents
- User demographics and vulnerability profile
- Regulatory requirements
- Known incidents or concerns

Ask key questions:
- What AI features are in scope?
- Who are the users? Are there vulnerable populations (children, elderly)?
- What decisions does the AI make or influence?
- What happens when the AI is wrong?
- What regulations apply? (COPPA, GDPR, AI Act, etc.)

### Step 2: Conduct Ethics & Bias Review

Apply the **ai-responsible-design** skill:

1. Audit for bias in data, algorithms, and interactions
2. Define fairness criteria per feature
3. Design transparency and AI disclosure mechanisms
4. Build safety guardrails for content and behavior
5. Create accountability framework

### Step 3: Assess AI Risks

Apply the **ai-risk-assessment** skill:

1. Identify risks: hallucination, prompt injection, data leakage, drift
2. Assess likelihood and impact per risk
3. Design mitigations for critical risks
4. Prioritize mitigation actions
5. Create monitoring and incident response plans

### Step 4: Generate Responsible AI Report

```markdown
## Responsible AI Report: [Product/Feature Name]

**Date**: [today]
**Author**: [user]
**Risk Level**: [High / Medium / Low]

### Executive Summary
[Key findings, critical risks, and top recommendations]

### Ethics & Bias Assessment
#### Bias Audit Results
| AI Feature | Bias Type | Affected Group | Severity | Mitigation |
|-----------|-----------|---------------|----------|------------|

#### Fairness Criteria
[Definitions and thresholds per feature]

#### Transparency Requirements
[AI disclosure, explainability, and limitation communication]

### Safety Guardrails
| Risk | Guardrail | Implementation Status |
|------|-----------|---------------------|

### Risk Register
| Risk | Category | Likelihood | Impact | Severity | Mitigation | Owner |
|------|----------|-----------|--------|----------|------------|-------|

### Compliance Status
| Requirement | Status | Gap | Action Needed |
|------------|--------|-----|--------------|

### Recommendations
| Priority | Action | Rationale | Effort |
|----------|--------|-----------|--------|

### Responsible AI Checklist
[Complete checklist with status]
```

Save as markdown.

### Step 5: Offer Next Steps

- "Want me to **design the human-in-the-loop system** for oversight?"
- "Should I **build an evaluation framework** focused on safety metrics?"
- "Want me to **check launch readiness** with safety as a gate?"
- "Should I **design the incident response playbook** for AI failures?"

## Notes

- For children's products: apply the HIGHEST safety standard — zero tolerance for harmful content
- Responsible AI is not a one-time review — schedule periodic re-assessments
- Include diverse perspectives in bias reviews — your team's blind spots are real
- Document decisions and trade-offs — "why we chose this fairness metric" matters
- When in doubt, choose safety over capability
