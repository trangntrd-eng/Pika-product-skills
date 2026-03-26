---
name: design-learning-path
description: "Design adaptive learning paths that personalize progression based on learner performance, preferences, and goals. Use when defining how different learners move through your curriculum differently — branching logic, adaptive difficulty, personalization rules, and path visualization."
---

## Design Learning Path

A learning path is the route a specific learner takes through your curriculum. While curriculum structure defines *what* exists, the learning path defines *how each individual moves through it*. In consumer EdTech, path design is the primary lever for both learning efficacy and retention — learners who feel the product is "just right" for them stay longer and learn more.

### Domain Context

**Vygotsky's Zone of Proximal Development (ZPD, 1978)** is the theoretical foundation. Every learner has:
- A **comfort zone** — what they can do independently (too easy = boredom)
- A **ZPD** — what they can do with guidance (the productive struggle zone)
- A **frustration zone** — what they cannot yet do even with help (too hard = abandonment)

The ideal learning path keeps the learner in their ZPD at all times. This is the core challenge of adaptive EdTech.

**Flow Theory (Csikszentmihalyi, 1990)** adds the engagement dimension. Flow occurs when challenge matches skill. The "flow channel" is narrow — slightly too easy and the learner is bored, slightly too hard and they're anxious. Learning path design is essentially flow channel maintenance.

**Adaptive learning systems exist on a spectrum:**

| Level | Adaptation | Complexity | Example |
|-------|-----------|------------|---------|
| 0 | Fixed | None — all learners take same path | Traditional courses |
| 1 | Branching | If-then rules based on assessment | Most EdTech apps |
| 2 | Algorithmic | Spaced repetition + mastery gating | Duolingo, Khan Academy |
| 3 | Model-based | Bayesian knowledge tracing, IRT | ALEKS, DreamBox |
| 4 | AI-driven | ML-based learner modeling | Emerging (few production examples) |

**For most B2C EdTech products, Level 1-2 is the right starting point.** Level 3+ requires significant data science investment and large user bases for model training. Start simple, add sophistication as you accumulate learner data.

### Context

You are designing the adaptive learning path system for **$ARGUMENTS**.

### Instructions

1. **Define Path Entry Points**

   How do learners enter the path?
   - **Default start:** All learners begin at Module 1, Lesson 1 (simplest, fine for narrow age-range products).
   - **Diagnostic placement:** Placement test determines starting point (better for wide skill ranges).
   - **Self-selection:** Learner (or parent) chooses starting level (risky — learners overestimate their level).
   - **Hybrid:** Quick diagnostic with self-selection override.

   For each entry point, define what data is needed and what happens next.

2. **Design the Progression Model**

   **Linear progression** (simplest):
   ```
   L1 → L2 → L3 → L4 → [Gate] → L5 → L6 → ...
   ```
   Good for: Sequential subjects (math, language grammar). Easy to build. Clear progress indicators.

   **Branching progression** (moderate):
   ```
   L1 → L2 → [Gate]
                ├─ Pass → L3a (advanced track)
                └─ Fail → L3b (review track) → L2 retry
   ```
   Good for: Differentiated pacing. Learners who struggle get more practice without blocking.

   **Network/graph progression** (complex):
   ```
   L1 ──→ L3 ──→ L5
    └──→ L2 ──→ L4 ──┘
         └──→ L6
   ```
   Good for: Non-sequential subjects (vocabulary, independent skills). Learner choice within constraints.

   **Choose based on:**
   - Subject linearity — Math is linear; vocabulary is a graph.
   - Learner autonomy — Young children need linear structure; older learners benefit from choice.
   - Content volume — Branching requires 1.5-2x the content of linear paths.

3. **Define Adaptation Rules**

   For each decision point in the path, specify the rule:

   | Trigger | Condition | Action | Rationale |
   |---------|-----------|--------|-----------|
   | Mastery gate passed | Score ≥ 80% | Advance to next unit | Standard progression |
   | Mastery gate failed | Score < 80%, 1st attempt | Offer review lesson, retry | One failure = normal |
   | Mastery gate failed twice | Score < 80%, 2nd attempt | Branch to remediation path | Needs different approach |
   | High performance streak | 5 correct, <3s each | Skip next 2 practice items | Already fluent, avoid boredom |
   | Declining performance | 3 consecutive errors | Reduce difficulty, add scaffolding | Entering frustration zone |
   | Long absence | >7 days since last session | Start with review of last 3 mastered concepts | Ebbinghaus decay |
   | Session too short | <2 min for 3 sessions | Surface easier/more engaging content | Re-engagement needed |

4. **Design the Review/Maintenance System**

   Learned content decays. The path must include maintenance:
   - **Spaced review queue:** Previously mastered items are scheduled for review at increasing intervals (1 day, 3 days, 7 days, 14 days, 30 days).
   - **Review-to-new ratio:** In any session, what percentage is review vs. new content? (Common: 30% review, 70% new for active learners. 50/50 after long absence.)
   - **Decay detection:** If a review item is answered incorrectly, it re-enters the active learning queue.

5. **Design Progress Visualization**

   How the learner (and parent) sees their path:
   - **Map metaphor:** Visual journey with locations (common in children's apps — cf. Duolingo, Cookie Run)
   - **Tree/branch metaphor:** Skill tree showing mastered and available nodes
   - **Linear bar:** Simple progress bar with percentage (effective but less engaging)
   - **Dashboard:** For parents — charts showing time, mastery, pace, areas of strength/weakness

   Key principles:
   - Show *progress*, not just *position*. "You've mastered 23 words!" > "You're on Level 3."
   - Never show how much is left to younger children (overwhelming). Do show it to parents.
   - Celebrate mastery visibly — the path visualization should make achievements feel tangible.

6. **Handle Edge Cases**

   Define behavior for:
   - **Gifted learner:** Races through content — do you let them finish the curriculum early? Offer enrichment? Cap daily progress?
   - **Struggling learner:** Stuck on the same concept for weeks — when do you suggest external help? How do you prevent discouragement?
   - **Irregular learner:** Uses the app once a week — how much review vs. new content? How does the path adapt to sporadic use?
   - **Multi-device/multi-context:** Same child learns on phone and robot — does path state sync? How?
   - **Curriculum reset:** Parent wants to restart — what happens to progress data?

### Output Format

```markdown
# Learning Path Design: [Product/Feature Name]

## Entry Points
| Entry Type | Who | Trigger | Data Needed | Starting Position |
|-----------|-----|---------|-------------|-------------------|
| [type] | [learner profile] | [how they enter] | [diagnostic/selection] | [where they start] |

## Progression Model
**Model type**: [linear / branching / network]
**Rationale**: [why this model fits]

[Visual diagram of path structure]

## Adaptation Rules
| Trigger | Condition | Action | Fallback |
|---------|-----------|--------|----------|
| [event] | [threshold] | [system response] | [if action fails] |

## Review System
- **Algorithm**: [spaced repetition variant / interval schedule]
- **Review-to-new ratio**: [X% review, Y% new]
- **Decay detection**: [how incorrect reviews are handled]

## Progress Visualization
- **Learner-facing**: [metaphor + description]
- **Parent-facing**: [dashboard elements]

## Edge Cases
| Scenario | Detection | Response |
|----------|-----------|----------|
| [edge case] | [how detected] | [system behavior] |
```

Save as `learning-path-[feature-name].md`.

### Further Reading
- Vygotsky, L. S. (1978). *Mind in Society*. Harvard University Press.
- Csikszentmihalyi, M. (1990). *Flow: The Psychology of Optimal Experience*. Harper & Row.
- Corbett, A. T. & Anderson, J. R. (1994). "Knowledge tracing: Modeling the acquisition of procedural knowledge." *User Modeling and User-Adapted Interaction*, 4(4). (Foundational paper for adaptive learning algorithms)
- VanLehn, K. (2011). "The Relative Effectiveness of Human Tutoring, Intelligent Tutoring Systems, and Other Tutoring Systems." *Educational Psychologist*, 46(4).
