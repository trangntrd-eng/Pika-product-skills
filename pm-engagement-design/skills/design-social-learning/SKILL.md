---
name: design-social-learning
description: "Design age-appropriate social and collaborative learning features — peer challenges, family learning, collaborative goals, and safe social interaction. Use when adding multiplayer, social, or collaborative elements to a children's EdTech product while maintaining safety."
---

## Design Social Learning Features

Social learning is one of the strongest drivers of both motivation and learning efficacy. Vygotsky's foundational insight — that children learn best in social contexts — is consistently supported by research. But social features in children's products carry the highest safety risks. This skill designs social mechanics that drive learning while remaining safe.

### Domain Context

**Why social features matter for EdTech:**
- **Peer tutoring effect** (Topping, 1996): Children who explain concepts to peers deepen their own understanding (effect size d = 0.55).
- **Social motivation** (Deci & Ryan): Relatedness is one of three core intrinsic motivators.
- **Accountability:** Social commitment increases follow-through on practice habits.
- **Family learning:** Parent involvement is the strongest predictor of children's educational outcomes (Hattie, d = 0.51 for parental engagement).

**Why social features are risky for children's products:**
- Cyberbullying, inappropriate content, predatory behavior
- Social comparison and self-esteem damage
- Privacy violations (sharing personal information)
- COPPA/GDPR restrictions on social features for under-13

**The spectrum of social features** (from safest to highest-risk):

| Feature | Safety Level | Age Suitability | Learning Value |
|---------|-------------|----------------|---------------|
| Parent-child shared progress | Very safe | All ages | High |
| Classroom/family aggregate stats | Very safe | All ages | Medium |
| Asynchronous cooperative goals | Safe | 6+ | High |
| Pre-written message exchange | Safe | 8+ | Medium |
| Peer comparison (anonymous) | Moderate | 10+ | Low |
| Real-time collaboration | Moderate | 10+ (moderated) | High |
| Free text chat | High risk | 13+ (moderated) | Medium |
| Video/voice chat | Very high risk | 13+ (heavily moderated) | High |

### Context

You are designing social learning features for **$ARGUMENTS**.

### Instructions

1. **Define Social Learning Goals**

   What learning outcomes should social features serve?

   - **Practice motivation:** "I practice because my friend practices" (accountability)
   - **Collaborative learning:** "We solve problems together" (peer tutoring)
   - **Family engagement:** "My parent knows what I'm learning" (home support)
   - **Healthy competition:** "I want to improve MY score" (self-improvement, not comparison)
   - **Teaching others:** "I explain concepts to my peer" (deepest learning)

   Pick 1-2 primary goals. Don't try to serve all five simultaneously.

2. **Design Family Learning Features**

   The safest and often most effective social features:

   **Parent Progress Dashboard:**
   - Weekly learning summary emailed/pushed to parent
   - Skill-by-skill mastery visualization
   - Time spent (with context: "15 minutes of focused practice" not just "15 minutes of screen time")
   - Conversation starters: "Ask your child what [concept] means — they learned it today!"

   **Co-Learning Mode:**
   - Activities designed for parent + child together (especially valuable for ages 4-7)
   - Parent reads the question, child answers on device
   - "Family challenge": Parent and child learn together, both contribute to a shared goal
   - Works especially well for language learning (parent practices too)

   **Sharing Achievements:**
   - Child can "show" a badge or mastery to parent (within app, not external sharing)
   - "Tell your parent" prompts after learning milestones
   - Parent can send a "proud of you" message back (pre-written options)

3. **Design Cooperative Learning Features**

   **Classroom/Group Goals:**
   - Aggregate goals: "Our class/family learned 500 words this week!" (collective achievement)
   - No individual exposure — only the group's aggregate progress is shown
   - Teacher/parent creates the group, invites members
   - Works without direct communication between children

   **Peer Challenges (Asynchronous):**
   - "Challenge a friend": Send a quiz to a friend, they complete it on their own time
   - Both participants see results after both complete (no real-time pressure)
   - Frame as fun, not competition: "See if your friend knows this too!"
   - Safety: Challenges use pre-built content only. No user-generated questions.

   **Collaborative Problem Solving (10+, moderated):**
   - Two learners work on the same problem simultaneously
   - Pre-written communication only ("I think it's A", "Try the other one", "Good idea!")
   - Turn-taking structure to prevent one child dominating
   - AI moderation of any free-form elements

4. **Design Healthy Comparison Mechanics**

   If any form of comparison is included:

   **Do:**
   - Compare child to their own past performance ("You improved 20% this week!")
   - Show anonymous aggregate stats ("78% of learners found this tricky too")
   - Celebrate personal bests and milestones

   **Don't:**
   - Individual leaderboards for children under 12
   - Ranking children against each other by name
   - Showing percentile rankings ("You're in the top 15%")
   - Making rewards contingent on being better than others

   **If leaderboards exist (12+ only):**
   - Opt-in only
   - Small group (friends only, not global)
   - Reset weekly (prevent permanent hierarchy)
   - Celebrate improvement, not position ("You moved up 3 spots!")
   - Always show personal stats alongside ranking

5. **Design the Safety Infrastructure**

   Every social feature needs a safety layer:

   | Component | Implementation |
   |-----------|---------------|
   | **Friend connections** | Parent-approved only. No friend suggestions. No public profiles. |
   | **Communication** | Pre-written messages for under-13. Filtered free text for 13+. |
   | **Content sharing** | No photo/video sharing between children. Learning artifacts only (scores, badges). |
   | **Reporting** | One-tap report button on any social interaction. |
   | **Blocking** | Children can block any peer. Blocked user cannot see blocker's activity. |
   | **Moderation** | Automated + human review for any free-form content. |
   | **Parent visibility** | Parents can see all social interactions their child has. |
   | **Emergency** | Content suggesting harm escalates to human review immediately. |

6. **Map Social Features to Age Bands**

   | Feature | 4-6 | 7-9 | 10-12 | 13+ |
   |---------|-----|-----|-------|-----|
   | Parent dashboard | ✅ | ✅ | ✅ | ✅ |
   | Co-learning mode | ✅ | ✅ | Optional | ❌ |
   | Group goals (aggregate) | ✅ | ✅ | ✅ | ✅ |
   | Async peer challenges | ❌ | ✅ (parent-approved friends) | ✅ | ✅ |
   | Pre-written messages | ❌ | ❌ | ✅ | ✅ |
   | Collaborative solving | ❌ | ❌ | ✅ (moderated) | ✅ |
   | Free text (filtered) | ❌ | ❌ | ❌ | ✅ |
   | Self-comparison | ✅ | ✅ | ✅ | ✅ |
   | Anonymous peer comparison | ❌ | ❌ | ✅ (opt-in) | ✅ |

### Output Format

```markdown
# Social Learning Design: [Product Name]

## Social Learning Goals
- **Primary**: [goal]
- **Secondary**: [goal]

## Family Learning Features
### Parent Dashboard
[Components and design]

### Co-Learning Mode
[Design and target age]

### Achievement Sharing
[Mechanics and safety constraints]

## Peer Learning Features
### Cooperative Goals
[Group mechanics and safety]

### Peer Challenges
[Challenge design and safety]

### Collaborative Learning (if applicable)
[Interaction design and moderation]

## Comparison Mechanics
[What's compared, how, safety guardrails]

## Safety Infrastructure
| Component | Implementation | Age Threshold |
|-----------|---------------|--------------|
| [component] | [details] | [age] |

## Age Band Matrix
[Feature availability by age]

## Metrics
| Metric | Definition | Target |
|--------|-----------|--------|
| Family engagement rate | % parents viewing dashboard weekly | >40% |
| Social feature adoption | % learners using any social feature | >25% |
| Social-driven return | Sessions triggered by social interaction | >10% |
| Safety incident rate | Reports per 1000 social interactions | <1 |
```

Save as `social-learning-[product-name].md`.

### Further Reading
- Vygotsky, L. S. (1978). *Mind in Society*. Harvard University Press.
- Topping, K. J. (1996). "The Effectiveness of Peer Tutoring." *Educational Psychology*, 16(3).
- Slavin, R. E. (1995). *Cooperative Learning: Theory, Research, and Practice*. Allyn & Bacon.
- Hattie, J. (2008). *Visible Learning*. Routledge. (Effect sizes for cooperative learning: d = 0.41; peer tutoring: d = 0.55)
