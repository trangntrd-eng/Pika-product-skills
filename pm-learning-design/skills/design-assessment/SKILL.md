---
name: design-assessment
description: "Design formative and summative assessments that measure real learning, not just engagement. Use when defining how your EdTech product will determine whether learners actually learned what you intended — quizzes, performance tasks, mastery gates, and diagnostic checks."
---

## Design Assessment

Assessment is how your EdTech product knows whether learning happened. Without well-designed assessment, you're measuring time-on-task and completion rates — vanity metrics that tell you nothing about efficacy. This skill produces assessment designs that are valid (measure what they claim to), reliable (consistent results), and developmentally appropriate.

### Domain Context

**Assessment taxonomy for EdTech PMs:**

**Formative Assessment** (assessment *for* learning — during the experience)
- Purpose: Guide instruction, provide real-time feedback, adapt difficulty.
- In-product form: Practice problems, check-your-understanding prompts, embedded questions, error analysis.
- Frequency: Continuous — every interaction can be formative.
- Stakes: Zero. The learner should feel safe to fail.

**Summative Assessment** (assessment *of* learning — after the experience)
- Purpose: Certify mastery, gate progression, measure efficacy.
- In-product form: End-of-unit quizzes, mastery tests, skill assessments, level-up challenges.
- Frequency: At defined checkpoints (end of lesson, unit, module).
- Stakes: Medium — affects progression but should always allow retry.

**Diagnostic Assessment** (assessment *before* learning — at entry)
- Purpose: Determine starting point, personalize path, skip what's already known.
- In-product form: Placement tests, onboarding quizzes, adaptive diagnostics.
- Frequency: Once at start, optionally at module boundaries.
- Stakes: Zero — but results are high-impact (determine the entire learning path).

**Webb's Depth of Knowledge (DOK)** — Complements Bloom's by focusing on the complexity of thinking required:
- DOK 1: Recall and Reproduction
- DOK 2: Skills and Concepts
- DOK 3: Strategic Thinking
- DOK 4: Extended Thinking

**Critical EdTech assessment principle:** The biggest mistake in consumer EdTech is conflating engagement metrics with learning metrics. A child completing 50 lessons is not the same as a child learning 50 concepts. Design assessments that distinguish the two.

### Context

You are designing the assessment system for **$ARGUMENTS**.

### Instructions

1. **Map Assessments to Learning Objectives**

   Every assessment item must trace back to a specific learning objective (from `design-learning-objectives`). Create a coverage matrix:

   | Learning Objective | Assessment Type | DOK Level | Item Format | Frequency |
   |-------------------|----------------|-----------|-------------|-----------|
   | LO-1: [objective] | Formative | 1 | Multiple choice | Every practice |
   | LO-2: [objective] | Summative | 2 | Performance task | End of unit |

   **Red flag:** If a learning objective has no assessment item, you cannot measure it. Either add an assessment or question whether the objective belongs.

2. **Select Item Formats by Age and Modality**

   **For ages 3-6 (pre-reader):**
   - Image matching, drag-and-drop sorting, voice response, tap-the-correct-answer
   - NO text-based questions. NO timing pressure.
   - Maximum 3 options per question (cognitive load constraint)

   **For ages 6-10:**
   - Multiple choice (4 options), fill-in-the-blank, ordering/sequencing, drawing, short voice response
   - Timing can be used for fluency (not for accuracy assessment)
   - Include "show your work" options for higher DOK

   **For ages 10+:**
   - All of the above + free text response, multi-step problems, open-ended prompts
   - Can handle more complex rubrics and self-assessment

   **By modality:**
   - Voice-only (robot): Use voice Q&A, verbal recall, "tell me what you learned"
   - Touch screen: Full range of interactive item types
   - Camera: Real-world identification, show-and-tell, physical manipulation tasks

3. **Design Formative Assessment (In-Practice)**

   Formative assessment should be invisible — woven into the practice experience, not a separate "quiz":

   - **Error analysis:** Track error patterns, not just right/wrong. A child who consistently confuses "b" and "d" has a different gap than one who confuses "b" and "p".
   - **Confidence calibration:** After answering, ask "How sure are you?" (thumbs up/down for young children). Confident-and-wrong indicates a misconception. Unconfident-and-right indicates fragile knowledge.
   - **Streak tracking:** N consecutive correct answers on the same concept = likely mastery. Define what N means for your product (typically 3-5).
   - **Response time analysis:** Getting faster on the same item type suggests growing fluency (automaticity).

4. **Design Summative Assessment (Mastery Gates)**

   For each checkpoint, define:
   - **Item pool size:** Minimum items available (at least 2x what's shown to prevent memorization)
   - **Passing threshold:** What score = mastery? (Common: 80% for progression, 90% for "star" rating)
   - **Retry policy:** Immediate retry? Cooldown period? Forced review before retry?
   - **Item selection:** Random from pool? Adaptive (harder items if doing well)? Ensure coverage of all objectives.

   **Mastery gate design principles:**
   - Never make a single assessment a permanent gate. Always allow retry.
   - Show progress toward the threshold ("You need 2 more correct to pass").
   - Vary items between attempts so the learner can't memorize answers.
   - After 2 failed attempts, recommend (don't force) a review activity.

5. **Design Diagnostic Assessment (Placement)**

   If the product supports adaptive starting points:
   - **Adaptive diagnostic:** Start at expected level, adjust up/down based on responses (like a reading level test). Typically 10-15 items to place accurately.
   - **Quick diagnostic:** 5-8 items sampling across modules. Rough but fast placement.
   - **Skip logic:** If learner demonstrates mastery of Module 3 content, skip Modules 1-2 but surface them in spaced review.

6. **Define the Data Model**

   What data does each assessment interaction generate?

   ```
   assessment_event:
     learner_id: string
     objective_id: string (traces to learning objective)
     item_id: string
     item_format: string
     response: string (learner's actual answer)
     correct: boolean
     response_time_ms: integer
     confidence: enum [high, medium, low] (optional)
     attempt_number: integer
     context: enum [formative, summative, diagnostic]
     timestamp: datetime
   ```

   This data feeds into `evaluate-learning-efficacy` for measuring whether the product actually teaches.

7. **Anti-Patterns to Avoid**

   - **Testing what wasn't taught:** Assessment items must match the instruction exactly.
   - **Trick questions:** Never. Especially with children. Test knowledge, not reading comprehension of tricky wording.
   - **Ceiling effects:** If 95% of learners get 100%, the assessment is too easy to differentiate. Add harder items.
   - **Floor effects:** If 80% of learners score below passing, the instruction isn't working (or the threshold is wrong). Don't blame the learner.
   - **Assessment fatigue:** For young children, no more than 5-8 summative items in a row. Break up with encouragement or mini-activities.

### Output Format

```markdown
# Assessment Design: [Feature/Module Name]

## Assessment Coverage Matrix
| Learning Objective | Formative | Summative | Diagnostic | DOK Level |
|-------------------|-----------|-----------|------------|-----------|
| LO-1 | [item type + frequency] | [item type] | [if applicable] | [1-4] |

## Formative Assessment Design
### Error Patterns to Track
| Error Pattern | Indicates | System Response |
|--------------|-----------|----------------|
| [pattern] | [gap type] | [adaptive action] |

### Mastery Signals
| Signal | Threshold | Meaning |
|--------|-----------|---------|
| Streak | [N] correct | Likely mastery |
| Speed | < [X] ms improvement | Fluency growth |
| Confidence | High + correct | Solid knowledge |

## Summative Assessment Design
### [Checkpoint Name]
- **Items**: [count] from pool of [total]
- **Passing threshold**: [X]%
- **Item formats**: [list]
- **Retry policy**: [details]
- **Review trigger**: After [N] failures

## Diagnostic Assessment (if applicable)
- **Length**: [N] items
- **Adaptation logic**: [how items are selected]
- **Placement output**: [what gets determined]

## Data Model
[Schema for assessment events]

## Validation
- [ ] Every learning objective has at least one formative and one summative item
- [ ] Item formats are age-appropriate
- [ ] Item pools are large enough to prevent memorization
- [ ] Passing thresholds are evidence-based, not arbitrary
- [ ] Retry paths exist for all summative gates
```

Save as `assessment-design-[feature-name].md`.

### Further Reading
- Webb, N. L. (1997). "Criteria for Alignment of Expectations and Assessments." CCSSO.
- Black, P. & Wiliam, D. (1998). "Assessment and Classroom Learning." *Assessment in Education*, 5(1). (The landmark paper on formative assessment — effect size d = 0.40-0.70)
- Pellegrino, J. W. et al. (2001). *Knowing What Students Know*. National Academies Press.
- Shute, V. J. (2008). "Focus on Formative Feedback." *Review of Educational Research*, 78(1).
