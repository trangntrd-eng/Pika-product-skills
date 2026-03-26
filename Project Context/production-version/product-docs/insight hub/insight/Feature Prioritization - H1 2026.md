# Feature Prioritization — H1 2026

> Framework: ICE Scoring (Impact × Confidence × Ease)
> Impact derived from Opportunity Score × estimated user reach
> Sources: Combined OST, Assumption Analysis (5 proposals), Q1 Customer Feedback Report, PTL Performance Report
> **Updated**: 2026-03-24 — incorporated Learn system meeting notes (3-tier content build, auto-gen templates, adaptive orchestrator, pronunciation correction tracks, B2B path building)
> Date: 2026-03-24

---

## Product Objective & Success Metrics

**Goal**: Increase 30-day subscription renewal from 15% → 35% by July 1, 2026 (120k VND/month)

| KR | Current | Target |
|----|---------|--------|
| KR1 Retention: Active ≥15 days / 30 days | 24% | 80% |
| KR2 Value: ≥2 quality sessions / active day | Unknown | 2/day |
| KR3 Qualified Lead: % parents willing to renew | Unknown | 60% |
| KR4 Close Rate: % leads who actually renew | Unknown | 60% |

**User base**: 5,426 registered parents, ~2,000 WAU (36.8%), ~210 PTL users

---

## Complete Feature Backlog (28 items)

All features from the Combined OST, team proposals (P1–P5), and PTL report, scored on a 1–10 scale for each ICE dimension.

### Scoring Methodology

- **Impact** (1–10): Opportunity Score × reach × KR alignment. "How much does this move the 15% → 35% needle?"
- **Confidence** (1–10): Evidence strength. Based on: # of data sources confirming, assumption risk level from the analysis, existing behavioral data.
- **Ease** (1–10): Inverse of effort. 10 = ship in days, 1 = multi-month build with dependencies.

**ICE Score = Impact × Confidence × Ease / 10** (normalized to 0–100 scale)

---

## ICE Scoring Table

> **Update from Learn system meeting notes**: 3 items rescored, 4 new items added (marked 🆕). Key changes:
> - S2.1 (Starter level) Ease 5→7: auto-gen template system means content can be generated faster, not all hand-built
> - S2.3 (Adaptive) rescoped as Adaptive Orchestrator with broader mandate (school alignment, B2B paths)
> - S1.2 (ASR lenient) split: pronunciation correction now has 2 explicit tracks (expression fix + pronunciation auto-catch)
> - New items: auto-gen lesson templates, pronunciation auto-catch extension, orchestrator for school alignment, B2B path builder

| Rank | ID | Feature | Opp. | Impact | Conf. | Ease | ICE | KR | Sprint |
|------|-----|---------|------|--------|-------|------|-----|-----|--------|
| 1 | S10.1 | **PTL safety hard-gate** — abort pipeline on UNSAFE_CONTENT | O10 | 10 | 10 | 9 | **90** | Trust | 0 |
| 2 | S1.4 | **ASR graceful failure responses** — stop "ù tai" loop, show what Pika heard, offer options after 2 fails | O1 | 8 | 9 | 8 | **58** | KR1,2 | 1 |
| 3 | S8.2 | **PTL XP scoring** — connect XP system for Photo-to-Lesson (currently 0 XP) | O8 | 7 | 9 | 9 | **57** | KR2 | 0 |
| 4 | S2.2 | **Fun-first onboarding (Days 1-3)** — games + Vietnamese chat + easy words, no structured lessons until Day 4 | O2 | 10 | 8 | 7 | **56** | KR1,2 | 1 |
| 5 | S8.1 | **PTL robot notification** — Pika announces new lesson when child next interacts | O8 | 7 | 8 | 9 | **50** | KR1,2 | 1 |
| 🆕6 | S2.1a | **Auto-gen Starter lessons via template system** — use "hệ tự gen" to rapidly produce Starter-level content (single-word vocab, games, drills) from templates instead of hand-building all 10 | O2 | 10 | 7 | 7 | **49** | KR1,2 | 1-2 |
| 7 | S1.2 | **ASR lenient mode for beginners** — lower confidence threshold for Pre-A1/Starter | O1 | 9 | 8 | 6 | **43** | KR1,2 | 1 |
| 8 | S8.3 | **PTL completion notification** — push to parent when child finishes/doesn't finish lesson | O8 | 6 | 8 | 9 | **43** | KR3 | 1 |
| 9 | S10.2 | **PTL image hash caching** — block retries of images previously flagged UNSAFE | O10 | 8 | 9 | 6 | **43** | Trust | 0 |
| 10 | — | **Voice-command sleep mode** — "Pika ngủ đi" + auto-sleep after 3-4 unanswered prompts | O4 | 6 | 9 | 8 | **43** | KR1 | 1 |
| 11 | — | **WiFi credential persistence** — save multiple networks, auto-reconnect on restart | O7 | 5 | 9 | 8 | **36** | KR1 | 1 |
| 12 | S2.1 | **Starter level (10 lessons)** — single-word vocab, Vietnamese scaffolding, daily-life topics. ⬆️ Ease 5→7: auto-gen templates accelerate production (3 hand-built + 7 auto-gen) | O2 | 10 | 8 | 7 | **56** ⬆️ | KR1,2 | 2 |
| 13 | S6.1 | **Daily conversation summary** — push notification to parent with 3-line summary | O6 | 8 | 7 | 7 | **39** | KR3 | 2 |
| 🆕14 | S1.6 | **Pronunciation auto-catch extension** — extend auto-detection of pronunciation errors to more use cases (beyond current fallback/silent/idk). Auto-correct in Talk mode, not just Learn | O1 | 7 | 7 | 6 | **29** | KR2 | 2 |
| 15 | S9.1 | **Fun-first default mode** — change Pika greeting from lesson-oriented to play-oriented | O9 | 6 | 7 | 8 | **34** | KR1 | 2 |
| 16 | S6.2 | **Weekly learning report** — vocab progress, pronunciation, time spent, topics | O6 | 9 | 7 | 5 | **32** | KR3 | 3 |
| 17 | S1.5 | **Pronunciation energy bar** — visual accuracy feedback replacing binary right/wrong | O1 | 6 | 6 | 8 | **29** | KR2 | 2 |
| 18 | S2.4 | **Assessment test** — place child at correct level before first lesson | O2 | 8 | 6 | 6 | **29** | KR1 | 2 |
| 19 | S3.1 | **Proactive engagement engine** — Pika initiates with personalized hooks at scheduled times | O3 | 9 | 6 | 5 | **27** | KR1 | 2 |
| 20 | S2.5 | **Embedded English in Talk** — weave vocab/grammar into fun conversations instead of drills | O2,O9 | 9 | 5 | 5 | **23** | KR1,2 | 3 |
| 21 | S8.4 | **Shorter PTL lessons** — test 5/10/15 min variants | O8 | 6 | 5 | 7 | **21** | KR2 | 2 |
| 22 | S3.2 | **Struggle-to-fun fallback** — detect disengagement → auto-switch to games/chat | O3 | 8 | 5 | 5 | **20** | KR1 | 3 |
| 23 | S10.3 | **Whitelist educational safety topics** — refine UNSAFE categories | O10 | 4 | 7 | 7 | **20** | Trust | 2 |
| 24 | S1.1 | **Child-voice ASR retraining** — fine-tune STT on Vietnamese children's voice data | O1 | 10 | 6 | 3 | **18** | KR1,2 | 3 |
| 25 | S3.3 | **Parent async missions** — parent sets daily quest, child completes independently | O3 | 7 | 5 | 5 | **18** | KR1,2 | 4 |
| 26 | S6.3 | **PTL conversation reports** — connect conversation_reports for PTL sessions | O6 | 6 | 6 | 5 | **18** | KR3 | 3 |
| 🆕27 | S2.6 | **Adaptive Orchestrator — school alignment** — orchestrator biết user đang học gì trên trường → Pika củng cố kiến thức đó. Giải quyết "user đang học ngoài cái điều hướng" | O2,O3 | 8 | 4 | 3 | **10** | KR1,2 | 4+ |
| 28 | S8.5 | **PTL "Learn together" mode** — parent starts lesson with child present | O8 | 5 | 5 | 5 | **13** | KR2 | 3 |
| 29 | S1.3 | **Regional accent ASR profiles** — Southern/Central Vietnamese support | O1 | 7 | 5 | 3 | **11** | KR1 | 4 |
| 30 | S9.3 | **Pika personality moments** — random fun facts, silly songs, curiosity triggers | O9 | 4 | 4 | 7 | **11** | KR1 | 4 |
| 🆕31 | S2.7 | **B2B path builder** — cho phép đối tác (trung tâm tiếng Anh, trường học) tự build lộ trình trên Pika | O2 | 7 | 3 | 2 | **4** | KR3+ | H2 |
| 32 | S2.3 | **Adaptive difficulty engine (full)** — auto-adjust content based on child performance. Rescoped: phần này nằm trong Adaptive Orchestrator, bao gồm cả scale cho trình độ khác + school alignment | O2 | 8 | 3 | 3 | **7** | KR2 | 4+ |

---

## Top 10 Recommendations

### #1: PTL Safety Hard-Gate (S10.1) — ICE: 90

**Ship today. Non-negotiable.**

11 images flagged UNSAFE still generated lessons, including 3 high-risk cases (knife image, reproductive terminology reaching children). The vision screener detects the problem but the pipeline ignores it.

- **Impact**: 10 — Legal/trust risk. One public incident could damage the brand irreparably.
- **Confidence**: 10 — We have the 11 cases documented with trace IDs.
- **Ease**: 9 — Single conditional gate in the pipeline. If `UNSAFE_CONTENT`, return error.
- **Trade-off**: None. This is a bug fix, not a feature trade-off.

---

### #2: ASR Graceful Failure Responses (S1.4) — ICE: 58

**Sprint 1. Highest ICE among real features.**

When Pika can't understand, it repeats "ù tai" endlessly. Children get frustrated and quit. This doesn't fix ASR accuracy but dramatically improves the failure experience while deeper ASR work (S1.1, S1.2) progresses.

- **Impact**: 8 — Reduces the #1 frustration driver. 35+ Q1 mentions. Every churned user reports this.
- **Confidence**: 9 — All 5 proposals and all data sources confirm. No assumption risk.
- **Ease**: 8 — Prompt engineering + UX change. Show what Pika heard on screen. Offer 2-3 options after failures. No model retraining needed.
- **Trade-off**: Doesn't fix the root cause (ASR accuracy). But buys time while S1.1/S1.2 are built. Children will still encounter misrecognition, but the experience will be frustrating instead of infuriating.

---

### #3: PTL XP Scoring (S8.2) — ICE: 57

**Sprint 0. Quick win on a live feature.**

PTL lessons award 0 XP. Children have no motivation to complete. 210 parents are actively creating lessons — the supply side works. Fix the demand side.

- **Impact**: 7 — 471 lessons delivered with only 14.2% completion. XP is a proven motivator (check-up data: kids love earning stars and diamonds). Even a modest improvement (14% → 25%) means ~50 more completed lessons/week.
- **Confidence**: 9 — XP system exists for standard lessons. PTL just isn't connected to it.
- **Ease**: 9 — Integration work: hook PTL lesson completion into existing XP system. No new design.
- **Trade-off**: Extrinsic motivation (XP) vs. intrinsic (genuine interest). But at 14.2% completion, we need any lever. Can be refined later.

---

### #4: Fun-First Onboarding Days 1-3 (S2.2) — ICE: 56

**Sprint 1-2. Highest-impact feature for KR1 (Retention).**

The "excitement cliff": children love Pika on Day 1-2 (Vietnamese chat, games), then hit a wall on Day 3-4 when structured English lessons begin. Most D7 churn happens here. Delay structured learning until the child has formed a Pika habit.

- **Impact**: 10 — Directly attacks the #1 retention bottleneck. If D7 retention improves by even 15pp, the entire funnel benefits.
- **Confidence**: 8 — Confirmed by Q1 data (30+ mentions), churn interviews (P3), and P2's D1→D7 observation. The evidence is strong but the specific "Days 1-3 = fun only" solution hasn't been tested.
- **Ease**: 7 — Requires: (a) redesigning the first-week todo/orchestration, (b) creating fun-first content for Days 1-3, (c) adjusting when Learn module appears. Medium effort across content + engineering.
- **Trade-off**: Parents bought Pika for English learning. Delaying English to Day 4 may frustrate parents who expect immediate educational value. Mitigate with: parent notification explaining the approach ("Pika đang làm quen với con — bài học tiếng Anh sẽ bắt đầu từ ngày 4").

---

### #5: PTL Robot Notification (S8.1) — ICE: 50

**Sprint 1. Low-effort, high-value for PTL.**

When a parent assigns a PTL lesson, it silently arrives on the robot. The child doesn't know. 30.4% of sessions end in ≤4 user turns — possibly because the child stumbled into a lesson they didn't expect.

- **Impact**: 7 — Bridges the parent→child handoff gap. If even half of the 30.4% "ghost sessions" convert to real engagement, PTL completion jumps significantly.
- **Confidence**: 8 — The handoff gap is clearly documented in PTL data. Re-assigned lessons complete at 1.6× (24.5% vs 15.3%), proving that parent involvement at the right moment helps.
- **Ease**: 9 — Pika already announces Learn lessons. Extend to PTL: "Mẹ vừa gửi cho bạn một bài mới! Mình thử nhé?"
- **Trade-off**: Child may dismiss the notification. But a dismissed notification is no worse than the current silent delivery.

---

### #6: ASR Lenient Mode for Beginners (S1.2) — ICE: 43

**Sprint 1-2. The real ASR fix for beginners (while full retraining is in progress).**

Lower the ASR confidence threshold specifically for Pre-A1/Starter level. Accept approximate pronunciation. Stop marking correct answers as wrong.

- **Impact**: 9 — Directly addresses the #1 churn driver for the highest-risk segment (Pre-A1). "Trẻ trả lời đúng nhưng Pika cứ bảo sai" — this destroys trust and makes children call Pika "ngu."
- **Confidence**: 8 — Strong signal from Q1, P3, and P2. The Assumption Analysis flagged one dependency: first diagnose whether failures are "heard wrong" vs. "scored wrong" (E1.D). If mostly "heard wrong," lenient mode alone won't suffice.
- **Ease**: 6 — Requires: (a) ASR diagnostic first (E1.D), (b) threshold tuning per level, (c) QA to ensure false positives stay ≤15%. Medium engineering effort.
- **Trade-off**: Leniency may mask real pronunciation errors. Mitigate: lenient mode only for Starter/Pre-A1. A1+ keeps normal thresholds. Parents can toggle in app.

---

### #7: PTL Completion Notification to Parent (S8.3) — ICE: 43

**Sprint 1. Starts the parent feedback loop.**

When the child completes (or abandons) a PTL lesson, push a notification to the parent. "Con vừa hoàn thành bài học về [topic]!" This is the minimum viable version of P4's hook loop.

- **Impact**: 6 — Directly drives KR3 (parent perceived value). PTL notification open rate is 38.6% — parents do read pushes. Knowing their child completed a lesson they created is the simplest "proof of value."
- **Confidence**: 8 — The notification infrastructure exists. The behavioral loop (parent assigns → child completes → parent sees result) is P4's core thesis, and this is the cheapest test of it.
- **Ease**: 9 — Trigger push notification on PTL lesson completion event. Template: "Con vừa hoàn thành bài [title]! Xem kết quả →"
- **Trade-off**: If child rarely completes (current 14.2%), the parent mostly gets "chưa hoàn thành" notifications — which could be discouraging. Ship alongside S8.2 (XP) and S8.1 (robot notification) to improve completion first.

---

### #8: Voice-Command Sleep Mode — ICE: 43

**Sprint 1. Quick win, eliminates a widespread annoyance.**

15+ Q1 mentions. Pika keeps talking after goodbye, forces physical button press. Not addressed in any team proposal — an easy gap to close.

- **Impact**: 6 — Doesn't directly drive retention, but eliminates a friction that makes parents and children dislike Pika. Every frustrated bedtime interaction is a small withdrawal from the trust bank.
- **Confidence**: 9 — Universally reported across Facebook, survey, and interview data. Zero assumption risk.
- **Ease**: 8 — Wake-word detection already exists. Add sleep trigger: "Pika ngủ đi" / "Goodbye Pika." Auto-sleep after 3-4 unanswered prompts.
- **Trade-off**: None meaningful. Ship it.

---

### #9: PTL Image Hash Caching (S10.2) — ICE: 43

**Sprint 0. Safety completion.**

Same image flagged UNSAFE on try 1 passes on retry (non-deterministic screening). Cache the hash — if flagged once, all retries blocked.

- **Impact**: 8 — Closes the safety bypass loophole found in PTL data. 4 of 11 unsafe cases involved retries that bypassed screening.
- **Confidence**: 9 — Root cause documented in PTL report.
- **Ease**: 6 — Requires image hashing + cache lookup before vision screening. Moderate engineering.
- **Trade-off**: May occasionally block a legitimate image that was incorrectly flagged on first attempt. Acceptable — err on the side of child safety.

---

### #10: WiFi Credential Persistence — ICE: 36

**Sprint 1. Quick quality-of-life fix.**

12+ Q1 mentions. Pika forgets WiFi after restart/unplug. Parents must re-enter WiFi password every time. Not in any proposal.

- **Impact**: 5 — Reduces daily friction. Especially important for families who use Pika in multiple locations (car, grandparent's house).
- **Confidence**: 9 — Clearly documented. Pure engineering fix.
- **Ease**: 8 — Store WiFi credentials in persistent storage. Standard IoT practice.
- **Trade-off**: None. Ship it.

---

## Features 11-15: Next Sprint

| Rank | Feature | ICE | Rationale |
|------|---------|-----|-----------|
| 11 | **Starter level — 10 lessons** (S2.1) | 40 | Highest-impact content work. Serves the segment with the worst retention (Pre-A1 beginners). Paired with S2.2 (fun-first onboarding). Medium effort because it's 10 new lessons + content design. |
| 12 | **Daily conversation summary** (S6.1) | 39 | Minimal viable "proof of value" for parents. Push notification after each day. Depends on conversation data actually being generated (currently null for PTL). Infrastructure work needed first. |
| 13 | **Fun-first default mode** (S9.1) | 34 | Change Pika's greeting from lesson-oriented to play-oriented. Low effort, meaningful perception shift. Directly addresses P3's "tool vs friend" insight. |
| 14 | **Weekly learning report** (S6.2) | 32 | The KR3 killer feature — parents who see weekly progress are more likely to renew. Must ship before June to influence July 1 renewal decisions. Higher effort than daily summary (needs aggregation, trends, vocab tracking). |
| 15 | **Pronunciation energy bar** (S1.5) | 29 | Good UX improvement from P2. Low effort. Replaces confusing binary feedback with visual gradient. Needs usability test with children first (Assumption U4). |

---

## What Was Deprioritized (with reasoning)

### Deferred to H2 (after July 1 renewal target)

| Feature | Source | ICE | Why Not Now |
|---------|--------|-----|-------------|
| Child-voice ASR retraining (S1.1) | OST | 18 | Very high impact but very high effort. Requires voice data collection program + model retraining. Ship lenient mode (S1.2) as interim. Start data collection now, retrain in H2. |
| Regional accent profiles (S1.3) | OST | 11 | High effort. Lenient mode partially addresses this. Full accent support is a multi-month project. |
| Adaptive Orchestrator full (S2.3 + S2.6) | P5, Meeting | 7-10 | Meeting notes rescope adaptive as a larger system: school alignment + B2B paths + multi-level scaling. This is the right vision but requires: (a) content auto-gen pipeline stable, (b) orchestrator architecture, (c) school curriculum data. Build foundations now (auto-gen templates), full orchestrator in H2. |
| B2B path builder (S2.7) | Meeting | 4 | "Cho phép các bên B2B tự build lộ trình." Strategic but H2+. Requires stable orchestrator + API layer + partner onboarding. Zero urgency for consumer renewal. |
| Korean/Chinese language (P5) | P5 | — | Zero validated demand. English isn't working. Cut entirely for H1. |
| STEM/Social Sciences expansion (P1, P5) | P1, P5 | — | Dilutes English identity before it's solid. P1 correctly identifies English as "anchor value" — anchor it first. |
| Adaptive Influence Framework (P1) | P1 | — | High feasibility risk (F2). LLM behavior influencing children requires safety guardrails that don't exist. No parent demand signal. |
| Badge system (P4, P5) | P4, P5 | — | Gamification amplifies a working product. At 24% D15 retention, the product isn't working well enough for badges to matter. Add when D7 retention >60%. |
| Ranking/leaderboard (P5) | P5 | — | May discourage Pre-A1 beginners (lowest-scoring, highest-churn segment). Only viable for A1+ after beginner experience is fixed. |
| Parent real-world rewards (P4) | P4 | — | Assumption V17: parents barely use existing app. Too complex. |
| Full app redesign/refactor (P4) | P4 | — | Massive effort. Ship targeted improvements (notifications, reports) first. Redesign when you know what parents actually use. |
| Todo list customization (P5) | P5 | — | Assumption U5 likely wrong. Validate whether todo flow is actually a churn driver before building. |
| Virtual gift exchange (P5) | P5 | — | Unclear value, no demand signal. RnD item with no evidence. |
| Functional dependence strategy (P1) | P1 | — | Right vision, wrong timing. Children must survive Week 1 first. Phase into H2 once D7 retention is healthy. |

### Conditional (validate before committing)

| Feature | Condition | Validation Method |
|---------|-----------|------------------|
| Embedded English in Talk (S2.5) | High potential but medium confidence. Validate that learning embedded in conversation produces real vocab retention, not just fun chat | A/B test (E2.5): Compare vocab retention in Embedded Talk vs. standard Learn mode. Must retain ≥80% of Learn mode's retention. |
| Proactive engagement engine (S3.1) | Medium confidence. May feel annoying instead of engaging if poorly designed | User test with 10 families first. Kill if children ignore or dismiss proactive prompts >50% of the time. |
| Parent async missions (S3.3) | Depends on whether parents will actually configure missions | Check: if PTL usage (parent-assigns model) stays above 100 users/week, then parents will configure missions too. If PTL usage drops, they won't. |
| Assessment test (S2.4) | Depends on whether incorrect level placement is actually a churn driver | Analyze: do children placed at wrong levels (Pre-A1 kids struggling with A1 content) churn faster than correctly-placed children? If no correlation, deprioritize. |

---

## Sprint Plan Summary

```
SPRINT 0 (This week)          SPRINT 1-2 (Apr W1-W2)         SPRINT 3-4 (Apr W3 – May W1)
─────────────────────          ────────────────────────         ────────────────────────────
#1  Safety hard-gate           #2  ASR failure responses       #11 Starter level (10 lessons)
#3  PTL XP scoring             #4  Fun-first onboarding        #12 Daily conversation summary
#9  Image hash caching         #5  PTL robot notification      #14 Weekly learning report
    ASR diagnostic (E1.D)      #6  ASR lenient mode            #15 Pronunciation energy bar
    D1→D7 diagnostic           #7  PTL completion notif.           Assessment test (S2.4)
                               #8  Sleep mode voice cmd            Proactive engine (S3.1)
                               #10 WiFi persistence
                               #13 Fun-first default mode

SPRINT 5-6 (May W2 – Jun W1)  SPRINT 7-8 (June)
─────────────────────────────  ──────────────────
Embedded English in Talk       Regional accent ASR
(if validated by E2.5)         Adaptive difficulty (if validated)
Child-voice ASR retraining     Parent async missions
Struggle-to-fun fallback       Pika personality moments
PTL conversation reports
```

---

## The Critical Chain (unchanged)

```
Fix ASR → Children can learn → Learning generates data → Data feeds parent reports → Parents see value → Parents renew
```

**If you can only do 3 things before July 1:**
1. Fix ASR (S1.2 lenient mode + S1.4 graceful failures)
2. Fix the first week (S2.2 fun-first onboarding + S2.1 Starter level)
3. Ship parent reports (S6.1 daily summary + S6.2 weekly report)

Everything else improves the experience. These three are the minimum to move from 15% → 35%.

---

---

## Update: Learn System Meeting Notes — Impact Analysis

### Tóm tắt meeting notes

Team managers đề cập 4 hướng cho Core Value - Learn:

**(1) Build bài — 3 hệ thống song song:**
- Hệ Verdette: ít, chất lượng cao, hand-crafted
- Hệ team tự build: tự động hoá là chính
- Hệ tự gen: có template, khi cần thì gen thêm (VD: luyện phát âm)

**(2) Sửa lỗi — 2 track:**
- Sửa diễn đạt → cho nhóm full tiếng Anh
- Sửa phát âm → extend các use case tự động bắt

**(3) Adaptive — qua Orchestrator:**
- Giải quyết học song song với trường lớp
- Scale cho các trình độ khác
- Cho phép B2B tự build lộ trình

**(4) Vấn đề được nhận diện:**
- Không adaptive
- Tốc độ build bài mới chưa nhanh
- User có thể đang học ngoài điều hướng

### Điều gì thay đổi trong prioritization?

#### ✅ S2.1 (Starter Level) tăng Ease: 5 → 7, ICE: 40 → 56

**Trước**: Ước tính 10 bài Starter cần hand-build → 2-3 tuần content production. Medium effort.
**Sau meeting**: "Hệ tự gen" cho phép gen bài từ template. Approach mới: 3 bài hand-craft (Verdette quality) + 7 bài auto-gen từ template. Production time giảm ~50%.

**Implication**: S2.1 nhảy từ rank #11 lên top 5. Fun-first onboarding (S2.2) + Starter level (S2.1) giờ có thể ship cùng sprint vì content production nhanh hơn.

#### 🆕 S2.1a (Auto-Gen Starter via Templates) — ICE: 49, NEW

Tách riêng vì đây là **capability mới** không chỉ phục vụ Starter mà còn là foundation cho:
- Pronunciation drill auto-gen ("khi cần thì gen thêm")
- Scale content cho các trình độ khác (A1, A2, B1)
- Cuối cùng: B2B path builder

**Đây là infrastructure investment, không chỉ 1 feature.** Nếu auto-gen template system hoạt động tốt, nó giải quyết vấn đề "tốc độ build bài mới chưa nhanh" — bottleneck mà meeting notes nhận diện.

#### 🆕 S1.6 (Pronunciation Auto-Catch Extension) — ICE: 29, NEW

Meeting notes tách rõ 2 track sửa lỗi:
- **Sửa diễn đạt**: cho nhóm full English → đây là chức năng hiện tại, cần refine
- **Sửa phát âm**: extend auto-detect → đây là mới, mở rộng khả năng tự động bắt lỗi phát âm ra nhiều use case hơn (Talk mode, not just Learn mode)

Đây quan trọng vì kết hợp với S2.5 (Embedded English in Talk): nếu trẻ học tiếng Anh qua conversation, Pika cần sửa phát âm trong conversation, không chỉ trong bài học.

#### 🆕 S2.6 (Adaptive Orchestrator — School Alignment) — ICE: 10, H2

Meeting notes cho thấy tầm nhìn adaptive rộng hơn feature S2.3 cũ:
- Không chỉ "adjust difficulty" mà là **biết user đang học gì trên trường → củng cố và thiết kế bài dựa trên kiến thức trên trường**
- "User có thể sẽ đang học ngoài cái điều hướng" = trẻ không follow lộ trình Pika, có thể đang follow lộ trình trường

**Implication**: Adaptive Orchestrator giải quyết root cause tốt hơn Adaptive Difficulty Engine đơn thuần. Nhưng complexity cũng cao hơn nhiều: cần input curriculum data trường → map với Pika content → adjust orchestrator.

**Recommendation**: H2 initiative. Trong H1: dùng PTL (Photo-to-Lesson) như workaround — ba mẹ chụp bài trên lớp → Pika tạo bài học bổ trợ. PTL đã chứng minh ba mẹ muốn điều này (53.2% organic usage).

#### 🆕 S2.7 (B2B Path Builder) — ICE: 4, H2+

"Cho phép các bên B2B tự build lộ trình" là strategic opportunity nhưng không phục vụ H1 renewal goal. Cần:
- Stable orchestrator
- API/SDK layer
- Partner onboarding process
- Content QA for partner-created paths

**Recommendation**: Park for H2+. Nhưng bắt đầu conversation với 2-3 trung tâm tiếng Anh tiềm năng để validate demand. Customer check-up data đã cho thấy nhiều phụ huynh muốn "chương trình học tiếng Anh kết hợp Pika với giáo viên."

#### S2.3 (Adaptive Difficulty) — rescoped, vẫn H2

Giờ S2.3 nằm trong S2.6 (Adaptive Orchestrator). Không còn là standalone feature mà là một phần của hệ thống lớn hơn. ICE vẫn thấp cho H1.

### Tóm tắt thay đổi

| Item | Before | After | Change |
|------|--------|-------|--------|
| S2.1 Starter Level | ICE 40, Sprint 2 | ICE 56, Sprint 1-2 | ⬆️ **Tăng priority** — auto-gen templates giảm effort |
| S2.1a Auto-Gen Templates | N/A | ICE 49, Sprint 1-2 | 🆕 **Mới** — infrastructure cho content scaling |
| S1.6 Pronunciation Auto-Catch | N/A | ICE 29, Sprint 2 | 🆕 **Mới** — extend phát âm ra Talk mode |
| S2.6 Adaptive Orchestrator | N/A | ICE 10, H2 | 🆕 **Mới** — broader than S2.3, school alignment |
| S2.7 B2B Path Builder | N/A | ICE 4, H2+ | 🆕 **Mới** — strategic, not H1 priority |
| S2.3 Adaptive (old) | ICE 7, Sprint 4 | ICE 7, H2 (part of S2.6) | Rescoped thành subset of orchestrator |

### Revised Top 5 for H1 (incorporating meeting notes)

| # | Feature | ICE | Thay đổi |
|---|---------|-----|----------|
| 1 | PTL safety hard-gate (S10.1) | 90 | Không đổi |
| 2 | ASR graceful failures (S1.4) | 58 | Không đổi |
| 3 | PTL XP scoring (S8.2) | 57 | Không đổi |
| 4 | Fun-first onboarding (S2.2) | 56 | Không đổi |
| **5** | **Starter level (S2.1)** | **56** ⬆️ | **Tăng từ #11 lên #5** — auto-gen templates giảm effort, giờ ngang ICE với S2.2 và nên ship cùng |

**S2.1 + S2.1a (auto-gen templates) nên ship cùng sprint vì chúng reinforce nhau**: templates là means, Starter content là ends. Build template system → gen Starter lessons → validate → use same system để scale A1/A2/B1 content sau.

---

*Prioritized using ICE framework (Impact × Confidence × Ease). Impact incorporates Opportunity Score (Dan Olsen) and KR alignment. Confidence reflects evidence strength from Q1 feedback (150+ responses), 5 team proposals, churn interviews, PTL production data (629 requests), and Learn system meeting notes.*
