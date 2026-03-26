# Opportunity Solution Tree — H1 2026 (Combined View)

> Combines: Original OST, Assumption Analysis of 5 team proposals, Photo-to-Lesson performance data
> Framework: Teresa Torres, Continuous Discovery Habits
> Date: 2026-03-24

---

## Desired Outcome

**Increase 30-day subscription renewal rate from 15% → 35% by July 1, 2026 (at 120k VND/month)**

| KR | Current | Target | Status |
|----|---------|--------|--------|
| **KR1 Retention**: Active ≥15 days in first 30 days | 24% | 80% | Far below |
| **KR2 Value**: ≥2 quality sessions/day | Unknown | 2/day | No tracking |
| **KR3 Qualified Lead**: % parents willing to renew | Unknown | 60% | No tracking |
| **KR4 Close Rate**: % leads who renew | Unknown | 60% | No tracking |

### Context Update (from team proposals + PTL data)
- **Total registered parents**: 5,426 | **Weekly active rate**: 36.8% (~2,000 WAU)
- **D7 churn** is the primary retention bottleneck — most users disengage within the first week
- **Photo-to-Lesson** launched Mar 19 with strong parent-side adoption (210 users, 87.9% acceptance) but only 14.2% child completion
- **Team capacity is overextended**: 5 proposals collectively propose 40+ features across 10+ pillars. The roadmap (P5) has no timeline for STT — the #1 user complaint.
- **Churned user interviews** (P3) confirm: ASR failures + content too hard + child can't engage independently = top 3 churn drivers

---

## Opportunity Map (Updated)

Opportunities re-scored with new evidence from team proposals (P1–P5), Photo-to-Lesson data, and the assumption analysis. **New opportunities added in bold.**

| # | Opportunity | Imp. | Sat. | Score | Evidence Update | KR Impact |
|---|------------|------|------|-------|----------------|-----------|
| **O1** | Child's speech isn't recognized — "Pika nghe ko hiểu" | 1.0 | 0.2 | **0.80** | All 5 proposals acknowledge. P5 roadmap has STT with **no timeline**. P3: 4/5 churned users report. Still #1 blocker. | KR1, KR2 |
| **O2** | Beginner content too hard — "câu dài quá, con chưa biết gì" | 0.95 | 0.15 | **0.81** | P2: learning content optimization. P3: Pre-A1 too hard. P5: "First lessons v2" planned but vague. Excitement cliff at Day 3-4 confirmed. | KR1, KR2 |
| **O3** | Child can't engage independently — "chỉ dùng khi bố mẹ ngồi cạnh" | 0.9 | 0.25 | **0.68** | P3 confirms. P4 proposes parent activation but doesn't solve child independence. PTL data shows **30.4% of robot sessions end within 4 user turns** — children aren't engaging even when lessons are assigned. | KR1 |
| **O4** | Can't stop Pika / no sleep mode | 0.7 | 0.1 | **0.63** | Not addressed in any proposal. Still unscheduled. | KR1 |
| **O5** | Parents want to customize learning content | 0.8 | 0.35 | **0.52** ↓ | **Satisfaction improved**: PTL partially addresses this. 210 parents used PTL in 5 days, 53.2% organic prompts. But PTL has a **14.2% child completion problem** — parent customization works, child delivery doesn't. Score lowered because parent-side satisfaction is up, but child-side value delivery is still broken. | KR2, KR3 |
| **O6** | Parents lack visibility into child's learning | 0.85 | 0.15 | **0.72** | P4 proposes hook loop + daily reports. P5 has Notification system planned. PTL data gap: `conversation_reports` and `conversation_summaries` are **all null** — no post-session data for parents even in the newest feature. **Critical for KR3** (parents need to see value to renew). | KR3 |
| **O7** | WiFi reconnection friction | 0.6 | 0.1 | **0.54** | Not addressed in any proposal. Still unscheduled. Quick fix. | KR1 |
| **NEW O8** | **Parent creates lesson but child never does it** — PTL parent→child handoff gap | 0.85 | 0.1 | **0.77** | PTL data: 471 lessons delivered to robot, only 67 completed (14.2%). 30.4% of sessions end in ≤4 user turns. Parent is engaged but child isn't present/aware/motivated when lesson arrives. Bot-to-user turn ratio of 4.9:1 suggests Pika talks to itself. | KR1, KR2 |
| **NEW O9** | **Pika feels like a learning tool, not a friend** — children resist when parents push lessons | 0.8 | 0.2 | **0.64** | P3 (Dịu): "trẻ cảm thấy Pika như 1 công cụ học nên tạo cảm giác không muốn dùng." Parents assign lessons constantly → child perceives Pika as homework. PTL amplifies this: more parent-assigned content = more "tool" perception. P2's "Embedded English in Talk" is the counter-strategy. | KR1, KR2 |
| **NEW O10** | **Safety guardrail regression** — unsafe content reaching children | 1.0 | 0.0 | **1.00** | PTL data: 11 images flagged UNSAFE still generated lessons. 3 high-risk cases (knife, reproductive terminology). Retry bypass: same image flagged UNSAFE on first try passes on second. **Non-negotiable P0 fix — not an opportunity to prioritize, just a bug to fix immediately.** | Trust, Legal |

### Priority Ranking (Updated)

| Tier | Opportunities | Rationale |
|------|--------------|-----------|
| **P0 — Fix now** | O10 (Safety), O1 (ASR) | Safety is non-negotiable. ASR is the #1 blocker confirmed by all data sources and all 5 proposals. |
| **P0.5 — This sprint** | O2 (Beginner content), O8 (PTL handoff) | O2 drives the excitement cliff. O8 is urgent because PTL is live and parent-side metrics are strong but child-side is broken — if parents create lessons and children never do them, parents will lose faith in the product. |
| **P1 — Next sprint** | O3 (Independent engagement), O6 (Parent visibility) | O3 is the structural enabler for KR1 (active ≥15 days requires child engaging without parent). O6 directly drives KR3 (parents see value → willing to renew). |
| **P2 — This quarter** | O9 (Tool vs friend), O5 (Custom content), O4 (Sleep mode), O7 (WiFi) | O9 is important but addressed by getting O2+O3 right. O5 is partially addressed by PTL. O4+O7 are quick wins to schedule. |

---

## Solutions (Updated with Team Proposals + PTL Evidence)

### O10: Safety Guardrail Regression — P0 IMMEDIATE

> Not an opportunity to brainstorm — this is a critical bug. Including for completeness.

| ID | Solution | Source | Effort | Status |
|----|----------|--------|--------|--------|
| S10.1 | **Hard-gate in pipeline**: If vision returns `[UNSAFE_CONTENT]`, abort pipeline, return error to parent app. Do not proceed to lesson generation. | PTL Report recommendation | Low | **Ship today** |
| S10.2 | **Fix non-deterministic screening**: Same image flagged UNSAFE on try 1, SAFE on retry. Add image hash caching — if an image was flagged once, all retries with same hash are blocked. | PTL Report finding | Medium | Ship this week |
| S10.3 | **Whitelist educational safety topics**: "bảo vệ cơ thể" (body safety for children) is legitimate education. Refine safety categories so educational content isn't over-blocked. | PTL Report case #7 | Low | Next sprint |

---

### O1: Speech Recognition Failures — P0

> "Pika nghe rất tệ" — 35+ Q1 mentions, 4/5 churned users (P3), all proposals acknowledge, P5 roadmap has **no timeline**

| ID | Solution | Source | Effort | Impact | Confidence |
|----|----------|--------|--------|--------|------------|
| S1.1 | **Child-voice ASR tuning**: Fine-tune STT on Vietnamese children's voice data (5-12 yo) | Original OST | High | Very High | Medium |
| S1.2 | **Lenient recognition mode for beginners**: Lower confidence threshold for Pre-A1/Starter. Accept approximate pronunciation. | Original OST + P2 (Vấn đề 1) | Medium | High | High |
| S1.3 | **Regional accent profiles**: Southern/Central Vietnamese support. Parent sets preference in app. | Original OST | High | High | Medium |
| S1.4 | **Graceful failure responses**: Stop repeating "ù tai." Show what Pika heard. After 2 failures, offer options. | Original OST + P2 | Low | Medium | High |
| S1.5 | **Pronunciation energy bar** (from P2): Visual feedback showing accuracy level instead of binary right/wrong | P2 (Long) — Assumption U4 | Low | Medium | Medium |

**Key insight from Assumption Analysis**: P2 proposes fixing pronunciation correction logic, but the underlying problem is more fundamental — Pika can't hear the child at all (ASR failure), not just scoring errors. **Diagnosis needed first** (Validation #4 from Assumption Analysis): What % of failures are "heard wrong words" vs. "heard right words but scored wrong"?

#### Experiments

| Exp | Hypothesis | Method | Metric | Threshold |
|-----|-----------|--------|--------|-----------|
| E1.1 | Lowering ASR threshold for Pre-A1 increases recognition success without degrading quality | A/B: lower threshold 20% for new Pre-A1 users | ASR success rate; false positive ≤15% | Success: 60% → 80% |
| E1.2 | Varied failure responses reduce session abandonment after ASR fails | Deploy new failure UX to 50% of users | Session abandonment after ASR failure | Drop: ~40% → ≤20% |
| E1.D | **Diagnostic**: Categorize 200 recent ASR failures into "heard wrong" vs. "scored wrong" | Log analysis — no build required | % distribution | Determines S1.1 vs S1.2 priority |

---

### O2: Beginner Content Too Hard — P0.5

> "câu khá dài và khó" — 30+ Q1 mentions, P3 confirms Pre-A1 too hard, P5 plans "First lessons v2" but vague

| ID | Solution | Source | Effort | Impact | Confidence |
|----|----------|--------|--------|--------|------------|
| S2.1 | **"Starter" level below Pre-A1**: Single-word vocabulary from daily life. Vietnamese scaffolding → English word → short phrase progression over weeks | Original OST | Medium | Very High | High |
| S2.2 | **Fun-first onboarding (Days 1-3)**: Games + Vietnamese chat + easy English words. No structured lessons until Day 4+. | Original OST + P2 (todo flow) + P3 ("tool vs friend") | Medium | Very High | High |
| S2.3 | **Adaptive difficulty engine**: Detect child struggle (silence, failures, Vietnamese fallback) → auto-downgrade to simpler content | Original OST + P5 ("Adaptive learning logic") | High | High | Low |
| S2.4 | **Assessment test before first lesson**: Accurately place child at right level from Day 1 | P5 (Learning Design pillar) | Medium | High | Medium |
| S2.5 | **Embedded English in Talk mode**: Weave vocabulary and grammar into fun conversations instead of structured lessons | P5 ("Embedded English practice in Talk") + P2 (Buddy Talk) | Medium | High | Medium |

**Key insight from Assumption Analysis**: P2's hypothesis that D1→D7 churn comes from "disconnected todo flow" (U5) is probably wrong — Q1+P3 data points to content difficulty as the real driver. However, P5's "Embedded English in Talk" (S2.5) is a **sleeper hit** that could solve both the content difficulty AND the "Pika feels like a tool" problem (O9) simultaneously — by making learning feel like play.

#### Experiments

| Exp | Hypothesis | Method | Metric | Threshold |
|-----|-----------|--------|--------|-----------|
| E2.1 | Starter level with single-word vocab improves Pre-A1 week-1 completion | Build 10-lesson Starter module, A/B with new Pre-A1 | Lessons completed W1 + D7 retention | ≥5 lessons; D7 +15pp |
| E2.2 | Fun-first Days 1-3 increases D7 retention | Modify onboarding for new cohort | D7 active rate | +20pp |
| E2.4 | Assessment test → correct level placement → better D7 retention | Deploy assessment for new users; compare D7 for tested vs. untested | D7 retention by level accuracy | Tested group +10pp |
| E2.5 | Embedded English in Talk produces equal vocab retention with higher enjoyment | A/B: Embedded Talk English vs. standard Learn mode | Vocab retention + session length + return rate | Retention ≥80% of Learn mode; session length +30% |

---

### O8: Parent→Child Handoff Gap (NEW) — P0.5

> PTL: 471 delivered, 67 completed (14.2%). 30.4% of sessions end in ≤4 user turns. Bot talks to itself (4.9:1 ratio).

| ID | Solution | Source | Effort | Impact | Confidence |
|----|----------|--------|--------|--------|------------|
| S8.1 | **Robot-side lesson notification**: When parent assigns a lesson, Pika proactively tells the child: "Mẹ vừa gửi cho bạn một bài học mới! Mình thử nhé?" next time child interacts | PTL Report rec. #3 | Low | High | High |
| S8.2 | **XP scoring for PTL lessons**: Children currently get 0 XP for PTL lessons. Connect XP system → child gets reward → motivation to complete | PTL Report rec. #2 | Low | High | High |
| S8.3 | **Lesson completion notification to parent**: Push to parent when child finishes (or doesn't finish). Closes the feedback loop. Enables P4's hook model. | PTL Report rec. #5 + P4 (hook loop) | Low | Medium | High |
| S8.4 | **Shorten PTL lessons**: Investigate if lessons are too long — 23% of incomplete sessions had 20+ user turns (high engagement but didn't finish). Test shorter lesson variants. | PTL Report §5.4 | Medium | Medium | Medium |
| S8.5 | **"Learn together" mode**: Parent starts PTL lesson with child present (prompt on app: "Bạn có muốn bắt đầu cùng con không?"). Addresses O3 for PTL specifically. | PTL data: re-assigned lessons complete at 1.6× rate (24.5% vs 15.3%) — parent involvement = higher completion | Medium | Medium | Medium |

**Key insight from PTL data**: Custom-photo lessons complete at **19.8%** vs. sample photos at 13.0% and text-only at 5.1%. **Personal relevance drives completion.** The highest-engagement completed session was 148 user turns / 46 minutes — when the content is right, children engage deeply.

#### Experiments

| Exp | Hypothesis | Method | Metric | Threshold |
|-----|-----------|--------|--------|-----------|
| E8.1 | Robot notification increases lesson start rate | A/B: Pika announces new lesson vs. silent delivery | % of delivered lessons where child starts (≥1 user turn) | From ~70% → 85% |
| E8.2 | XP scoring increases completion rate | Connect XP for PTL lessons. Compare before/after | Completion rate (14.2% baseline) | → 25%+ |
| E8.3 | Shorter lessons improve completion | Create 5-min vs. 10-min vs. 15-min lesson variants | Completion rate by length | Find optimal length |

---

### O3: Child Can't Engage Independently — P1

> P3: "chỉ dùng khi bố mẹ động viên, ngồi cùng." P4 tries to solve via parent activation, but child independence is upstream.

| ID | Solution | Source | Effort | Impact | Confidence |
|----|----------|--------|--------|--------|------------|
| S3.1 | **Proactive engagement engine**: Pika initiates at scheduled times with personalized hooks — games, fun facts, "đố bạn biết..." No English pressure. | Original OST + P1 (Attraction strategy) + P5 (Personality, Talk topics) | Medium | Very High | Medium |
| S3.2 | **Struggle-to-fun fallback**: Detect disengagement (silence >15s, "không biết") → auto-switch to games/chat → re-introduce learning after re-engagement | Original OST + P5 (Adaptive learning) | Medium | High | Medium |
| S3.3 | **Parent async mission via app**: Parent sets daily mission → Pika presents as quest → child completes independently → parent gets notification | Original OST + P4 (hook loop) + PTL (parent-assigns model proven) | Medium | High | Medium |

**Key insight from Assumption Analysis**: P4 assumes parent activation drives retention (B4). But child engagement is upstream — if the child doesn't engage, the parent hook loop has nothing to loop on. **Solve O3 first, then P4's framework will work.**

---

### O6: Parents Lack Visibility — P1

> P4's core thesis. PTL data confirms: `conversation_reports` and `conversation_summaries` are all null even for the newest feature.

| ID | Solution | Source | Effort | Impact | Confidence |
|----|----------|--------|--------|--------|------------|
| S6.1 | **Daily conversation summary push notification**: 3-line summary of what child discussed/learned today | Original OST + P4 (hook loop Lv1: "chứng minh tức thì") | Low | High | High |
| S6.2 | **Weekly learning report**: Vocab learned, pronunciation progress, time spent, topics. In-app + optional email. | Original OST + P4 (hook loop Lv2: "chứng minh qua thời gian") + P2 | Medium | Very High (for KR3) | Medium |
| S6.3 | **PTL completion report**: When child finishes a PTL lesson, parent sees: what the child said, how they did, which words they learned | PTL Report (currently all null) | Medium | High | High |
| S6.4 | **Pika status in app**: Is Pika sleeping, chatting, or in lesson mode? | Original OST + Q1 feedback | Low | Medium | High |

**Key insight from PTL data**: The notification funnel shows **38.6% open rate** — parents do read notifications. S6.1 (daily summary push) has a viable delivery channel. But the content generation (conversation_reports/summaries) isn't connected yet — this is infrastructure work that must happen before any reporting feature can work.

---

### O9: Pika Feels Like a Tool, Not a Friend — P2

> P3 (Dịu): "trẻ cảm thấy Pika như 1 công cụ học." PTL may amplify this if used for constant lesson assignment.

| ID | Solution | Source | Effort | Impact | Confidence |
|----|----------|--------|--------|--------|------------|
| S9.1 | **Fun-first default mode**: Pika's default when turned on = playful chat, not "time for your lesson!" Change greeting to be curiosity-driven. | P3 insight + P1 (Personality) | Low | High | Medium |
| S9.2 | **Embedded English in Talk** (= S2.5): Learn English through fun conversations, not structured drills. "The sleeper hit." | P5 + P2 (Buddy Talk) | Medium | High | Medium |
| S9.3 | **Pika personality moments**: Random fun facts, silly songs, "guess what happened to me" — creates curiosity-pull instead of lesson-push | P1 (Attraction strategy) + P5 (Personality) | Low | Medium | Medium |
| S9.4 | **Limit parent lesson assignment frequency**: Guide parents to assign max 1 structured lesson/day. Rest = organic play. Pika tells parent if over-assigning. | P3 (V9, V12) | Low | Medium | Low |

**Key insight**: O9 is largely solved by getting O2 (fun-first onboarding) and O3 (independent engagement) right. If Pika's default is fun and learning is embedded in play, the "tool" perception disappears. This doesn't need its own heavy investment — it needs the other solutions to be designed with this lens.

---

## Full Tree Visualization

```
                        ┌──────────────────────────────────────────────┐
                        │              DESIRED OUTCOME                  │
                        │      30-day renewal: 15% → 35%                │
                        │  KR1: Active 15d   KR2: 2 quality sessions    │
                        │  KR3: 60% willing   KR4: 60% close            │
                        └────────────────────┬─────────────────────────┘
                                             │
          ┌────────────┬────────────┬────────┼────────┬────────────┬──────────┐
          │            │            │        │        │            │          │
     ┌────▼────┐  ┌────▼────┐ ┌────▼───┐ ┌──▼──┐ ┌──▼───┐  ┌────▼────┐ ┌──▼──┐
     │O10 SAFE │  │O1 ASR   │ │O2 BEGIN│ │ O8  │ │ O3   │  │O6 PARENT│ │ O9  │
     │CRITICAL │  │FAILURES │ │CONTENT │ │ PTL │ │INDEP.│  │VISIBLE. │ │TOOL │
     │Score:1.0│  │Scr: 0.80│ │Scr:0.81│ │HAND │ │ENGAG.│  │Scr: 0.72│ │ vs  │
     │   P0    │  │   P0    │ │  P0.5  │ │OFF  │ │ P1   │  │   P1    │ │FRND │
     └────┬────┘  └────┬────┘ └────┬───┘ │0.77 │ └──┬───┘  └────┬────┘ │0.64 │
          │            │           │      │P0.5 │    │            │      │ P2  │
       S10.1        S1.1-S1.5   S2.1-S2.5└──┬──┘  S3.1-S3.3   S6.1-S6.4└──┬──┘
       Hard         Child ASR   Starter      │     Proactive    Daily       │
       gate         + Lenient   + Fun-first  │     engine +     report +  S9.1-S9.4
       (ship        mode +      + Embedded   │     Struggle     Weekly    Fun default
       today)       Energy bar  English Talk │     fallback     report    + Personality
                                             │
                                          S8.1-S8.5
                                          Robot notify +
                                          XP scoring +
                                          Shorter lessons +
                                          Learn together
```

---

## Execution Roadmap (Revised)

### Sprint 0 — NOW (This week)

| Item | Solution | Effort | Why now |
|------|----------|--------|---------|
| Safety hard-gate | S10.1, S10.2 | Low | Critical regression. Children exposed to unsafe content. **Non-negotiable.** |
| ASR diagnostic | E1.D | None (log analysis) | Determines whether to prioritize ASR tuning (S1.1) or lenient mode (S1.2) |
| D1→D7 diagnostic | Validation #1 from Assumption Analysis | None (log analysis) | Validates P2's todo-flow hypothesis (U5) before investing sprints |
| PTL: Connect XP scoring | S8.2 | Low | Live feature with 210 users getting 0 XP. Quick win for completion rate. |

### Sprint 1-2 (April Week 1-2)

| Item | Solution | Effort | KR Impact |
|------|----------|--------|-----------|
| ASR lenient mode for Pre-A1 | S1.2 | Medium | KR1, KR2 — immediate frustration reduction |
| ASR failure response variety | S1.4 | Low | KR1 — stop "ù tai" loop |
| Fun-first onboarding (Days 1-3) | S2.2 | Medium | KR1 — attack the excitement cliff |
| PTL: Robot lesson notification | S8.1 | Low | KR2 — close the handoff gap |
| PTL: Completion notification to parent | S8.3 | Low | KR3 — start the parent feedback loop |
| Sleep mode voice command | O4 fix | Low | KR1 — quick win, high frustration reducer |
| WiFi credential persistence | O7 fix | Low | KR1 — quick win |

### Sprint 3-4 (April Week 3 – May Week 1)

| Item | Solution | Effort | KR Impact |
|------|----------|--------|-----------|
| Starter level (10 lessons) | S2.1 | Medium | KR1, KR2 — serve the highest-churn segment |
| Assessment test → level placement | S2.4 | Medium | KR1 — prevent wrong-level assignment |
| Daily conversation summary push | S6.1 | Low | KR3 — parents see daily value proof |
| Proactive engagement engine | S3.1 | Medium | KR1 — child engages without parent |
| Pronunciation energy bar | S1.5 | Low | KR2 — better learning UX |
| PTL: Shorter lesson variants | S8.4 | Medium | KR2 — improve 14.2% completion |

### Sprint 5-6 (May Week 2 – June Week 1)

| Item | Solution | Effort | KR Impact |
|------|----------|--------|-----------|
| **Embedded English in Talk mode** | S2.5 / S9.2 | Medium | KR1, KR2 — the breakthrough: learning feels like play. Solves O2 + O9 simultaneously. |
| Weekly learning report | S6.2 | Medium | **KR3 — critical for renewal.** Parents must see tangible progress before July 1 renewal decision. |
| Child-voice ASR retraining (with collected data) | S1.1 | High | KR1, KR2 — deep fix, sustained improvement |
| Struggle-to-fun fallback | S3.2 | Medium | KR1 — prevent mid-session drop-off |
| PTL: Conversation reports connected | S6.3 | Medium | KR3 — PTL parents see what child learned |

### Sprint 7-8 (June — Pre-renewal)

| Item | Solution | Effort | KR Impact |
|------|----------|--------|-----------|
| Regional accent ASR profiles | S1.3 | High | KR1 — serve Southern/Central families |
| Adaptive difficulty engine | S2.3 | High | KR2 — auto-match content to child level |
| Parent async missions | S3.3 | Medium | KR1, KR2 — structured independent engagement |
| Fun-first default mode | S9.1 | Low | KR1 — polish, not foundation |
| Pika personality moments | S9.3 | Low | KR1 — delight layer |

### July 1: Renewal at 120k/month

By this point, a renewing parent should have experienced:
- Child can interact with Pika without frustration (ASR works)
- First week was fun, not overwhelming (fun-first onboarding + Starter level)
- Child engages most days independently (proactive engine + struggle fallback)
- Learning happens through conversation, not just drills (Embedded English in Talk)
- Parent receives weekly reports showing vocabulary growth and pronunciation improvement
- PTL lessons are completed and reported back to parent

---

## What Was Deprioritized (and Why)

| Item | Source | Why Deprioritized |
|------|--------|-------------------|
| Korean/Chinese language support | P5 | Zero validated demand. English isn't working yet. Defer to H2. |
| STEM/Social Sciences content expansion | P1, P5 | English is the anchor value proposition (Layer A). Expanding before it works dilutes focus and resources. |
| Adaptive Influence Framework | P1 | High implementation risk (F2). No parent demand signal. Requires safety guardrails that don't exist. Explore in H2. |
| Badge system / Virtual gift exchange | P4, P5 | Gamification amplifies a working product. Can't fix a broken one. Add after D7 retention >60%. |
| Parent real-world rewards | P4 | Assumption V17: most parents barely use existing app. Too complex for current engagement level. |
| To-do list customization | P5 | Assumption U5 likely wrong — D1→D7 churn is content/ASR, not todo structure. Validate first. |
| Ranking/leaderboard | P5 | May discourage Pre-A1 beginners who rank lowest. Add for A1+ after beginner experience is fixed. |
| Functional dependence strategy (full) | P1 | Right vision, wrong timing. Children must survive Week 1 before long-term dependence can form. Phase in H2. |
| App redesign/refactor (L0) | P4 | Large effort. Ship targeted improvements (report, notifications) first. Full redesign after content issues are fixed. |
| In-app usage guide / cẩm nang | P4 | Assumption V15: guides have low engagement. Contextual discovery > static documentation. |

---

## Critical Dependencies

```
Safety Fix (S10) ──────────────────► PTL continues operating safely
        │
ASR Diagnostic (E1.D) ────────────► Determines S1.1 vs S1.2 priority
        │
ASR Fix (S1.2/S1.1) ──────────────► Enables all learning features
        │                                    │
        ├── Starter Level (S2.1) ────────────┤
        │                                    │
        ├── Embedded English Talk (S2.5) ────┤
        │                                    │
        └── Pronunciation Energy Bar (S1.5) ─┤
                                             │
                                    Conversation Data Generated
                                             │
                              ┌──────────────┴──────────────┐
                              │                             │
                    Daily Summary (S6.1)          Weekly Report (S6.2)
                              │                             │
                              └──────────────┬──────────────┘
                                             │
                                    Parent Sees Value
                                             │
                                    Willing to Renew (KR3)
                                             │
                                    July 1 Renewal
```

**The chain**: Fix ASR → Children can learn → Learning generates data → Data feeds parent reports → Parents see value → Parents renew.

If ASR isn't fixed, **nothing downstream works**.

---

## Validation Priorities (from Assumption Analysis)

### Validate This Week (existing data)

| # | Question | Method | Informs |
|---|----------|--------|---------|
| 1 | ASR: "heard wrong" vs. "scored wrong" split? | Log analysis | S1.1 vs S1.2 priority |
| 2 | Is D1→D7 churn about todo flow or content? | Compare retention: todo-completers vs. non-completers | P2's hypothesis U5 |
| 3 | Does parent app engagement predict child retention? | Correlation: parent app opens vs. child D30 | P4's thesis B4 |
| 4 | What % of parents use "tạo bài"? | Analytics query | P2's assumption V8 |
| 5 | PTL: Why do 30.4% of sessions end in ≤4 turns? | Manual review of 15 transcripts | S8.1-S8.5 priority |

### Validate This Sprint

| # | Question | Experiment | Informs |
|---|----------|-----------|---------|
| 6 | Will parents read session summaries? | Push 1 test notification to 100 parents | S6.1 viability |
| 7 | Does fun-first Day 1 improve child return? | A/B: play-oriented vs. lesson-oriented greeting | S2.2, S9.1 |
| 8 | Do children understand the energy bar? | Paper prototype, 10 kids, 1 day | S1.5 |
| 9 | Does PTL XP scoring increase completion? | Before/after comparison | S8.2 impact |

---

## How This Tree Resolves Proposal Tensions

| Tension | Resolution |
|---------|-----------|
| P1 (long-term vision) vs. P2/P3 (fix basics now) | **Sequence**: Fix basics Sprint 0-4, then build toward P1's vision Sprint 5+. P1 is the north star, P2/P3 inform the immediate roadmap. |
| P4 (parent activation first) vs. P3 (child experience first) | **Child is upstream**: Fix child experience (O1, O2, O3) → generates data → feeds parent reports (O6) → enables P4's hook loop. Not either/or — just sequenced correctly. |
| P5 (10 pillars in parallel) vs. reality (limited capacity) | **Focus 3 pillars**: Core AI (STT), Learning Design (Starter + Embedded English), Onboarding. Cut/defer the other 7 for H1. |
| P2 (Buddy Talk = learning reinforcement) vs. P1 (Buddy Talk = emotional bond) | **Both, via Embedded English in Talk (S2.5)**: Learning woven into fun conversations. Not "homework review" and not "pure chat" — it's the bridge. |
| PTL (parent creates lessons) vs. O9 (child resists lesson-pushing) | **Connect the handoff**: Robot announces lessons as fun quests (S8.1), XP rewards (S8.2), shorter sessions (S8.4). Parent creates; Pika delivers as play, not homework. |

---

*This OST should be reviewed and updated weekly as experiment results come in. Kill solutions that don't validate. Explore new branches as you learn.*

*Built using the Opportunity Solution Tree framework (Teresa Torres) + Opportunity Scoring (Dan Olsen) + ICE prioritization. Incorporates evidence from Q1 Customer Feedback Report (150+ responses), 5 team proposals (P1–P5), and Photo-to-Lesson performance data (629 requests, 5-day production).*
