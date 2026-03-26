---
name: design-progression-mechanics
description: "Design the progression system — skill trees, mastery levels, unlock mechanics, and difficulty curves. Use when defining how learners advance through your product, how difficulty scales, and how progress feels visible and motivating."
---

## Design Progression Mechanics

Progression is the spine of an EdTech product. It answers the learner's fundamental question: "Am I getting better?" A well-designed progression system makes growth visible, calibrates difficulty to maintain flow, and gives learners agency over their path. A poorly designed one either bores (too easy), frustrates (too hard), or confuses (unclear what to do next).

### Domain Context

**Flow Theory (Csikszentmihalyi, 1990)** provides the foundation. The "flow channel" is the narrow band between boredom (challenge too low for skill) and anxiety (challenge too high for skill). Progression design is the art of keeping the learner in this channel as their skill increases.

**Difficulty curve models:**

| Model | Shape | Best For | Risk |
|-------|-------|----------|------|
| **Linear** | Steady increase | Structured curricula, math | Monotonous feel, no variation |
| **Sawtooth** | Rise → dip → higher rise | Most EdTech | Requires careful tuning |
| **Stepped** | Plateau → jump → plateau | Mastery-gated products | Frustration at jumps if too steep |
| **Logarithmic** | Fast early, slow later | Casual/supplementary apps | Late-stage content feels like grind |

**Recommended for children's EdTech: Sawtooth.** New concepts introduce difficulty, followed by practice that feels easier, followed by the next concept. This creates a rhythm of challenge and confidence that sustains motivation.

**Skill tree models from game design:**
- **Linear chain** — A → B → C → D (simplest, most constrained)
- **Branching tree** — A → (B or C) → D (choice, but converges)
- **Open network** — Multiple paths, few hard prerequisites (maximum autonomy)
- **Hub and spoke** — Core skill with optional extensions (good for topic-based learning)

### Context

You are designing the progression mechanics for **$ARGUMENTS**.

### Instructions

1. **Define the Progression Axes**

   Most EdTech products have multiple concurrent progressions:

   | Axis | What Progresses | Metric | Visibility |
   |------|----------------|--------|-----------|
   | **Content mastery** | Topics/skills learned | Mastery % per unit | Skill tree / map |
   | **Difficulty level** | Problem complexity | Bloom's level / DOK | Difficulty indicator |
   | **Fluency** | Speed and accuracy | Response time trends | Speed badges |
   | **Breadth** | Topics explored | # of topics touched | Exploration meter |
   | **Consistency** | Practice habit | Streak / sessions per week | Streak counter |
   | **Meta-level** | Overall growth | Composite score / level | Profile level |

   **Decide which axes are primary** (shown prominently, drive progression) and which are secondary (tracked, shown subtly).

2. **Design the Difficulty Curve**

   For the primary content progression, map the difficulty curve:

   ```
   Difficulty
   │    ╭─╮   ╭──╮    ╭───╮
   │   ╭╯ ╰─╮╭╯  ╰──╮╭╯   ╰─╮   ← Sawtooth: new concept → practice → new concept
   │  ╭╯    ╰╯      ╰╯      ╰╮
   │ ╭╯                       ╰
   │╭╯
   └──────────────────────────── Time/Sessions
   ```

   For each module, specify:
   - **Introduction difficulty:** How challenging is the first encounter with a new concept? (Should be low — scaffolded introduction)
   - **Practice difficulty:** How quickly does it ramp during practice? (Gradual — 3-5 items at each difficulty tier)
   - **Mastery difficulty:** How hard is the mastery gate? (Moderate — achievable with honest practice)
   - **Review difficulty:** When a mastered concept reappears, at what level? (Match the mastery level, not reset to easy)

3. **Design the Skill Tree / Progress Map**

   Choose a visual model and populate it:

   **For linear subjects (math, language grammar):**
   ```
   Module 1: Foundations
   ├── 1.1 Letters A-E ✅
   ├── 1.2 Letters F-J ✅
   ├── 1.3 Letters K-O 🔓 ← Current
   └── 1.4 Letters P-T 🔒

   Module 2: Words (locked until Module 1 complete)
   ├── 2.1 3-letter words 🔒
   ...
   ```

   **For non-linear subjects (vocabulary, facts, topics):**
   ```
   ┌─────────┐     ┌─────────┐
   │ Animals ├──┬──┤  Food   │
   │  ✅ 80% │  │  │ 🔓 20% │
   └─────────┘  │  └─────────┘
                │
   ┌─────────┐  │  ┌─────────┐
   │ Colors  ├──┴──┤ Numbers │
   │  ✅ 100%│     │ 🔓 60% │
   └─────────┘     └─────────┘
   ```

   Design rules:
   - **Unlock logic:** What must be completed to unlock the next node? (Mastery gate? Time? Parent approval?)
   - **Visible horizon:** How many locked nodes ahead can the learner see? (2-3 is ideal — enough to create anticipation without overwhelm)
   - **Dead ends:** Never design paths that lead to a dead end. Every node should connect forward.

4. **Design the Mastery Representation**

   How does mastery look and feel per node?

   | State | Visual | Meaning |
   |-------|--------|---------|
   | Locked | Gray/dark, lock icon | Prerequisites not met |
   | Available | Colored, glowing | Ready to start |
   | In Progress | Partially filled | Started, not mastered |
   | Mastered | Fully filled, star/checkmark | Mastery gate passed |
   | Reviewed | Gold/special | Mastered + retained in review |
   | Decayed | Faded mastered state | Was mastered, failed recent review |

   **Decayed state (controversial):** Showing decay can motivate review but also discourage. For children under 10, prefer "Your [topic] knowledge wants attention!" over showing de-leveling. For 10+, showing gentle decay can teach that skills require maintenance.

5. **Design the Unlock & Reward Moments**

   Every progression milestone needs a reward moment:

   | Milestone | Reward | Emotional Target |
   |-----------|--------|-----------------|
   | Complete first lesson | XP + encouragement animation | "I can do this!" |
   | First mastery gate passed | Badge + level up | "I'm getting better!" |
   | Complete a module | Major celebration + collectible | "I achieved something real!" |
   | Return after absence | Review success + welcome back | "I still know this!" |
   | Attempt hard content (even if fail) | Effort recognition | "Trying hard things is good!" |

6. **Design Pacing Controls**

   Prevent both too-fast and too-slow progression:

   - **Speed limit (optional):** Maximum new content per day (prevents burnout and bingeing). E.g., max 3 new lessons/day. Offer review activities beyond the limit.
   - **Minimum pace guidance:** If a learner hasn't progressed in 7+ days, surface encouragement or suggest a different topic.
   - **Parent pacing controls:** Let parents set minimum/maximum daily goals.
   - **Smart pacing:** If the learner is breezing through (>90% correct, fast response times), skip ahead or offer enrichment. If struggling, slow down and add scaffolding.

### Output Format

```markdown
# Progression Mechanics: [Product Name]

## Progression Axes
| Axis | Primary/Secondary | Metric | Visualization |
|------|------------------|--------|---------------|
| [axis] | [primary/secondary] | [metric] | [how shown] |

## Difficulty Curve
**Model**: [sawtooth / linear / stepped]
[Curve diagram with module markers]

| Module | Intro Difficulty | Practice Ramp | Mastery Gate | Review Level |
|--------|-----------------|--------------|-------------|-------------|
| [module] | [low/med/high] | [gradual/moderate/steep] | [threshold] | [level] |

## Skill Tree / Progress Map
**Model**: [linear / branching / network / hub-spoke]
[Visual diagram]

### Unlock Rules
| Node | Prerequisites | Unlock Trigger |
|------|--------------|----------------|
| [node] | [what must be done] | [specific condition] |

## Mastery States
| State | Visual | Trigger | Transition Rules |
|-------|--------|---------|-----------------|
| [state] | [appearance] | [when entered] | [when left] |

## Reward Moments
[Table from Step 5]

## Pacing Controls
| Control | Default | Parent Configurable? |
|---------|---------|---------------------|
| [control] | [value] | [yes/no] |
```

Save as `progression-mechanics-[product-name].md`.

### Further Reading
- Csikszentmihalyi, M. (1990). *Flow: The Psychology of Optimal Experience*. Harper & Row.
- Schell, J. (2019). *The Art of Game Design: A Book of Lenses* (3rd ed.). CRC Press. (Ch. 14: "The Lens of the Flow Channel")
- Koster, R. (2013). *A Theory of Fun for Game Design* (2nd ed.). O'Reilly.
- Rigby, S. & Ryan, R. M. (2011). *Glued to Games*. Praeger. (SDT applied to game design)
