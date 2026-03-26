---
name: design-habit-loops
description: "Design habit-forming mechanics that drive consistent learning practice — session triggers, routine anchoring, streak design, and re-engagement. Use when optimizing daily/weekly return rates, reducing churn, or building a 'practice habit' that parents value and children maintain."
---

## Design Habit Loops for Learning

Habit is the mechanism that turns a downloaded app into a daily practice. For EdTech, habit formation is uniquely important AND uniquely constrained — you need children to return regularly (learning requires repetition), but you must do so ethically (no dark patterns, no excessive screen time). This skill designs habit loops that parents actively want their children to have.

### Domain Context

**Hooked Model (Nir Eyal, 2014)** — the standard framework for habit-forming products:

```
Trigger → Action → Variable Reward → Investment
  ↑                                        │
  └────────────────────────────────────────┘
```

**For children's EdTech, this model needs ethical modification:**

| Component | Standard Tech | Ethical EdTech Adaptation |
|-----------|-------------|--------------------------|
| **Trigger** | Push notification, anxiety ("your streak!") | External: parent routine, scheduled time. Internal: curiosity, sense of progress |
| **Action** | Minimal friction to open app | Meaningful action: start a learning activity (not just open) |
| **Variable Reward** | Social validation, random rewards | Learning discovery, mastery surprise, new content unlocked |
| **Investment** | Store personal data, build social graph | Build knowledge, grow skill tree, develop character relationship |

**BJ Fogg's Behavior Model (2009):** Behavior = Motivation × Ability × Prompt. All three must be present simultaneously:
- **Motivation:** The child wants to learn (intrinsic) or earn rewards (extrinsic) or please parent (social)
- **Ability:** The app is accessible, the task is achievable, the session fits available time
- **Prompt:** Something triggers the child to start (notification, parent, routine, curiosity)

**Key insight for children:** Children's habits are more influenced by routines and parent behavior than by app prompts. Design for the family routine, not just the individual child.

### Context

You are designing habit loops for **$ARGUMENTS**.

### Instructions

1. **Map the Current Habit Context**

   Understand when and why children currently use (or would use) the product:

   | Time Slot | Context | Motivation | Competition for Attention |
   |-----------|---------|-----------|--------------------------|
   | Morning before school | Routine, alert | Low (rushed) | Getting dressed, breakfast |
   | After school | Free time, moderate energy | Medium | YouTube, games, outdoor play |
   | Before bed | Wind-down, tired | Mixed | Books, TV, family time |
   | Weekend morning | Relaxed, high energy | High | Cartoons, play |
   | Commute/travel | Bored, captive | High (for screen time) | Other apps, looking out window |

   **Identify the 1-2 highest-opportunity time slots** where your product can become a routine anchor.

2. **Design the Trigger System**

   **External triggers (product-initiated):**
   - **Push notifications:** MAX 1 per day, sent at the parent-configured time. Never guilt-based. Always offer value.
     - Good: "New lesson available: Space Animals! Ready to explore?" (curiosity)
     - Good: "Pika misses you! There's a new challenge waiting." (character relationship)
     - Bad: "Your streak is about to break!" (anxiety)
     - Bad: "You haven't practiced today!" (guilt)
   - **Parent-mediated triggers:** "Remind your child" button in parent dashboard. Parent is the most effective trigger for young children.
   - **Scheduled practice:** Allow parent to set a "learning time" that triggers a gentle reminder.

   **Internal triggers (learner-initiated):**
   - **Curiosity:** Leave a cliffhanger at session end ("Tomorrow: discover what happens when you mix colors!")
   - **Ownership:** "Your garden is growing — water it with a practice session" (investment → return)
   - **Competence:** "You're 2 lessons away from mastering Animals!" (proximity to goal)
   - **Routine:** After consistent use, the habit itself becomes the trigger ("It's after dinner, time for Pika")

3. **Design the Session Start Experience**

   The first 30 seconds determine whether a session happens:

   - **Instant engagement:** Skip splash screens. Go directly to a meaningful choice or activity within 3 taps.
   - **Warm welcome:** Character greeting that acknowledges their return ("You're back! Ready to learn about [topic]?")
   - **Low-friction start:** Default to "Continue where you left off" with option to choose something else.
   - **Quick win first:** Start every session with a review item the child is likely to get right (confidence boost).
   - **Daily surprise:** A small new element each day (new character outfit, new background, new fun fact) that makes each session feel fresh.

4. **Design the Streak System** (Ethically)

   Streaks are the most powerful and most abused habit mechanic. Design them carefully:

   **What counts as a streak day:**
   - Completing at least 1 meaningful learning activity (not just opening the app)
   - Minimum quality threshold (e.g., at least 3 correct answers, not just tapping through)

   **Streak visualization:**
   - Show the streak as a positive achievement, not a liability
   - "You've practiced 5 days in a row! Your brain is getting stronger!" (celebration)
   - NOT "5-day streak — don't break it!" (anxiety)

   **Streak break handling:**
   - **No punishment.** Never take away earned rewards or progress because of a missed day.
   - **Streak freeze:** 1-2 free "freeze" days per week (acknowledges that life happens). Bonus freezes earned through learning.
   - **Easy restart:** If streak breaks, show "Welcome back! Start a new streak today." No mourning animation.
   - **Streak insurance (for older children):** "Your streak paused because you were busy. Complete one lesson to resume."

   **Parent perspective:** Parents should feel that streaks encourage healthy practice, not screen addiction. Show parents the streak alongside learning outcomes ("5-day streak + 12 new words mastered").

5. **Design the Session End Experience**

   How a session ends determines whether they return:

   - **Summary:** Show what was learned (not just time spent). "Today you mastered 4 new words and reviewed 8!"
   - **Investment moment:** Something that creates return motivation:
     - Character: "Pika is proud of you! Come back tomorrow to unlock a new adventure."
     - Collection: "You're 1 star away from completing the Ocean collection!"
     - Preview: "Tomorrow's challenge: can you solve the mystery word?"
   - **Natural stopping point:** Don't end mid-activity. Finish on a complete, satisfying moment.
   - **Parent share prompt:** "Tell your parent what you learned today!" (reinforces learning through verbalization)

6. **Design Re-Engagement for Lapsed Users**

   Define behavior for users who stop returning:

   | Days Absent | Category | Action |
   |------------|----------|--------|
   | 1-2 days | Normal gap | No action (respect natural variation) |
   | 3-5 days | Mild lapse | Push notification with new content hook |
   | 7-14 days | Significant lapse | Parent notification + easy re-entry session |
   | 14-30 days | At risk | Email to parent with progress summary + "miss you" message to child |
   | 30+ days | Churned | Monthly email to parent with product updates. Don't spam the child. |

   **Re-entry session design:**
   - Start with a quick review of previously mastered content (rebuild confidence)
   - Show how much they already know ("Welcome back! You've already mastered 45 words!")
   - Make the first returning session shorter and easier than normal
   - DO NOT show how much they've "fallen behind" or how much their peers have progressed

### Output Format

```markdown
# Habit Loop Design: [Product Name]

## Target Practice Habit
- **Frequency goal**: [X sessions per week]
- **Session length**: [X minutes]
- **Optimal time slot(s)**: [when]
- **Routine anchor**: [what the practice attaches to]

## Trigger System
### External Triggers
| Trigger | Channel | Timing | Message Pattern | Frequency Cap |
|---------|---------|--------|----------------|---------------|
| [trigger] | [push/email/parent] | [when] | [pattern] | [max] |

### Internal Triggers
| Trigger | Emotion | Product Hook |
|---------|---------|-------------|
| [trigger] | [curiosity/ownership/competence] | [what in the product triggers return] |

## Session Start Design
[First 30 seconds flow]

## Streak System
- **Streak definition**: [what counts]
- **Visualization**: [how shown]
- **Break handling**: [freeze / restart / no penalty]
- **Parent communication**: [how streaks are framed to parents]

## Session End Design
- **Summary**: [what's shown]
- **Investment hook**: [what creates return motivation]
- **Parent share**: [how learning is communicated outward]

## Re-Engagement Ladder
| Days Absent | Action | Channel | Message |
|------------|--------|---------|---------|
| [days] | [action] | [channel] | [message pattern] |

## Ethical Guardrails
- [ ] No guilt-based notifications
- [ ] No loss mechanics
- [ ] Streak breaks have no punishment
- [ ] Session time limits respected
- [ ] Parent controls available for all triggers
```

Save as `habit-loops-[product-name].md`.

### Further Reading
- Eyal, N. (2014). *Hooked: How to Build Habit-Forming Products*. Portfolio/Penguin.
- Fogg, B. J. (2009). "A Behavior Model for Persuasive Design." *Proceedings of Persuasive Technology*.
- Eyal, N. (2019). *Indistractable*. Bloomsbury. (The ethical counterbalance to Hooked)
- Wood, W. (2019). *Good Habits, Bad Habits*. Farrar, Straus and Giroux.
- Duhigg, C. (2012). *The Power of Habit*. Random House.
