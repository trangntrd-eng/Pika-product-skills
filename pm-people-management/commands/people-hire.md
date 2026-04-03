---
description: Hiring end-to-end — JD, interview design, evaluation, and decision
argument-hint: "<role to hire>"
---

# /people-hire — Hiring End-to-End

Run the full hiring process: write the JD, design interviews, create scorecards, and evaluate candidates.

## Invocation

```
/people-hire Senior Product Manager for Pika Learning team
/people-hire [upload existing JD to improve]
/people-hire                    # asks about the role
```

## Workflow

### Step 1: Understand the Role

Accept context from:
- Staffing plan (from `/people-plan`)
- Existing job description to revise
- Team context and hiring urgency

Ask key questions:
- What role are you hiring for? What level?
- What's the #1 thing this person needs to accomplish in their first 6 months?
- What does your team look like today — what gap does this person fill?
- What's your hiring timeline and budget?

### Step 2: Create the Hiring Scorecard

Apply the **hiring-scorecard** skill:

1. Define success at 6 and 12 months
2. Identify predictive evaluation criteria with weights
3. Set scoring thresholds
4. Identify anti-patterns and non-negotiables

### Step 3: Write the Job Description

Apply the **job-description** skill:

1. Lead with impact, not requirements
2. Write specific "first 6 months" milestones
3. Separate must-have from nice-to-have
4. Check for inclusive language
5. Include compensation range

### Step 4: Design the Interview Process

Apply the **interview-kit** skill:

1. Define competencies to assess per round
2. Assign interviewers to competencies
3. Write structured questions with rubrics
4. Create scoring templates and debrief format
5. Plan the candidate experience

### Step 5: Evaluate Candidates (When Ready)

When candidates have been interviewed, apply the **candidate-evaluation** skill:

1. Aggregate scores per criterion per candidate
2. Compare against the scorecard (not each other)
3. Identify alignment and divergence
4. Produce clear hire/no-hire recommendation

### Step 6: Generate Hiring Package

```markdown
## Hiring Package: [Role Title]

### 1. Hiring Scorecard
[Criteria, weights, thresholds]

### 2. Job Description
[Ready-to-post JD]

### 3. Interview Kit
| Round | Interviewer | Competencies | Duration |
|-------|------------|-------------|----------|
[Questions, rubric, debrief template]

### 4. Candidate Evaluation (when available)
[Comparison matrix, recommendation]

### Timeline
[End-to-end hiring timeline from posting to start date]
```

Save as markdown.

### Step 7: Offer Next Steps

- "Ready to **evaluate candidates**? Share interview feedback and I'll produce a comparison report"
- "Want me to **create an onboarding plan** for the new hire?"
- "Should I **adjust the interview kit** based on early candidate feedback?"

## Notes

- Create the scorecard BEFORE seeing any candidates to avoid anchoring bias
- Great JDs attract great candidates — invest the time
- Structured interviews are 2x more predictive than unstructured ones
- For Vietnam hiring: consider bilingual JDs and whether Vietnamese-language interviews increase signal
- The hiring process IS the employer brand — candidate experience matters
