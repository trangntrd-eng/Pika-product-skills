---
description: Design learning experiences — from objectives through curriculum, pedagogy, assessment, and efficacy measurement
argument-hint: "<feature or learning module to design>"
---

# /learning-design -- Learning Experience Design Workflow

Design a complete, pedagogically-sound learning experience for an EdTech feature or module. This command chains the learning design skills in the right order — starting from learning outcomes and working backward to the experience (Backward Design).

## Invocation

```
/learning-design Pika Photo-to-Lesson English vocabulary feature
/learning-design Math foundations module for ages 6-8
/learning-design Ôn Bài review system for Vietnamese students
```

## Workflow

### Step 1: Understand the Learning Context

Ask the user:
1. **What should the learner be able to do after this experience?** (The desired outcome, in plain language)
2. **Who is the target learner?** (Age, prior knowledge, motivation, learning environment)
3. **What product constraints exist?** (Modality, session length, content available, engineering budget)

If the user has existing product context (PRD, personas, user research), review it first. Check for prior artifacts in the project context directory.

### Step 2: Design Learning Objectives

Apply the `design-learning-objectives` skill.

- Define 3-7 ABCD learning objectives
- Map to Bloom's Taxonomy levels
- Validate against product constraints
- Output: `learning-objectives-[feature].md`

**Checkpoint:** Review objectives with the user. Confirm the Bloom's distribution matches their ambition. Ask: "Are these the right outcomes? Should we aim higher or more foundational?"

### Step 3: Select Pedagogy Model

Apply the `select-pedagogy-model` skill.

- Profile the learning task, learner, and constraints
- Select primary + supporting models
- Design core learning loop (micro and macro)
- Define adaptive behavior rules
- Output: `pedagogy-model-[feature].md`

**Checkpoint:** Present the model selection with rationale. Ask: "Does this approach match how you want learners to experience the feature?"

### Step 4: Design Curriculum Structure

Apply the `design-curriculum-structure` skill.

- Define structural hierarchy (course → module → unit → lesson)
- Build scope & sequence matrix
- Map spiral touchpoints and mastery gates
- Estimate content production requirements
- Output: `curriculum-structure-[feature].md`

**Checkpoint:** Review the scope. Ask: "Is this the right amount of content for your timeline and resources?"

### Step 5: Design Assessment System

Apply the `design-assessment` skill.

- Map assessments to every learning objective
- Design formative (in-practice), summative (gates), and diagnostic (placement) assessments
- Select age-appropriate item formats
- Define the assessment data model
- Output: `assessment-design-[feature].md`

### Step 6: Design Feedback System

Apply the `design-feedback-system` skill.

- Map all feedback moments
- Design graduated error response
- Create growth-mindset encouragement language
- Plan parent-facing feedback
- Output: `feedback-system-[feature].md`

### Step 7: Design Learning Path

Apply the `design-learning-path` skill.

- Define entry points and progression model
- Set adaptation rules and thresholds
- Design review/maintenance system
- Plan progress visualization
- Handle edge cases
- Output: `learning-path-[feature].md`

### Step 8: Synthesize into Learning Design Brief

Combine all artifacts into a single **Learning Design Brief** that can be handed to engineering and content teams:

```markdown
# Learning Design Brief: [Feature Name]

## Executive Summary
[2-3 sentences: what this feature teaches, to whom, using what approach]

## Learning Objectives (from Step 2)
[Summary table of objectives with Bloom's levels]

## Pedagogy Model (from Step 3)
[Selected model + core learning loop diagram]

## Curriculum Overview (from Step 4)
[Scope & sequence summary — modules, units, estimated duration]

## Assessment Strategy (from Step 5)
[Key assessment types, mastery thresholds, data collected]

## Feedback Design (from Step 6)
[Feedback philosophy + key patterns]

## Learning Path (from Step 7)
[Progression model + adaptation rules summary]

## Content Production Requirements
[What content needs to be created, estimated effort]

## Efficacy Measurement Plan
[How we'll know if this works — key metrics and targets]

## Open Questions
[Unresolved decisions that need input from engineering, content, or leadership]
```

Save as `learning-design-brief-[feature].md`.

### Step 9: Offer Next Steps

Suggest:
- **"Want me to create the PRD?"** → Feed the learning design brief into `/write-prd` as context
- **"Want me to design the gamification layer?"** → Route to `/engagement-design`
- **"Want me to plan the efficacy measurement?"** → Apply `evaluate-learning-efficacy` in depth
- **"Want me to check child safety compliance?"** → Route to `/child-safety`

## Notes

- This workflow produces 6 artifacts + 1 synthesis document. It's a deep exercise (1-2 hours of collaborative work). For lighter-weight learning design, run individual skills directly.
- The Learning Design Brief is designed to complement, not replace, the PRD. The PRD covers product requirements; the Brief covers pedagogical requirements. Together they give engineering the full picture.
- Always validate with domain experts (teachers, instructional designers, child development specialists) if available. AI-generated learning design is a strong starting point, not a final answer.
