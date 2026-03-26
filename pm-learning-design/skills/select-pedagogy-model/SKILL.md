---
name: select-pedagogy-model
description: "Select and configure the right pedagogical model for an EdTech feature based on learning goals, target age, and product constraints. Use when deciding between spaced repetition, mastery learning, scaffolding, inquiry-based learning, or other approaches — before building the learning mechanics."
---

## Select Pedagogy Model

The pedagogy model is the engine inside your EdTech feature. It determines how learners interact with content, how the system responds to learner behavior, and ultimately whether learning actually happens. Choosing the wrong model wastes engineering effort and produces features that feel educational but aren't.

### Domain Context

**The core models relevant to consumer EdTech:**

**1. Spaced Repetition (Ebbinghaus, 1885; Leitner, 1972; Pimsleur, 1967)**
- **How it works:** Items are reviewed at exponentially increasing intervals. Items answered incorrectly are reviewed sooner.
- **Best for:** Memorization — vocabulary, facts, definitions, formulas.
- **Algorithm:** SM-2 (SuperMemo), FSRS (Free Spaced Repetition Scheduler), or Leitner boxes.
- **Product examples:** Anki, Duolingo (vocabulary component), Quizlet.
- **Limitation:** Only works for declarative knowledge (facts). Cannot teach procedural skills, problem-solving, or creative thinking.

**2. Mastery Learning (Bloom, 1968; Khan Academy model)**
- **How it works:** Learner must demonstrate mastery (typically 80-90% accuracy) before advancing. Time is flexible; achievement is fixed.
- **Best for:** Skill progression with clear prerequisites — math, programming, language grammar.
- **Key mechanic:** Diagnostic → Practice → Assessment → Gate (pass/remediate).
- **Product examples:** Khan Academy, IXL, Duolingo (skill tree).
- **Limitation:** Requires well-defined mastery criteria and enough practice content at each level.

**3. Scaffolding (Vygotsky's Zone of Proximal Development, 1978; Wood, Bruner & Ross, 1976)**
- **How it works:** System provides support (hints, partial solutions, worked examples) that is gradually removed as the learner gains competence. The "zone" is the sweet spot between what a learner can do alone and what they can do with help.
- **Best for:** Complex skill building, problem solving, creative tasks.
- **Key mechanic:** Full support → Partial support → Independent performance.
- **Product examples:** Photomath (step-by-step), Codecademy (guided projects), writing assistants.
- **Limitation:** Hard to implement adaptively at scale. Requires modeling individual learner competence.

**4. Inquiry-Based / Discovery Learning (Bruner, 1961; Papert, 1980)**
- **How it works:** Learner explores, experiments, and constructs understanding through guided discovery rather than direct instruction.
- **Best for:** Science, creative subjects, computational thinking. Ages 7+ (concrete operational stage).
- **Key mechanic:** Question → Hypothesis → Experiment → Reflection.
- **Product examples:** Scratch, Tynker, science simulation apps.
- **Limitation:** Higher cognitive load. Younger children need more structure. Without careful guidance, discovery learning can produce misconceptions.

**5. Game-Based Learning (Gee, 2003; Prensky, 2001)**
- **How it works:** Learning is embedded in game mechanics. Progression, challenge, feedback, and narrative drive engagement while learning happens implicitly.
- **Best for:** Engagement-critical contexts (young children, reluctant learners), practicing skills through repetition.
- **Key mechanic:** Challenge → Attempt → Feedback → Reward → Increased difficulty.
- **Product examples:** DragonBox (algebra), Prodigy (math), Pika Robot.
- **Limitation:** Risk of "chocolate-covered broccoli" — game mechanics that don't actually integrate with learning. The game should *require* the knowledge, not just reward it.

**6. Social/Collaborative Learning (Vygotsky; Topping, 1996)**
- **How it works:** Learners learn from and with peers — through discussion, peer teaching, collaborative problem-solving.
- **Best for:** Language practice, debate/critical thinking, project-based work. Ages 8+.
- **Limitation:** Requires active user base. Moderation challenges with children. Hard to ensure learning quality.

### Context

You are selecting the optimal pedagogy model for **$ARGUMENTS**.

### Instructions

1. **Profile the Learning Task**

   Answer these diagnostic questions:
   - **Knowledge type:** Declarative (facts, vocabulary) → favors spaced repetition. Procedural (skills, steps) → favors mastery learning. Conceptual (understanding, transfer) → favors scaffolding/inquiry.
   - **Bloom's target level:** Remember/Understand → spaced repetition or mastery. Apply/Analyze → mastery or scaffolding. Evaluate/Create → inquiry or project-based.
   - **Skill vs. knowledge:** Is this about knowing or doing?
   - **Transfer requirement:** Must the learner apply this in novel contexts? If yes, avoid pure memorization models.

2. **Profile the Learner Context**

   - **Age/developmental stage:** Under 7 → needs concrete, game-based, heavily scaffolded. 7-11 → can handle mastery gates, light inquiry. 12+ → can handle all models.
   - **Attention span:** Younger = shorter sessions = favor modular, quick-feedback models.
   - **Motivation:** Intrinsically motivated learners tolerate more challenge (mastery, inquiry). Extrinsically motivated need more engagement hooks (game-based, social).
   - **Solo vs. social:** Is the learner alone or with peers/parents?

3. **Profile the Product Constraints**

   - **Content volume:** Spaced repetition needs large item pools. Mastery learning needs graded difficulty sets. Inquiry needs rich environments.
   - **Interaction modality:** Voice-only (robot) limits visual scaffolding. Touch screen enables drag-and-drop mastery activities. Camera enables real-world inquiry.
   - **Engineering complexity:** Spaced repetition (low — well-known algorithms). Mastery gates (medium — need diagnostic logic). Adaptive scaffolding (high — need learner modeling). Full inquiry (very high — need open-ended interaction).
   - **Session length:** <5 min → spaced repetition or micro-mastery. 5-15 min → mastery or game-based. 15+ min → scaffolding or inquiry.

4. **Select Primary + Supporting Models**

   Most effective EdTech features use a **primary model** for the core loop and **supporting models** for specific components:

   Example combinations:
   - **Mastery (primary) + Spaced repetition (review):** Main progression is mastery-gated. Previously mastered items enter a spaced review queue.
   - **Game-based (primary) + Scaffolding (support):** Game provides engagement and practice. Scaffolding activates when the learner struggles.
   - **Inquiry (primary) + Mastery (assessment):** Discovery-based exploration with mastery checkpoints to verify understanding.

5. **Design the Core Learning Loop**

   For the selected model, define the micro-loop (single session) and macro-loop (across sessions):

   **Micro-loop** (within one session):
   ```
   [Trigger] → [Present challenge] → [Learner responds] → [Feedback] → [Adjust difficulty] → [Next challenge or session end]
   ```

   **Macro-loop** (across sessions):
   ```
   [Session start] → [Review previous] → [New content/challenge] → [Practice] → [Assessment] → [Progress update] → [Session end with hook for return]
   ```

6. **Define Adaptive Behavior**

   How does the system respond to learner performance?
   - **When learner excels:** Skip ahead? Increase difficulty? Offer bonus challenges?
   - **When learner struggles:** Provide hints? Reduce difficulty? Switch modality? Suggest review?
   - **When learner is disengaged:** Shorten session? Switch activity type? Introduce novelty?

   Define thresholds for each adaptation (e.g., "3 consecutive errors → activate scaffolding hint").

### Output Format

```markdown
# Pedagogy Model Selection: [Feature Name]

## Learning Task Profile
- **Knowledge type**: [declarative / procedural / conceptual]
- **Bloom's target**: [level]
- **Transfer requirement**: [low / medium / high]

## Learner Profile
- **Age range**: [X-Y]
- **Developmental stage**: [Piaget stage]
- **Motivation context**: [intrinsic / extrinsic / mixed]
- **Session context**: [solo mobile / with parent / classroom]

## Product Constraints
- **Session length**: [X min]
- **Interaction modality**: [touch / voice / camera / hybrid]
- **Content volume available**: [large / medium / limited]
- **Engineering budget**: [high / medium / constrained]

## Model Selection

| Role | Model | Rationale |
|------|-------|-----------|
| Primary | [model] | [why this fits the task + learner + constraints] |
| Supporting | [model] | [what component it serves] |
| Review | [model] | [how previously learned content is maintained] |

### Why Not [Alternative Model]
[Brief explanation of why other models were considered and rejected]

## Core Learning Loop

### Micro-Loop (Single Session)
[Step-by-step flow diagram]

### Macro-Loop (Across Sessions)
[Step-by-step flow diagram]

## Adaptive Behavior Rules
| Trigger | Condition | System Response |
|---------|-----------|----------------|
| Excelling | [e.g., 5 correct in a row] | [response] |
| Struggling | [e.g., 3 errors on same concept] | [response] |
| Disengaged | [e.g., session < 2 min for 3 days] | [response] |

## Implementation Requirements
- **Algorithm/logic needed**: [e.g., FSRS scheduler, mastery threshold calculator]
- **Data to collect**: [learner events needed for adaptation]
- **Content requirements**: [what content is needed to support the model]
```

Save as `pedagogy-model-[feature-name].md`.

### Further Reading
- Bloom, B. S. (1968). "Learning for Mastery." *Evaluation Comment*, 1(2).
- Vygotsky, L. S. (1978). *Mind in Society*. Harvard University Press.
- Gee, J. P. (2003). *What Video Games Have to Teach Us About Learning and Literacy*. Palgrave.
- Clark, R. C. & Mayer, R. E. (2016). *e-Learning and the Science of Instruction* (4th ed.). Wiley.
- Pashler, H. et al. (2007). "Organizing Instruction and Study to Improve Student Learning." IES Practice Guide, NCER 2007-2004.
- Papert, S. (1980). *Mindstorms: Children, Computers, and Powerful Ideas*. Basic Books.
