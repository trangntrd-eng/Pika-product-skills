---
name: design-parent-engagement
description: "Design the parent experience layer — dashboards, communication, co-learning features, and renewal motivation. Use when the user of your product is a child but the buyer is a parent, and you need to keep parents informed, engaged, and willing to renew their subscription."
---

## Design Parent Engagement

In B2C children's EdTech, you have two users: the child who learns and the parent who pays. Most EdTech products optimize entirely for child engagement and neglect the parent — then wonder why renewals are low. Parents renew when they can *see* their child learning. This skill designs the parent experience that drives trust, satisfaction, and subscription retention.

### Domain Context

**The parent-child value gap in EdTech:**
- **Child's value perception:** "This is fun. I like playing it." (engagement-based)
- **Parent's value perception:** "My child is actually learning something." (outcome-based)

These are not the same. A child can love an app that teaches nothing (games). A child can dislike an app that teaches effectively (boring drills). The product must satisfy both — and communicate *learning outcomes* to the parent even when the child only talks about *fun*.

**Hattie's meta-analysis** on parental involvement: d = 0.51 (medium-large effect). But the type of involvement matters:
- **High-impact:** Setting expectations, discussing learning, showing interest in what the child learned
- **Low-impact:** Checking homework, enforcing screen time, monitoring app usage

**Your parent engagement design should encourage high-impact involvement,** not just provide monitoring tools.

### Context

You are designing the parent engagement system for **$ARGUMENTS**.

### Instructions

1. **Map the Parent Journey**

   Parents have their own lifecycle with your product:

   | Stage | Parent Mindset | Key Question | Product Must Provide |
   |-------|---------------|-------------|---------------------|
   | **Discovery** | "Will this help my child?" | Is it effective? | Social proof, efficacy claims, free trial |
   | **Onboarding** | "How does this work?" | How do I set it up for my child? | Simple setup, consent flow, initial configuration |
   | **First Week** | "Is my child using it?" | Is the child engaged? | Usage notifications, first progress report |
   | **First Month** | "Is my child learning?" | Can I see results? | Learning progress report, milestone celebration |
   | **Renewal Decision** | "Is it worth continuing?" | Has enough happened to justify the cost? | Outcome summary, comparison to baseline |
   | **Ongoing** | "Am I getting value?" | Keep me informed | Regular digests, conversation starters |
   | **At Risk** | "We've stopped using it" | Win us back | Re-engagement email with progress reminder |

2. **Design the Parent Dashboard**

   The dashboard is the parent's primary touchpoint. Design for scanning, not studying:

   **Above the fold (immediate answers):**
   - **This week's summary:** Sessions completed, minutes practiced, concepts mastered
   - **Streak status:** Current streak (with learning context, not just number)
   - **Highlight:** The single most impressive thing the child did this week ("Mastered all addition facts!")
   - **Suggested action:** One thing the parent can do ("Ask your child to tell you 3 new English words")

   **Below the fold (details for interested parents):**
   - **Skill-by-skill mastery:** Visual grid showing progress across all topics
   - **Time distribution:** What topics the child spent time on
   - **Struggle areas:** "Your child is working on [topic] — here's how to help" (frame positively)
   - **Historical trend:** Week-over-week or month-over-month progress chart

   **Design principles:**
   - Lead with achievements, not problems
   - Never use language that implies the child is "behind"
   - Show learning outcomes prominently, screen time secondarily
   - Make it feel like a celebration report, not a surveillance tool

3. **Design the Communication Cadence**

   | Communication | Channel | Frequency | Content |
   |--------------|---------|-----------|---------|
   | **Session summary** | Push notification | End of each session (optional) | "Your child mastered 3 new words today!" |
   | **Weekly digest** | Email + in-app | Weekly (Sunday/Monday) | Week summary, highlights, suggestion |
   | **Milestone alert** | Push notification | When achieved | "Your child just completed Module 2!" |
   | **Struggle alert** | In-app only | When detected | "Your child is working hard on [topic]" |
   | **Monthly report** | Email | Monthly | Full progress report with trend analysis |
   | **Renewal reminder** | Email | 7 days before renewal | Progress summary since subscription start |

   **Tone rules:**
   - Always lead with positive
   - Struggle framed as "working on" not "struggling with"
   - Include a specific parent action ("Ask your child about...")
   - Respect parent's time — be brief

4. **Design "Conversation Starters"**

   The highest-impact parent engagement is talking to their child about what they learned. Design prompts that make this easy:

   - After each session: "Today I learned about [topic]. Ask me: [specific question]!"
   - Weekly: "This week your child learned [X]. Try asking: '[conversation starter question]'"
   - At dinner table: "Fun fact your child can share: [interesting thing from today's content]"
   - Before bedtime: "Ask [child] to teach you how to say [word] in English!"

   **Why this matters:** When a child teaches a parent what they learned, it reinforces learning (generation effect), builds the parent's perception of value, and creates a positive family learning culture.

5. **Design the Renewal Decision Support**

   The subscription renewal is the most important parent decision. Before renewal:

   **7 days before renewal — Progress Summary Email:**
   ```
   Subject: [Child]'s learning journey with [Product] — 30-day recap

   Since starting, [Child] has:
   ✅ Mastered [N] concepts
   ✅ Completed [N] lessons
   ✅ Practiced [N] days

   Biggest achievement: [specific milestone]
   Currently working on: [current topic]

   [Renew to keep the momentum going →]
   ```

   **Key principles:**
   - Show concrete outcomes, not just activity metrics
   - Reference specific achievements (personalized, not generic)
   - Show what's coming next (investment in the future)
   - Make renewal frictionless (one-tap)
   - NEVER threaten loss of progress to drive renewal

6. **Design Parent Controls**

   Give parents meaningful control:

   | Control | Options | Default |
   |---------|---------|---------|
   | Daily time limit | 10-60 min | 20 min (under 8), 30 min (8+) |
   | Available hours | Schedule picker | No restriction |
   | Notification preferences | Per-type toggle | Weekly digest on, daily off |
   | Content difficulty | Auto / manual override | Auto (adaptive) |
   | Social features | On/off per feature | Age-appropriate defaults |
   | Streak notifications to child | On/off | On (positive framing) |

   **Keep controls simple.** Parents are busy. 6-8 settings maximum on one screen. Default to sensible values.

### Output Format

```markdown
# Parent Engagement Design: [Product Name]

## Parent Journey Map
| Stage | Duration | Key Question | Product Response |
|-------|----------|-------------|-----------------|
| [stage] | [typical timeframe] | [question] | [what we provide] |

## Parent Dashboard
### Above the Fold
[Components and layout]

### Detailed View
[Drill-down components]

### Design Principles
[Rules for tone and framing]

## Communication Plan
| Communication | Channel | Frequency | Content Pattern |
|--------------|---------|-----------|----------------|
| [type] | [channel] | [frequency] | [pattern] |

## Conversation Starters
[Examples and delivery mechanism]

## Renewal Support
- **7-day email**: [content template]
- **Cancellation save flow**: [what's shown]
- **Win-back sequence**: [for churned subscribers]

## Parent Controls
| Control | Options | Default |
|---------|---------|---------|
| [control] | [options] | [default] |

## Metrics
| Metric | Definition | Target |
|--------|-----------|--------|
| Parent dashboard open rate | % parents who view dashboard weekly | >30% |
| Conversation starter engagement | % parents who report talking about learning | >20% |
| Renewal rate | Subscription renewals / eligible | >70% |
| Parent NPS | Net promoter score from parent surveys | >50 |
```

Save as `parent-engagement-[product-name].md`.

### Further Reading
- Hattie, J. (2008). *Visible Learning*. Routledge. (Parental involvement effect size: d = 0.51)
- Fan, X. & Chen, M. (2001). "Parental Involvement and Students' Academic Achievement." *Educational Psychology Review*, 13(1).
- Goodall, J. & Montgomery, C. (2014). "Parental involvement to parental engagement." *Educational Review*, 66(3).
- Eyal, N. (2014). *Hooked*. Portfolio/Penguin. (For the dual-user engagement framework)
