---
name: design-learning-objectives
description: "Design measurable learning objectives using Backward Design and Bloom's Revised Taxonomy. Use when defining what learners should know, do, or feel after completing a learning experience — before designing content, UI, or assessments."
---

## Design Learning Objectives

Learning objectives are the foundation every EdTech feature is built on. A feature without clear learning objectives is entertainment, not education. This skill ensures every learning experience starts from the outcome and works backward to the experience — not the other way around.

### Domain Context

This skill applies **Backward Design** (Wiggins & McTighe, *Understanding by Design*, 2005) — the principle that effective learning experiences are designed by first identifying desired results, then determining acceptable evidence, and only then planning the learning experience.

Learning objectives are structured using **Bloom's Revised Taxonomy** (Anderson & Krathwohl, 2001), which organizes cognitive processes into six levels:

| Level | Cognitive Process | What the Learner Does | Example Verbs |
|-------|------------------|----------------------|---------------|
| 1. Remember | Retrieve knowledge | Recall facts, terms, concepts | define, list, recall, recognize |
| 2. Understand | Construct meaning | Explain, summarize, classify | describe, explain, paraphrase |
| 3. Apply | Use in new situations | Solve, demonstrate, use | calculate, implement, solve |
| 4. Analyze | Break into parts | Compare, contrast, organize | differentiate, distinguish, examine |
| 5. Evaluate | Make judgments | Critique, justify, assess | argue, defend, judge, support |
| 6. Create | Produce new work | Design, construct, develop | compose, design, formulate, invent |

**Critical principle for EdTech PMs:** Most consumer EdTech products operate at levels 1-3 (Remember, Understand, Apply). Levels 4-6 require more complex interaction design and are where differentiation happens. Know which level your feature targets — it determines everything from content format to assessment type to session length.

**For children's products specifically:** Bloom's levels must be cross-referenced with developmental stage. A 6-year-old can *Create* (finger painting, storytelling) but not *Evaluate* (critical analysis). The taxonomy applies within age-appropriate bounds.

### Context

You are a learning experience designer defining learning objectives for **$ARGUMENTS**.

### Instructions

1. **Identify the Target Learner**

   Before writing any objective, establish:
   - **Age range** and developmental stage (Piaget: preoperational 2-7, concrete operational 7-11, formal operational 11+)
   - **Prior knowledge** — what do they already know? What's the entry point?
   - **Motivation context** — intrinsic (curiosity, mastery) vs. extrinsic (grades, parent pressure, rewards)
   - **Learning environment** — solo on mobile, with parent, in classroom, with robot companion

2. **Define the Desired Outcome (Stage 1 of Backward Design)**

   Answer: "After completing this experience, the learner will be able to ___."

   Write 3-7 learning objectives using the **ABCD formula**:
   - **A**udience — Who is learning? (e.g., "A 7-year-old Vietnamese student")
   - **B**ehavior — What will they do? Use a Bloom's verb. (e.g., "will explain")
   - **C**ondition — Under what circumstances? (e.g., "given a set of mixed fractions")
   - **D**egree — To what standard? (e.g., "correctly sorting at least 4 out of 5")

   Example:
   > A 7-year-old student (A), given a photo of a real-world scene (C), will identify and name (B) at least 3 English vocabulary words depicted in the image with correct pronunciation (D).

3. **Map Objectives to Bloom's Levels**

   For each objective, tag the Bloom's level. Check the distribution:
   - **Imbalanced toward Remember/Understand?** The feature risks being a flashcard clone. Consider adding Apply or Analyze objectives.
   - **Heavy on Create/Evaluate?** Verify the target age group can reach these levels. Check if the interaction design supports it.
   - **Right distribution depends on product stage:** An onboarding flow should favor Remember/Understand. A mastery module should push toward Apply/Analyze.

4. **Define Acceptable Evidence (Stage 2 of Backward Design)**

   For each objective, specify how you'll know the learner achieved it:
   - What **observable behavior** demonstrates mastery?
   - What's the **minimum threshold** (e.g., 80% correct, 3 consecutive successes)?
   - What **data** will the product collect to measure this?

   This directly feeds into the `design-assessment` skill.

5. **Sequence Objectives into a Learning Progression**

   Order objectives from foundational to advanced using prerequisite logic:
   - Which objectives must be achieved before others unlock?
   - Where are the natural "checkpoint" moments?
   - What's the expected time-to-mastery for each objective?

   Output as a dependency graph:
   ```
   Objective 1 (Remember) ─┬─→ Objective 3 (Apply)
   Objective 2 (Understand) ┘         │
                                       ├─→ Objective 5 (Analyze)
   Objective 4 (Apply) ───────────────┘
   ```

6. **Validate Against Product Constraints**

   Cross-check objectives against reality:
   - **Session length** — Can this objective be meaningfully progressed in one session (typically 5-15 min for children)?
   - **Interaction modality** — Does the app/device support the required interaction? (Voice? Touch? Camera? Robot?)
   - **Content availability** — Does content exist or need to be created for each objective?
   - **Measurement feasibility** — Can the product actually detect whether the objective was met?

### Output Format

```markdown
# Learning Objectives: [Feature/Module Name]

## Target Learner Profile
- **Age range**: [e.g., 6-8 years old]
- **Developmental stage**: [Piaget stage]
- **Prior knowledge**: [assumed baseline]
- **Motivation context**: [intrinsic/extrinsic drivers]
- **Learning environment**: [context of use]

## Learning Objectives

| # | Objective (ABCD) | Bloom's Level | Evidence of Mastery | Priority |
|---|-------------------|---------------|--------------------:|----------|
| 1 | [Full ABCD statement] | [Level] | [Observable behavior + threshold] | Must-have |
| 2 | ... | ... | ... | ... |

## Bloom's Distribution
- Remember: [count] objectives
- Understand: [count]
- Apply: [count]
- Analyze: [count]
- Evaluate: [count]
- Create: [count]

## Learning Progression
[Dependency graph showing prerequisite relationships]

## Constraints Check
| Constraint | Status | Notes |
|-----------|--------|-------|
| Session length fit | ✅/⚠️/❌ | [details] |
| Interaction support | ✅/⚠️/❌ | [details] |
| Content availability | ✅/⚠️/❌ | [details] |
| Measurement feasibility | ✅/⚠️/❌ | [details] |
```

Save as `learning-objectives-[feature-name].md`.

### Further Reading
- Wiggins, G. & McTighe, J. (2005). *Understanding by Design* (2nd ed.). ASCD.
- Anderson, L. W. & Krathwohl, D. R. (2001). *A Taxonomy for Learning, Teaching, and Assessing*. Pearson.
- Clark, R. C. & Mayer, R. E. (2016). *e-Learning and the Science of Instruction* (4th ed.). Wiley.
- Hattie, J. (2008). *Visible Learning*. Routledge. (Meta-analysis of effect sizes for learning objectives: d = 0.56)
