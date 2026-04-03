---
description: Team health check — morale, workload, collaboration, and psychological safety
argument-hint: "<team name>"
---

# /people-health — Team Health Check

Diagnose team health across morale, workload, collaboration, psychological safety, and alignment — with specific actions to improve.

## Invocation

```
/people-health Pika product team
/people-health [upload recent survey results or 1:1 notes]
/people-health                    # asks about your team
```

## Workflow

### Step 1: Gather Context

Accept context from:
- Team structure and recent changes
- Manager observations and concerns
- Survey data, 1:1 notes, or Slack sentiment
- Recent project outcomes (successes and failures)
- Departure or retention data

Ask key questions:
- How many people are on the team? What roles?
- Any recent changes? (new members, departures, reorgs, project shifts)
- What's your gut feeling about team health right now?
- Any specific concerns? (burnout, conflict, disengagement, turnover)

### Step 2: Run the Health Check

Apply the **team-health-check** skill:

1. Assess each health dimension (psychological safety, workload, clarity, collaboration, growth, morale, management, alignment)
2. Rate each as Green/Yellow/Red with trend direction
3. Connect symptoms to root causes
4. Identify what's working (protect it)
5. Prioritize the top 3 interventions

### Step 3: Generate Report

```markdown
## Team Health Check: [Team Name]

**Date**: [today]
**Team size**: [N]
**Overall health**: [Green / Yellow / Red]

### Health Dashboard
| Dimension | Status | Trend | Key Signal |
|-----------|--------|-------|-----------|
[8 dimensions with ratings]

### What's Working Well
[Strengths to protect — don't take for granted]

### Areas of Concern
[For each Yellow/Red: symptoms, root cause, recommendation]

### Top 3 Actions
| # | Action | Owner | Timeline | Impact |
|---|--------|-------|----------|--------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

### Survey Template
[Optional: 8-question pulse survey for the team]

### Follow-up Plan
[When to re-assess, what to watch for]
```

Save as markdown.

### Step 4: Offer Next Steps

- "Want me to **run the pulse survey** with your team? Here's the template"
- "Should I **create a team retrospective** to address the top concern?"
- "Want me to **assess team capabilities** to see if workload issues are a skills gap?"
- "Should I **build a staffing plan** if the root cause is understaffing?"

## Notes

- Run health checks proactively (quarterly), not reactively (after someone quits)
- Anonymous data gets more honest results than direct questions from the manager
- The manager IS the team health — start with self-reflection
- In Vietnamese teams: hierarchy can mask real sentiment. Create psychologically safe channels
- Fix 1-2 things well > try to fix everything at once
