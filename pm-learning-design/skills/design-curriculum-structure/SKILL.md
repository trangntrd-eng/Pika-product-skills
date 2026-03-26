---
name: design-curriculum-structure
description: "Design the scope, sequence, and structural hierarchy of a learning curriculum. Use when you need to organize learning content into modules, units, and lessons — defining what gets taught, in what order, and how topics connect across the full learning journey."
---

## Design Curriculum Structure

Curriculum structure is the architecture of a learning product. Just as a poorly structured product creates user confusion, a poorly structured curriculum creates cognitive overload and learning gaps. This skill produces the scope & sequence document that becomes the blueprint for content production, learning path logic, and progress tracking.

### Domain Context

This skill draws from three foundational curriculum design models:

**1. Spiral Curriculum (Jerome Bruner, 1960)**
Core concepts are revisited at increasing levels of complexity. A child learns "addition" first with objects, then with numbers, then with fractions, then with algebra. The same concept spirals upward. This is the dominant model for K-12 EdTech because it maps naturally to spaced repetition and mastery-based progression.

**2. Competency-Based Structure (Bloom's Mastery Learning, 1968)**
Learners progress only when they demonstrate mastery at each level. Time is the variable, not achievement. This model is ideal for self-paced EdTech products because it respects individual learning speeds.

**3. Modular/Microlearning Structure**
Content is organized into self-contained units (5-15 minutes) that can be completed in a single session. Critical for mobile-first B2C EdTech where session times are short and interruptible.

**Which model to choose:**
- **Spiral** when building long-term skill development (language learning, math progression)
- **Competency-based** when learners have varied starting points (adaptive products)
- **Modular** when engagement and flexibility matter more than deep sequencing (casual learning, supplementary products)
- **Hybrid** (most common in practice) — spiral for macro-structure, competency-based for gating, modular for session design

### Context

You are a curriculum architect designing the learning structure for **$ARGUMENTS**.

### Instructions

1. **Define the Curriculum Scope**

   Determine the boundaries of what this curriculum covers:
   - **Subject domain** — What knowledge area? (e.g., "English vocabulary for Vietnamese children ages 6-10")
   - **Breadth** — How many topics/skills are in scope? List them exhaustively.
   - **Depth** — To what level of mastery for each topic? (Recognition → Recall → Application → Transfer)
   - **Time horizon** — How much total learning time does the full curriculum represent? (e.g., "200 hours across 12 months")
   - **Standards alignment** (if applicable) — Which educational standards does this map to? (Vietnam MOE, Common Core, CEFR, etc.)

2. **Design the Structural Hierarchy**

   Organize content into a clear hierarchy. For most EdTech products:

   ```
   Course (full learning journey)
   └── Module (major topic area, ~2-4 weeks)
       └── Unit (focused sub-topic, ~1 week)
           └── Lesson (single session, 5-20 min)
               └── Activity (single interaction, 1-5 min)
   ```

   For each level, define:
   - **Naming convention** — How are items named/numbered?
   - **Typical duration** — How long does one instance take?
   - **Completion criteria** — What counts as "done"?
   - **Relationship to UI** — How does this map to screens/flows in the product?

3. **Create the Scope & Sequence Matrix**

   Build a matrix showing what gets taught and when:

   | Module | Unit | Key Concepts | Bloom's Target | Prerequisites | Est. Duration |
   |--------|------|-------------|----------------|---------------|---------------|
   | M1: Foundations | U1.1: ... | concept A, B | Remember | None | 3 lessons |
   | ... | U1.2: ... | concept C | Understand | U1.1 | 4 lessons |

   **Sequencing principles:**
   - **Prerequisite logic** — Topic B requires Topic A. Make dependencies explicit.
   - **Interleaving** — Mix related topics to strengthen discrimination (Rohrer & Taylor, 2007). Don't teach all of Topic A, then all of Topic B. Alternate.
   - **Spacing** — Revisit previously learned concepts at increasing intervals (Ebbinghaus spacing effect). Build review touchpoints into the sequence.
   - **Difficulty progression** — Within each module, follow an easy→medium→hard arc. Across modules, gradually increase cognitive load.

4. **Define Spiral Touchpoints** (if using spiral model)

   For each core concept, map where it appears across the curriculum at increasing complexity:

   ```
   Concept: "Addition"
   ├── M1: Adding objects (concrete, Remember)
   ├── M3: Adding single digits (symbolic, Apply)
   ├── M5: Adding double digits with carrying (procedural, Apply)
   ├── M8: Word problems with addition (transfer, Analyze)
   └── M12: Mental math strategies (fluency, Create)
   ```

5. **Design the Mastery Gates**

   Define where learners must demonstrate mastery before progressing:
   - **Hard gates** — Cannot proceed without passing (use sparingly, for true prerequisites)
   - **Soft gates** — Recommendation to review, but learner can proceed (for spiral revisits)
   - **Assessment type** at each gate — quiz, performance task, streak requirement
   - **Remediation path** — What happens when a learner fails a gate? (Reteach? Alternative explanation? Simpler practice?)

6. **Map Content Requirements**

   For each unit, specify what content assets are needed:
   - Number and type of lessons
   - Number of practice items/exercises per concept
   - Media requirements (images, audio, video, 3D, AR)
   - Estimated production effort per unit
   - Localization considerations

   This becomes the content production backlog.

7. **Validate the Structure**

   Check against these common curriculum design failures:
   - **Coverage gaps** — Are there concepts learners need that aren't in scope?
   - **Prerequisite violations** — Does any unit assume knowledge not yet taught?
   - **Pacing problems** — Are any modules significantly longer/harder than others?
   - **Engagement valleys** — Are there long stretches without variety or novelty?
   - **Assessment alignment** — Does every learning objective have a corresponding assessment?

### Output Format

```markdown
# Curriculum Structure: [Product/Feature Name]

## Scope Definition
- **Subject**: [domain]
- **Target learner**: [age, level]
- **Total duration**: [hours/months]
- **Standards alignment**: [if applicable]
- **Curriculum model**: [spiral / competency-based / modular / hybrid]

## Structural Hierarchy
| Level | Name | Typical Duration | Completion Criteria | UI Mapping |
|-------|------|-----------------|--------------------:|------------|
| Course | ... | ... | ... | ... |
| Module | ... | ... | ... | ... |
| Unit | ... | ... | ... | ... |
| Lesson | ... | ... | ... | ... |

## Scope & Sequence

### Module 1: [Name]
**Duration**: [X weeks] | **Bloom's ceiling**: [level] | **Prerequisites**: [none/list]

| Unit | Key Concepts | Objectives (from learning-objectives) | Lessons | Gate Type |
|------|-------------|---------------------------------------|---------|-----------|
| 1.1 | ... | LO-1, LO-2 | 3 | Soft |
| 1.2 | ... | LO-3 | 4 | Hard |

[Repeat for each module]

## Spiral Map (if applicable)
[Concept → appearance at each level across modules]

## Content Production Requirements
| Module | Lessons | Practice Items | Media Assets | Est. Effort |
|--------|---------|---------------|-------------|-------------|
| M1 | ... | ... | ... | ... |

## Validation Checklist
- [ ] All learning objectives covered
- [ ] No prerequisite violations
- [ ] Pacing balanced across modules
- [ ] Review/spacing touchpoints every 3-5 units
- [ ] Assessment at every gate point
```

Save as `curriculum-structure-[product-name].md`.

### Further Reading
- Bruner, J. (1960). *The Process of Education*. Harvard University Press.
- Wiggins, G. & McTighe, J. (2005). *Understanding by Design*. ASCD.
- Bloom, B. S. (1968). "Learning for Mastery." *Evaluation Comment*, 1(2).
- Rohrer, D. & Taylor, K. (2007). "The shuffling of mathematics problems improves learning." *Instructional Science*, 35(6).
- Clark, R. C. (2008). *Building Expertise*. Wiley.
