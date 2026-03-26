---
name: evaluate-learning-efficacy
description: "Measure whether your EdTech product actually produces learning outcomes — not just engagement. Use when designing efficacy measurement frameworks, analyzing learning data, or preparing evidence that your product works for investors, parents, or school partners."
---

## Evaluate Learning Efficacy

This is the skill that separates real EdTech from dressed-up entertainment. Engagement metrics (DAU, session length, retention) tell you if people *use* your product. Efficacy metrics tell you if they *learn* from it. The most successful EdTech companies (Duolingo, Khan Academy, BYJU'S) all invest heavily in proving efficacy — it drives word-of-mouth, parent trust, and institutional sales.

### Domain Context

**Kirkpatrick's Four Levels of Evaluation (1959, updated 2016)** — adapted for EdTech:

| Level | Question | EdTech Measurement | Typical Metrics |
|-------|----------|-------------------|-----------------|
| 1. Reaction | Did learners enjoy it? | NPS, ratings, session engagement | 4.5+ stars, >70% sessions completed |
| 2. Learning | Did learners actually learn? | Pre/post assessments, mastery rates | Statistically significant improvement |
| 3. Behavior | Do learners apply what they learned? | Transfer tasks, real-world performance | Improved school grades, test scores |
| 4. Results | Did it produce meaningful outcomes? | Long-term outcomes, life impact | College readiness, career outcomes |

**Most EdTech products only measure Level 1 (engagement).** Measuring Level 2 (learning) is the minimum bar for credibility. Level 3 requires partnerships with schools/parents. Level 4 requires years of longitudinal data.

**Effect size (Cohen's d)** is the standard measure for learning impact:
- d = 0.20: Small effect (barely noticeable)
- d = 0.40: Medium effect (equivalent to one year of typical schooling growth)
- d = 0.60: Large effect (meaningful, visible improvement)
- d = 0.80+: Very large effect (transformative — rare in EdTech)

**Hattie's hinge point (d = 0.40):** Any intervention with an effect size above 0.40 is worth doing. Below 0.40, question whether the engineering investment is justified.

### Context

You are designing the learning efficacy measurement framework for **$ARGUMENTS**.

### Instructions

1. **Define What "Learning" Means for Your Product**

   Before measuring, be precise about what you're claiming:
   - **Knowledge gain:** Learner knows more facts/concepts than before (measurable via pre/post tests)
   - **Skill acquisition:** Learner can do something they couldn't before (measurable via performance tasks)
   - **Fluency improvement:** Learner performs faster/more accurately than before (measurable via response time + accuracy)
   - **Transfer:** Learner applies learning in new contexts (hardest to measure, highest value)
   - **Attitude/motivation change:** Learner feels differently about the subject (measurable via surveys, but weakest evidence)

   Be honest: most B2C EdTech delivers knowledge gain and fluency improvement. Claims of transfer or attitude change require stronger evidence.

2. **Design the Pre/Post Measurement**

   The gold standard for Level 2 (Learning) efficacy:

   **Pre-test → Intervention (your product) → Post-test**

   Design requirements:
   - **Pre-test and post-test must be equivalent but not identical** — same difficulty, same objectives, different items. Otherwise you're measuring item memorization.
   - **Timing:** Pre-test at first session. Post-test after defined learning period (e.g., after completing Module 1, or after 30 days of use).
   - **Control for test-retest effect:** If possible, include a control group that takes both tests without using the product. (Easier in school partnerships than B2C.)
   - **Minimum sample size:** For meaningful statistical conclusions, n ≥ 30 per group. For publishable research, n ≥ 100.

   **Lightweight alternative for B2C (no control group):**
   - Use the product's own diagnostic assessment as pre-test (placement quiz at onboarding)
   - Use summative assessments as post-test
   - Compare pre/post scores using paired t-test or Wilcoxon signed-rank test
   - Report effect size (Cohen's d) alongside p-values
   - Caveat: Without a control group, you can't attribute improvement solely to your product

3. **Define the Efficacy Metrics Dashboard**

   | Metric | Definition | Target | Measurement Method |
   |--------|-----------|--------|-------------------|
   | **Learning gain** | Post-test score - Pre-test score | d ≥ 0.40 | Pre/post assessment |
   | **Mastery rate** | % of learners achieving mastery per unit | ≥ 70% | Summative gate data |
   | **Time to mastery** | Average sessions to achieve unit mastery | Decreasing over time | Assessment timestamps |
   | **Retention rate** | % of mastered concepts retained after 30 days | ≥ 60% | Spaced review performance |
   | **Fluency growth** | Response time improvement on same item types | >20% faster over 30 days | Response time tracking |
   | **Error pattern reduction** | Decrease in specific error types over time | Declining trend | Error classification data |
   | **Completion-to-mastery ratio** | Of those who complete content, % who master it | ≥ 80% | Completion + mastery data |

4. **Segment Efficacy Analysis**

   Efficacy varies dramatically across learner segments. Always break down by:
   - **Starting level:** Do beginners learn more than advanced learners? (Common — ceiling effect)
   - **Usage intensity:** Is there a dose-response relationship? (More use = more learning? Where are diminishing returns?)
   - **Age group:** Does the product work equally well for 6-year-olds and 10-year-olds?
   - **Learning style/pace:** Do fast learners and slow learners both benefit?
   - **Engagement pattern:** Do daily users learn more than weekly users? (Seems obvious, but quantify it)

   **Key question:** Is your product effective for the learners who need it most, or only for those who were already motivated?

5. **Design the Learning Funnel**

   Adapt the product funnel concept for learning:

   ```
   Onboarded (took placement test)
   └── Started learning (completed ≥ 1 lesson)
       └── Engaged learner (completed ≥ 1 week)
           └── Active learner (completed ≥ 1 unit)
               └── Demonstrated learning (passed ≥ 1 mastery gate)
                   └── Retained learning (passed 30-day review)
                       └── Transferred learning (applied in new context)
   ```

   Measure conversion rates between each stage. The drop-off between "Active learner" and "Demonstrated learning" is the most critical — it's where engagement fails to convert to learning.

6. **Plan for Efficacy Communication**

   Who needs to see efficacy data and how?

   - **Parents:** "Your child improved their vocabulary by 40% this month" (simple, specific, personal)
   - **Marketing:** "87% of active learners demonstrate measurable improvement" (headline stat, defensible)
   - **Investors:** "Average effect size d = 0.52 across n = 1,200 learners, with dose-response relationship" (rigorous, contextualized)
   - **School partners:** "Aligned to [standard], with pre/post data showing [X] grade-level improvement" (standards-mapped, comparable)
   - **Internal team:** Full dashboard with segment breakdowns, trends, and leading indicators

7. **Establish a Research Partnership** (Optional but High-Value)

   For credible third-party validation:
   - Partner with a university education department for an independent study
   - Use a randomized controlled trial (RCT) design if possible
   - Pre-register the study (prevents cherry-picking results)
   - Aim for publication in a peer-reviewed journal (gold standard for credibility)
   - Timeline: 6-12 months minimum for a meaningful study

### Output Format

```markdown
# Learning Efficacy Framework: [Product Name]

## Learning Claims
| Claim | Type | Evidence Required | Current Status |
|-------|------|------------------|----------------|
| [what you claim the product teaches] | [knowledge/skill/fluency/transfer] | [measurement approach] | [have data / planned / aspirational] |

## Pre/Post Measurement Design
- **Pre-test**: [instrument description]
- **Post-test**: [instrument description]
- **Timing**: [when each is administered]
- **Sample**: [target n, segments]
- **Analysis**: [statistical method]
- **Control**: [control group plan, or caveat if none]

## Efficacy Metrics Dashboard
| Metric | Definition | Target | Current | Trend |
|--------|-----------|--------|---------|-------|
| [metric] | [definition] | [target] | [value] | [direction] |

## Segmented Analysis Plan
| Segment | Hypothesis | Measurement |
|---------|-----------|-------------|
| [segment] | [expected difference] | [how to test] |

## Learning Funnel
[Funnel stages with current conversion rates]

## Communication Plan
| Audience | Key Message | Evidence Level | Format |
|----------|------------|---------------|--------|
| Parents | [message] | [Kirkpatrick level] | [in-app / email / report] |
| Marketing | [message] | [level] | [website / case study] |
| Investors | [message] | [level] | [deck / data room] |

## Research Roadmap
- [ ] Implement pre/post assessment system
- [ ] Collect baseline data (n ≥ [target])
- [ ] First efficacy analysis at [date]
- [ ] Explore university research partnership
```

Save as `learning-efficacy-[product-name].md`.

### Further Reading
- Kirkpatrick, J. D. & Kirkpatrick, W. K. (2016). *Kirkpatrick's Four Levels of Training Evaluation*. ATD Press.
- Hattie, J. (2008). *Visible Learning*. Routledge. (Meta-analysis of 800+ meta-analyses on learning interventions)
- What Works Clearinghouse (IES). *Procedures Handbook* (v5.0). (Gold standard for EdTech efficacy evaluation in the US)
- Means, B. et al. (2013). *Effectiveness of Online and Blended Learning*. US Department of Education. (Large meta-analysis of technology-mediated learning)
- Cohen, J. (1988). *Statistical Power Analysis for the Behavioral Sciences*. Routledge. (Defines effect size conventions)
