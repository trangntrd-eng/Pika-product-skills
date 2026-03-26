---
description: Design the full engagement layer — gamification, progression, habits, social features, and parent engagement
argument-hint: "<product or feature to design engagement for>"
---

# /engagement-design -- Engagement & Retention Design Workflow

Design a complete engagement system for a children's EdTech product — from gamification and progression through habit formation, social features, and parent engagement. Every mechanic is designed to reinforce learning, not undermine it.

## Invocation

```
/engagement-design Pika Robot learning platform
/engagement-design Photo-to-Lesson vocabulary feature
/engagement-design Retention improvement sprint for H1 2026
```

## Workflow

### Step 1: Understand the Engagement Context

Ask the user:
1. **What is the current retention problem?** (Churn rate? Where in the lifecycle do users drop off? Low session frequency?)
2. **What learning behaviors should engagement drive?** (Daily practice? Review? Exploration? Deeper focus?)
3. **What's the target age range and family context?**
4. **What engagement mechanics exist today?** (Any gamification, streaks, rewards already in place?)

Check for existing product context: user feedback, retention data, feature reports.

### Step 2: Design Gamification System

Apply the `design-gamification-system` skill.

- Define gamification philosophy (what to reinforce, what to never do)
- Design reward economy (currency, badges, collectibles)
- Design level/progression system tied to learning milestones
- Output: `gamification-system-[product].md`

**Checkpoint:** Review the reward economy. Ask: "Can a child earn maximum rewards without actually learning? If yes, we need to redesign."

### Step 3: Design Progression Mechanics

Apply the `design-progression-mechanics` skill.

- Define progression axes (mastery, difficulty, fluency, breadth)
- Design difficulty curve (sawtooth recommended)
- Design skill tree / progress map
- Output: `progression-mechanics-[product].md`

### Step 4: Design Habit Loops

Apply the `design-habit-loops` skill.

- Map habit context (when/where/why children practice)
- Design trigger system (ethical notifications + internal triggers)
- Design streak system (positive framing, no punishment)
- Design session start/end experiences
- Output: `habit-loops-[product].md`

**Checkpoint:** Ask: "Would a parent be happy knowing their child has this habit? If the answer isn't clearly yes, redesign."

### Step 5: Design Social Learning Features

Apply the `design-social-learning` skill.

- Choose social learning goals (family, cooperative, teaching)
- Design family learning features
- Design age-appropriate peer features
- Define safety infrastructure
- Output: `social-learning-[product].md`

### Step 6: Design Parent Engagement

Apply the `design-parent-engagement` skill.

- Map parent journey from discovery to renewal
- Design parent dashboard and communication cadence
- Create conversation starters
- Design renewal decision support
- Output: `parent-engagement-[product].md`

### Step 7: Synthesize into Engagement Design Brief

```markdown
# Engagement Design Brief: [Product Name]

## Engagement Philosophy
[Core principle: engagement serves learning, not the reverse]

## Gamification Summary
[Key mechanics, reward economy overview]

## Progression System
[Model, key milestones, difficulty curve]

## Habit System
[Target frequency, trigger strategy, streak design]

## Social Features
[What's included, age-gating, safety approach]

## Parent Engagement
[Dashboard, communication cadence, renewal strategy]

## Ethical Guardrails
[What we explicitly will NOT do]

## Expected Impact on Metrics
| Metric | Current | Target | Mechanic |
|--------|---------|--------|----------|
| D7 retention | [%] | [%] | [which mechanic] |
| Weekly active rate | [%] | [%] | [which mechanic] |
| Sessions per week | [N] | [N] | [which mechanic] |
| Parent dashboard open rate | [%] | [%] | [which mechanic] |
| Subscription renewal rate | [%] | [%] | [which mechanic] |
```

Save as `engagement-design-brief-[product].md`.

### Step 8: Offer Next Steps

- **"Want me to run a child safety review on these features?"** → `/child-safety`
- **"Want me to design the learning layer first?"** → `/learning-design`
- **"Want me to write a PRD for the engagement system?"** → `/write-prd` with engagement brief as context
- **"Want me to measure if this is working?"** → Apply `evaluate-learning-efficacy`

## Notes

- Engagement design should come AFTER learning design, not before. Know what you're teaching before designing how to make it engaging.
- Always cross-reference engagement features with the `/child-safety` review. Gamification mechanics are the most common source of dark pattern violations in EdTech.
- Parent engagement is often the highest-ROI investment for B2C EdTech retention, yet it's the most commonly neglected. Prioritize it.
