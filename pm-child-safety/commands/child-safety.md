---
description: Run a comprehensive child safety and compliance review for a children's EdTech product
argument-hint: "<product or feature to audit>"
---

# /child-safety -- Child Safety & Compliance Review

Run a full safety and compliance review for a children's EdTech product. Produces a compliance audit, identifies gaps, and generates actionable remediation plans across privacy, consent, data practices, and UX safety.

## Invocation

```
/child-safety Pika Robot learning platform
/child-safety Photo-to-Lesson feature launch review
/child-safety Pre-launch compliance checklist for Vietnam + US markets
```

## Workflow

### Step 1: Scope the Review

Ask the user:
1. **What product/feature is being reviewed?**
2. **What markets do you serve?** (US, EU, Vietnam, other — determines which regulations apply)
3. **What is the target age range?**
4. **Is this a new launch, a feature addition, or a periodic review?**

Review any existing compliance documentation, privacy policies, or prior audits in the project context.

### Step 2: Run Compliance Audit

Apply the `assess-coppa-compliance` skill.

- Determine regulatory scope
- Inventory all data collection
- Assess consent mechanism, privacy notices, data practices
- Audit third-party services
- Output: `compliance-audit-[product].md`

**Checkpoint:** Share the compliance scorecard. Ask: "Are there any data practices or third-party services I'm missing?"

### Step 3: Audit Data Minimization

Apply the `audit-data-minimization` skill.

- Apply the necessity test to each data point
- Propose less-identifying alternatives
- Audit SDK data collection
- Define data lifecycle and retention
- Output: `data-minimization-audit-[product].md`

### Step 4: Review Consent Flow

Apply the `design-parental-consent` skill.

- Determine required consent level based on data practices
- Design or review the 5-stage consent flow
- Design consent management dashboard for parents
- Output: `parental-consent-[product].md`

### Step 5: Review Age Gating

Apply the `design-age-gating` skill.

- Define age bands with feature access rules
- Map UI adaptations by age
- Design transition experiences
- Output: `age-gating-[product].md`

### Step 6: Review UX Safety

Apply the `design-safe-ux` skill.

- Audit for dark patterns and manipulative design
- Review content safety (AI and UGC)
- Review session management and communication safety
- Output: `safe-ux-design-[product].md`

### Step 7: Generate Executive Safety Report

Synthesize all findings into a single report:

```markdown
# Child Safety Review: [Product Name]
## Date: [date]

## Overall Safety Rating: [Green / Yellow / Red]

## Critical Findings (Must Fix Before Launch)
1. [Finding + remediation + owner + deadline]

## Important Findings (Fix Within 30 Days)
1. [Finding + remediation]

## Recommendations (Improvement Opportunities)
1. [Recommendation]

## Compliance Status by Regulation
| Regulation | Status | Key Gaps |
|-----------|--------|----------|
| COPPA | [status] | [gaps] |
| GDPR-K | [status] | [gaps] |
| Vietnam PDPD | [status] | [gaps] |
| App Store | [status] | [gaps] |

## Artifacts Generated
- [ ] compliance-audit-[product].md
- [ ] data-minimization-audit-[product].md
- [ ] parental-consent-[product].md
- [ ] age-gating-[product].md
- [ ] safe-ux-design-[product].md
```

Save as `child-safety-review-[product].md`.

### Step 8: Offer Next Steps

- **"Want me to draft the privacy policy?"** → Use findings to generate a COPPA-compliant privacy policy
- **"Want me to create tickets for remediation?"** → Break findings into actionable engineering tasks
- **"Want me to design the feedback system with safety in mind?"** → Route to `/learning-design`

## Notes

- This review is a starting point, not a legal opinion. Always have findings reviewed by legal counsel before making compliance claims.
- Re-run this review when: entering new markets, adding features that collect new data types, changing third-party services, or at minimum annually.
- For products in the Apple Kids Category or Google Play Families program, app store policies are often stricter than the law. Design for the strictest applicable standard.
