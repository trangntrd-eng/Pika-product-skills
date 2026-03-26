---
name: design-feedback-system
description: "Design the feedback system that responds to learner actions in real-time — immediate vs. delayed feedback, error correction, encouragement, and hints. Use when defining how your EdTech product communicates with learners about their performance during and after learning activities."
---

## Design Feedback System

Feedback is the single most powerful lever in learning. Hattie's meta-analysis (*Visible Learning*, 2008) ranks feedback as one of the top influences on achievement (d = 0.70). But feedback quality varies enormously — the wrong feedback at the wrong time can actually *harm* learning. This skill designs a feedback system that accelerates learning, not just makes learners feel good.

### Domain Context

**Hattie & Timperley's Feedback Model (2007)** identifies four levels of feedback, from most to least effective:

| Level | Focus | Example | Effectiveness |
|-------|-------|---------|---------------|
| **Task** | Whether the answer is correct | "That's correct!" / "Try again" | Low (necessary but insufficient) |
| **Process** | The strategy used | "You added the ones column first — good strategy" | High |
| **Self-regulation** | The learner's approach to learning | "You checked your work before submitting — that's a strong habit" | High |
| **Self** | The person ("You're so smart!") | "Good job!" / "You're a great student!" | **Harmful** — promotes fixed mindset |

**Critical insight for EdTech PMs:** Most consumer EdTech products only implement Level 1 (correct/incorrect) and Level 4 (generic praise). The learning science is clear: invest in Level 2 (process) and Level 3 (self-regulation) feedback. This is where product differentiation lives.

**Dweck's Growth Mindset research (2006)** directly applies:
- Praise effort and strategy, never ability → "You worked hard on that!" not "You're so smart!"
- Normalize mistakes as part of learning → "Mistakes help your brain grow!"
- Frame challenges as opportunities → "This is a tricky one — let's figure it out together"

**Feedback timing (Shute, 2008):**
- **Immediate feedback:** Best for simple, factual tasks (flashcards, vocabulary). Prevents error reinforcement.
- **Delayed feedback:** Better for complex, conceptual tasks. Gives the learner time to self-correct first. Also reduces feedback dependency.
- **Elaborated feedback:** Explains *why* something is right/wrong. More effective than simple correct/incorrect, but higher cognitive load — use for summative moments, not every practice item.

### Context

You are designing the feedback system for **$ARGUMENTS**.

### Instructions

1. **Audit Feedback Moments**

   Map every point in the learning experience where feedback occurs:

   | Moment | Current Feedback | Hattie Level | Timing | Improvement Opportunity |
   |--------|-----------------|-------------|--------|------------------------|
   | Correct answer | "Great job!" ✓ | Self (L4) | Immediate | Add process feedback |
   | Wrong answer | "Try again" ✗ | Task (L1) | Immediate | Add hint/scaffolding |
   | Streak completed | Badge animation | Self (L4) | Immediate | Add self-regulation praise |
   | Session end | Stars earned | Task (L1) | Delayed | Add learning summary |
   | Mastery gate passed | Level up | Task (L1) | Delayed | Add "what you mastered" recap |

2. **Design Feedback for Correct Responses**

   Don't just say "Correct!" — vary the feedback based on context:

   - **First correct on new concept:** Elaborate — "Yes! 3 + 4 = 7. When we add, we're putting groups together." (Process, Level 2)
   - **Correct after struggle:** Acknowledge the effort — "You got it! You tried a different approach and it worked." (Self-regulation, Level 3)
   - **Correct on review item:** Keep it light — brief positive sound/animation. Don't interrupt flow.
   - **Correct with fast response:** Build fluency awareness — "Lightning fast! You're getting really fluent with this."
   - **Streak of correct:** Milestone recognition — "5 in a row! Your practice is paying off." (Process, Level 2)

   **For children under 8:** Pair text/voice with visual feedback (animations, character reactions). The emotional tone matters as much as the words.

3. **Design Feedback for Incorrect Responses**

   This is where most EdTech products fail. Define a **graduated response system:**

   **First error:**
   - Show correct/incorrect clearly (visual + audio cue)
   - For factual items: Show the correct answer briefly, then move on
   - For procedural items: Provide a hint, let them try again
   - Tone: Neutral, encouraging. "Not quite — let's try again!"

   **Second error on same concept:**
   - Provide a scaffolded hint (process-level feedback)
   - "Remember, when we add two-digit numbers, start with the ones column"
   - Reduce complexity if possible (show a simpler version of the same problem)

   **Third error on same concept:**
   - Provide the answer with a full worked example (elaborated feedback)
   - "Let me show you: 23 + 15 → ones: 3+5=8, tens: 2+1=3, answer: 38"
   - Mark this concept for additional practice in next session
   - Tone: "This is a tough one! Let's look at it together."

   **Persistent errors across sessions:**
   - Flag for parent dashboard: "Your child is working on [concept] and could use some extra support"
   - Suggest a different learning modality (if available)
   - Reduce the frequency of this concept type temporarily to prevent frustration

   **Never:**
   - Show a red X with a buzzer sound for young children (creates anxiety)
   - Say "Wrong!" (judgmental, not informative)
   - Prevent progression entirely without offering an alternative path

4. **Design Encouragement & Motivation Feedback**

   Separate from correctness feedback — these are proactive messages that sustain engagement:

   - **Session start:** "Welcome back! You learned [X] new words last time. Ready for more?"
   - **Mid-session energy:** After 5+ minutes of focused work — "You've been working hard! Keep going or take a break?"
   - **Struggle acknowledgment:** When performance dips — "This topic is challenging for many learners. You're making progress!" (normalize difficulty)
   - **Return after absence:** "It's been [N] days! Let's warm up with a quick review." (no guilt)
   - **Milestone celebration:** At meaningful learning milestones (not arbitrary points) — "You can now [real skill]! That's a big deal."

   **Growth mindset language bank for children's products:**
   - "Mistakes help your brain grow stronger!"
   - "You haven't figured it out *yet* — but you're getting closer!"
   - "That was a tricky one. Good thing you like challenges!"
   - "Look how much you've improved since you started!"

5. **Design Parent-Facing Feedback**

   Parents are the paying customer. Their feedback needs are different:

   - **Progress summaries:** Weekly digest — time spent, concepts mastered, areas of growth
   - **Struggle alerts:** "Your child has been working on [X] and might benefit from practice together"
   - **Celebration sharing:** "Your child just mastered [skill]! Ask them to show you."
   - **Engagement nudges:** "Your child hasn't practiced in [N] days. A quick reminder might help."

   **Never tell parents their child is "behind" or "struggling."** Frame as "working on" or "building skills in."

6. **Define the Feedback Content System**

   Feedback messages can't be static — learners hear the same "Great job!" 500 times and it becomes meaningless.

   - **Message pools:** Create 10-20 variants for each feedback category. Rotate randomly.
   - **Character voice:** If the product has a character/mascot, all feedback should be in that character's voice. Define the character's personality guide.
   - **Localization notes:** Feedback is culturally sensitive. What's encouraging in one culture may feel patronizing in another. Vietnamese educational culture, for example, values persistence language differently than American.
   - **Audio/visual feedback:** Define sound design and animation for each feedback type (correctness chime, streak fanfare, milestone celebration, gentle error nudge).

### Output Format

```markdown
# Feedback System Design: [Feature Name]

## Feedback Moment Map
| Moment | Trigger | Hattie Level | Timing | Message Pattern | Visual/Audio |
|--------|---------|-------------|--------|-----------------|-------------|
| [moment] | [event] | [L1-L4] | [immediate/delayed] | [template] | [description] |

## Correct Response Feedback
| Context | Message Pattern | Example | Hattie Level |
|---------|----------------|---------|-------------|
| First correct | [pattern] | [example] | Process (L2) |
| Correct after struggle | [pattern] | [example] | Self-reg (L3) |
| Fast correct | [pattern] | [example] | Process (L2) |

## Error Response System
| Error Stage | System Response | Tone | Example |
|------------|----------------|------|---------|
| 1st error | [response] | Neutral, encouraging | [example] |
| 2nd error | [scaffolded hint] | Supportive | [example] |
| 3rd error | [worked example] | Patient, collaborative | [example] |
| Persistent | [flag + reroute] | Empathetic | [example] |

## Motivation & Encouragement
| Trigger | Message Pattern | Growth Mindset Framing |
|---------|----------------|----------------------|
| [trigger] | [pattern] | [mindset language] |

## Parent-Facing Feedback
| Type | Frequency | Content | Tone |
|------|-----------|---------|------|
| Progress summary | Weekly | [elements] | Celebratory |
| Struggle alert | As needed | [elements] | Supportive, actionable |

## Message Pools
[Sample messages for each category — minimum 10 variants per category]

## Localization Notes
[Cultural considerations for feedback tone and content]
```

Save as `feedback-system-[feature-name].md`.

### Further Reading
- Hattie, J. & Timperley, H. (2007). "The Power of Feedback." *Review of Educational Research*, 77(1). (The definitive paper on feedback in learning)
- Shute, V. J. (2008). "Focus on Formative Feedback." *Review of Educational Research*, 78(1).
- Dweck, C. S. (2006). *Mindset: The New Psychology of Success*. Random House.
- Kluger, A. N. & DeNisi, A. (1996). "The Effects of Feedback Interventions on Performance." *Psychological Bulletin*, 119(2). (Meta-analysis: 1/3 of feedback interventions actually decrease performance — design matters)
