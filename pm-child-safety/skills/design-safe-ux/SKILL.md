---
name: design-safe-ux
description: "Design child-safe interaction patterns, content moderation, and protective UX for children's EdTech products. Use when reviewing or designing UX flows where children interact with user-generated content, AI-generated content, communication features, or external links."
---

## Design Child-Safe UX

Safe UX for children is not just about blocking bad content — it's about designing an environment where children can explore, learn, and create without encountering harm. This includes content safety (what they see), interaction safety (what they can do), and behavioral safety (how the product avoids manipulative patterns).

### Domain Context

**The UK Age Appropriate Design Code (AADC)** provides the most comprehensive framework for child-safe design. Its 15 standards include:

- **Best interests of the child** — The child's wellbeing takes priority over commercial interests
- **Age-appropriate application** — Features adapt to the child's age and capacity
- **Transparency** — Privacy information is provided in age-appropriate language
- **Detrimental use of data** — Don't use children's data in ways that are detrimental to their wellbeing
- **Nudge techniques** — Don't use design tricks to encourage children to provide more data or weaken privacy
- **Connected toys and devices** — Apply all standards to physical products with digital connectivity

**Dark patterns that are especially harmful for children:**
- Infinite scroll (no natural stopping point → screen time excess)
- Social validation features (likes, public follower counts → social comparison)
- Urgency tactics ("limited time!" "your streak will break!") → anxiety
- Loot boxes / random rewards → gambling-like behavior
- Pay-to-win mechanics → financial pressure on parents through children
- Autoplay → attention capture, undermines self-regulation

### Context

You are designing child-safe UX for **$ARGUMENTS**.

### Instructions

1. **Audit for Harmful Design Patterns**

   Review the current (or planned) product for these categories:

   | Pattern | Present? | Severity | Remediation |
   |---------|----------|----------|-------------|
   | **Infinite scroll** | [yes/no] | High | Add natural stopping points ("Great job! Time for a break?") |
   | **Autoplay** | [yes/no] | High | Require explicit action to start next content |
   | **Social comparison** (public rankings, likes) | [yes/no] | High | Make progress personal, not comparative |
   | **Streak anxiety** ("Don't break your streak!") | [yes/no] | Medium | Frame as positive ("Welcome back!") not guilt |
   | **Notification spam** | [yes/no] | Medium | Limit to parent-configured times, max 1/day |
   | **Random/variable rewards** (loot boxes) | [yes/no] | High | Use fixed, predictable reward schedules |
   | **Urgency/scarcity** | [yes/no] | Medium | Remove time pressure from children's experience |
   | **In-app purchase prompts to children** | [yes/no] | High | Route ALL purchase interactions to parent |
   | **External links/ads** | [yes/no] | High | Remove entirely for Kids Category apps |
   | **Data collection disguised as play** | [yes/no] | High | Ensure any data-collecting interaction has consent |

2. **Design Content Safety**

   If the product displays any content not 100% pre-curated by your team:

   **AI-generated content:**
   - All AI outputs shown to children must be filtered for age-appropriateness
   - Implement content safety classifiers before display
   - Define a blocklist of topics: violence, sexual content, substance use, self-harm, hate speech, profanity, horror/fear
   - For educational AI: constrain outputs to the subject domain (don't let a math tutor discuss politics)
   - Human review pipeline for edge cases flagged by classifiers

   **User-generated content (if applicable):**
   - Pre-moderation (review before display) for children under 13
   - Post-moderation (with rapid takedown) for 13+
   - Automated + human moderation pipeline
   - Report mechanism accessible to children (simple: tap a flag icon)
   - Block/mute functionality

   **Content from the internet (if applicable):**
   - URL whitelisting, not blacklisting (only allow known-safe sources)
   - Safe search enforcement
   - No raw web browsing for children under 13

3. **Design Session Management**

   Help children (and parents) manage screen time:

   - **Session time limits:** Parent-configurable (default: 20 min for under-8, 30 min for 8-12)
   - **Break reminders:** Gentle, non-punishing ("You've been learning for 20 minutes! Time to stretch?")
   - **Natural stopping points:** Design sessions with clear endings rather than cliffhangers
   - **Bedtime mode:** Parent can set hours when the app is unavailable
   - **Daily/weekly reports to parents:** Total time, number of sessions, time distribution

   **Implementation principle:** The product should help children stop, not make it harder. This directly opposes engagement-maximization incentives — resolve in favor of the child.

4. **Design Communication Safety**

   If the product includes any form of communication between users:

   | Feature | Safety Design |
   |---------|--------------|
   | Text chat | Pre-written responses only (under 13). Filtered free text (13+). No private messaging. |
   | Voice chat | Real-time moderation or no voice chat for under-13. Recording and review capability. |
   | Photo sharing | Pre-moderation required. No face/location metadata. No external sharing. |
   | Video | Not recommended for under-13 without parent co-presence. |
   | Multiplayer | Matchmaking with known contacts only (parent-approved friends list). |

5. **Design the Reporting & Escalation System**

   - **Child-accessible report button:** Visible on any screen with user-generated or AI content. Simple icon (flag), one-tap action.
   - **Report categories:** "This makes me uncomfortable," "This is mean," "Something else." Use child-friendly language.
   - **Escalation flow:** Report → Auto-review (classifier) → Human review (within 24h) → Action (remove/warn/ban) → Reporter notified
   - **Parent notification:** If a child reports content, notify the parent.
   - **Emergency protocol:** If content suggests self-harm or abuse, escalate immediately to human review and provide crisis resources.

6. **Design Physical Safety** (for connected toys/robots)

   If the product includes a physical device:
   - Motor/movement safety limits (speed, force)
   - Audio volume limits (especially for headphones — max 85 dB for children)
   - No data collection when child is unaware (no always-on microphones)
   - Clear indicator when device is recording/listening (LED, sound)
   - Physical power-off mechanism accessible to parents

### Output Format

```markdown
# Child-Safe UX Design: [Product Name]

## Dark Pattern Audit
| Pattern | Status | Severity | Action Required |
|---------|--------|----------|----------------|
| [pattern] | [present/absent] | [H/M/L] | [remediation] |

## Content Safety
### AI Content Guardrails
- [Filtering rules and blocklists]
- [Review pipeline design]

### User-Generated Content (if applicable)
- [Moderation approach and pipeline]

## Session Management
| Setting | Default | Parent Configurable? |
|---------|---------|---------------------|
| [setting] | [value] | [yes/no] |

## Communication Safety Matrix
[Table from Step 4]

## Reporting System
- **Report mechanism**: [design]
- **Escalation flow**: [pipeline]
- **Emergency protocol**: [if applicable]

## Physical Safety (if applicable)
[Safety limits and indicators]

## Compliance Mapping
| AADC Standard | Status | Evidence |
|--------------|--------|----------|
| Best interests | [status] | [how met] |
| Nudge techniques | [status] | [how met] |
| Connected toys | [status] | [how met] |
```

Save as `safe-ux-design-[product-name].md`.

### Further Reading
- ICO (UK). "Age Appropriate Design: A Code of Practice for Online Services." (The 15 AADC standards)
- 5Rights Foundation. "Disrupted Childhood: The Cost of Persuasive Design." (2018)
- Common Sense Media. "Privacy Program: Best Practices for EdTech."
- UNICEF. "Memorandum on Artificial Intelligence and Child Rights." (2021)
- Kidron, B. & Rudkin, A. (2017). "Digital Childhood." 5Rights Foundation.
