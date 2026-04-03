---
description: Team planning — staffing, capability assessment, and succession planning
argument-hint: "<team or product area>"
---

# /people-plan — Team Planning

Plan your team strategically: assess current capabilities, build a staffing plan tied to the roadmap, and create succession plans for key roles.

## Invocation

```
/people-plan Pika product team for H2 2026
/people-plan [upload team roster and roadmap]
/people-plan                    # asks about your team
```

## Workflow

### Step 1: Understand the Team & Context

Accept context from:
- Team roster, org chart, or people spreadsheet
- Product roadmap and milestones
- Budget constraints
- Recent or upcoming changes (departures, reorgs)

Ask key questions:
- What's your team structure today? (roles, levels, count)
- What does your roadmap demand in the next 6-12 months?
- Are there any known gaps, bottlenecks, or flight risks?
- What's your hiring budget and timeline?

### Step 2: Assess Current Capabilities

Apply the **team-capability-assessment** skill:

1. Map the roadmap to required skills
2. Assess each team member against requirements
3. Identify strengths, gaps, and key-person dependencies
4. Recommend: hire, upskill, restructure, or adjust scope

### Step 3: Build the Staffing Plan

Apply the **team-staffing-plan** skill:

1. Tie each hire request to a roadmap outcome
2. Prioritize by impact and urgency
3. Build the financial case
4. Create a hiring timeline
5. Define contingency plans

### Step 4: Plan Succession

Apply the **succession-planning** skill:

1. Identify key-person risks (bus factor = 1)
2. Map potential successors
3. Design development plans for successors
4. Create immediate risk mitigations

### Step 5: Generate Team Plan

```markdown
## Team Plan: [Team Name] — [Period]

**Date**: [today]
**Team size**: [current] → [planned]

### Capability Assessment Summary
| Dimension | Status | Key Gaps |
|-----------|--------|----------|

### Staffing Plan
| Priority | Role | Start By | Roadmap Dependency | Status |
|----------|------|----------|--------------------|--------|

### Succession Plan
| Critical Role | Bus Factor | Successor | Readiness |
|--------------|-----------|-----------|-----------|

### Budget Summary
[Cost table]

### Action Items
[Prioritized next steps]
```

Save as markdown.

### Step 6: Offer Next Steps

- "Want me to **write job descriptions** for the priority hires?"
- "Should I **design interview kits** for these roles?"
- "Want me to **run a team health check** to complement this assessment?"
- "Should I **create career ladders** for the team?"

## Notes

- Revisit this plan quarterly as roadmaps evolve
- Staffing plans that aren't connected to roadmap outcomes get rejected by finance
- Capability assessment works best with input from the team, not just the manager's view
- For Vietnam tech market: factor in competitive salaries and hiring timelines for scarce skills
