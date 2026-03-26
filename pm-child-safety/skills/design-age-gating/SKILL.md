---
name: design-age-gating
description: "Design age-appropriate feature gating — determining which features, content, and interactions are available to which age groups. Use when building a product used by children of different ages, or a product used by both children and adults, where some features must be restricted by age."
---

## Design Age Gating

Age gating goes beyond the compliance checkbox. It's about designing a product that adapts its capabilities to the developmental stage of the user. A 6-year-old and a 12-year-old have fundamentally different cognitive abilities, safety needs, and engagement patterns. Treating them identically fails both.

### Domain Context

**Developmental stage framework (Piaget, adapted for digital products):**

| Stage | Age | Capabilities | Product Implications |
|-------|-----|-------------|---------------------|
| Preoperational | 2-7 | Symbolic play, limited logic, egocentric, preliterate (early), short attention | No text UI, no social features, no in-app purchases, adult co-use required, sessions <10min |
| Concrete Operational | 7-11 | Logical thought about concrete things, reading, basic math, understanding of rules | Can navigate menus, follow multi-step instructions, limited social (moderated), sessions 10-20min |
| Formal Operational | 11+ | Abstract thought, hypothetical reasoning, self-regulation improving | Can handle open-ended tasks, peer interaction (with moderation), longer sessions, some self-management |

**Age gating operates on two dimensions:**
1. **Safety gating** — Blocking features that pose safety/privacy risks for younger users (social features, data-collecting features, external links)
2. **Developmental gating** — Adapting feature complexity and content to match cognitive ability (difficulty, UI complexity, session length)

### Context

You are designing the age-gating system for **$ARGUMENTS**.

### Instructions

1. **Define Age Bands**

   Based on your product's target range, define 2-4 distinct age bands:

   Example for a 4-12 product:
   | Band | Age | Label (internal) | Piaget Stage | Parental Involvement |
   |------|-----|-----------------|-------------|---------------------|
   | A | 4-6 | Early Learner | Preoperational | High (co-use required) |
   | B | 7-9 | Independent Learner | Early Concrete | Medium (supervised) |
   | C | 10-12 | Advanced Learner | Late Concrete | Low (autonomous, parent dashboard) |

2. **Map Features to Age Bands**

   For every product feature, determine access by age band:

   | Feature | Band A (4-6) | Band B (7-9) | Band C (10-12) | Rationale |
   |---------|-------------|-------------|----------------|-----------|
   | Core learning content | ✅ (simplified) | ✅ (standard) | ✅ (advanced) | Developmental |
   | Voice interaction | ✅ | ✅ | ✅ | Core modality |
   | Text-based chat | ❌ | ⚠️ (pre-written responses only) | ✅ (moderated) | Literacy + safety |
   | Photo capture | ❌ | ✅ (on-device only) | ✅ | Privacy risk |
   | Social/peer features | ❌ | ❌ | ⚠️ (heavily moderated) | Safety risk |
   | Progress sharing | Parent only | Parent + child | Child + parent | Developmental |
   | Settings/preferences | Parent only | Parent + limited child | Both | Cognitive capacity |
   | External links | ❌ | ❌ | ❌ (COPPA/Kids policy) | Compliance |
   | In-app purchases | ❌ | ❌ | ❌ (parent only) | Legal/app store |
   | Notifications | Parent only | Parent + child (limited) | Both | Distraction + safety |

3. **Design Age Determination Logic**

   How does the product know the user's age?
   - **Parent-provided at registration:** Most reliable. Parent enters child's birth date during consent flow.
   - **Self-reported:** Unreliable for children. Use only as supplementary signal.
   - **Inferred from behavior:** Risky as sole method, but useful for anomaly detection (e.g., child using a "parent" account).

   **Implementation:**
   - Store birth date (not just age — it changes), derive current age at runtime
   - Auto-transition between bands on birthday (with grace period and parent notification)
   - Allow parent to override band upward or downward ("my 6-year-old reads at age 9 level")
   - Never let the child change their own age band

4. **Design the Transition Experience**

   When a child ages into a new band:
   - **Unlock new features gradually** — don't overwhelm. "You're now old enough to try [feature]!"
   - **Notify parent first** — "Your child has reached a new stage. Here are the new features being unlocked. You can adjust these in settings."
   - **Parent override** — Allow parent to keep restrictions from the previous band
   - **Celebrate** — Aging up should feel like an achievement, not a bureaucratic event

5. **Design UI Adaptations by Age Band**

   | UI Element | Band A (4-6) | Band B (7-9) | Band C (10-12) |
   |-----------|-------------|-------------|----------------|
   | Navigation | Icon-only, minimal depth, large touch targets | Icon + text, 2 levels deep | Standard navigation |
   | Text content | Voice-over only, no reading required | Short text + voice support | Standard text |
   | Input method | Tap, drag, voice | Tap, drag, voice, simple typing | All methods |
   | Session timer | Hard cap (10-15 min), parent-configurable | Soft reminder (20 min), override-able | Optional reminder |
   | Error messages | Character animation + voice | Simple text + character | Standard text |
   | Settings access | Hidden from child (parent PIN) | Limited child access | Shared access |

### Output Format

```markdown
# Age Gating Design: [Product Name]

## Age Bands
| Band | Age Range | Label | Key Characteristics | Parental Involvement |
|------|-----------|-------|--------------------:|---------------------|
| [band] | [range] | [label] | [summary] | [level] |

## Feature Access Matrix
| Feature | Band A | Band B | Band C | Gating Rationale |
|---------|--------|--------|--------|-----------------|
| [feature] | [access level] | [access level] | [access level] | [safety/developmental] |

## Age Determination
- **Primary method**: [how age is known]
- **Override rules**: [parent adjustments]
- **Transition logic**: [what happens at band boundaries]

## UI Adaptations
[Table of UI differences per band]

## Parent Controls
| Setting | Default | Parent Can Adjust? |
|---------|---------|-------------------|
| [setting] | [default per band] | [yes/no + range] |
```

Save as `age-gating-[product-name].md`.

### Further Reading
- Piaget, J. (1952). *The Origins of Intelligence in Children*. International Universities Press.
- ICO (UK). "Age Appropriate Design Code" — 15 standards for child-accessible services.
- Common Sense Media. "Design Guidelines for Kid-Friendly Apps."
- UNICEF. "Industry Toolkit: Children's Online Privacy and Freedom of Expression." (2018)
