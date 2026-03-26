# Opportunity Solution Tree — H1 2026

> Based on Teresa Torres' Continuous Discovery Habits framework
> Built from: H1 2026 Goals + Q1 Customer Feedback Report + Pika Value Direction

---

## Desired Outcome

**Increase 30-day subscription renewal rate from 15% → 35% by July 1, 2026 (at 120k VND/month)**

### Supporting Key Results

| KR | Current | Target |
|----|---------|--------|
| **Retention**: Users active ≥15 days within first 30 days | 24% | 80% |
| **Value**: ≥2 quality sessions/active day (delivers core value per product vision) | Unknown | 2/day |
| **Qualified Lead**: % parents willing to renew | Unknown | 60% |
| **Close Rate**: % qualified leads who actually renew | Unknown | 60% |

### What "Quality Session" Means (per Pika Value Direction)
A session that delivers value from at least one core layer:
- **Layer A**: English speaking practice with learning loop, or academic assistance
- **Layer B**: Daily life utility (reminders, Q&A, habit building)
- **Layer C**: Value imprint (emotional intelligence, problem-solving embedded in conversation)
- **Layer D**: Emotional attachment (meaningful personal chat, games, check-in)

---

## Opportunity Map

Opportunities are framed from the customer's perspective, sourced from Q1 feedback data (150+ responses across 4 channels). Scored using **Opportunity Score = Importance × (1 − Satisfaction)**, normalized 0–1.

| # | Opportunity | Importance | Satisfaction | Opp. Score | Evidence |
|---|------------|------------|--------------|------------|----------|
| **O1** | "Con nói mà Pika không hiểu, phải nói đi nói lại" — Child's speech isn't recognized | 1.0 | 0.2 | **0.80** | 35+ mentions, #1 theme, confirmed by churn data |
| **O2** | "Bài học khó quá, con chưa biết gì về tiếng Anh mà phải nói cả câu" — Beginner content is too hard | 0.95 | 0.15 | **0.81** | 30+ mentions, #1 churn trigger, "excitement cliff" at Day 3-4 |
| **O3** | "Con chỉ dùng khi bố mẹ ngồi cạnh, bận là thôi" — Child can't engage independently | 0.9 | 0.25 | **0.68** | Churn interviews, 6+ mentions, key hidden churn driver |
| **O4** | "Bảo Pika ngủ mà Pika cứ nói mãi" — Can't stop Pika / no sleep mode | 0.7 | 0.1 | **0.63** | 15+ mentions, frustrates bedtime routine |
| **O5** | "Muốn tự thêm từ vựng cho con học" — Parents want to customize learning | 0.8 | 0.05 | **0.76** | 20+ mentions, power users requesting |
| **O6** | "Không biết con học gì, nói gì với Pika cả ngày" — Parents lack visibility into child's learning | 0.85 | 0.15 | **0.72** | 12+ mentions, parent app UX complaints, check-up data |
| **O7** | "WiFi phải kết nối lại mỗi lần tắt mở" — Technical friction breaks daily habit | 0.6 | 0.1 | **0.54** | 12+ mentions, contributes to churn |

### Prioritized Opportunities (Top 3 for H1)

Based on Opportunity Score × alignment with KRs:

1. **O2: Beginner content too hard** (Score: 0.81) → Directly drives KR1 (Retention) and KR2 (Quality sessions). The "excitement cliff" at Day 3-4 is where most users are lost. Fixing this extends the engagement window.

2. **O1: Speech recognition failures** (Score: 0.80) → Blocks KR2 (Quality sessions). Even good content fails if Pika can't understand the child. Directly causes frustration → churn.

3. **O3: Child can't engage independently** (Score: 0.68) → Critical for KR1 (Retention). If usage depends on parent presence, daily active days will never reach 80%. This is the gatekeeper to habit formation (Layer D value).

**Secondary** (pursue if capacity allows):
- O6: Parent visibility (drives KR3 — Qualified Lead, because parents who see progress are more likely to renew)
- O5: Custom content (drives KR2 — Value, by enabling parents to align Pika with school curriculum)

---

## Solutions & Experiments

### O2: Beginner Content Too Hard

> "câu khá dài và khó với bé chưa có trình độ — nên bắt đầu bằng book, pen, ball"
> "Bài học pre-A1 khó với trẻ, cháu nản" (churned user)

#### Solutions

| ID | Solution | Perspective | Effort | Impact |
|----|----------|------------|--------|--------|
| S2.1 | **"Starter" level below Pre-A1**: Single-word vocabulary from daily life (colors, animals, food, school items). Vietnamese scaffolding before English. Progress: word → phrase → short sentence over weeks | PM + Content | Medium | Very High |
| S2.2 | **Gentle first-week onboarding flow**: Days 1-3 = primarily fun (Vietnamese chat, games, easy English words). Days 4-7 = introduce structured lessons gradually. No "hard English" until child has formed a Pika habit | PM + Design | Medium | Very High |
| S2.3 | **Adaptive difficulty engine**: Pika detects when child is struggling (silence, repeated failures, Vietnamese fallback) and auto-downgrades to simpler content — shorter words, more Vietnamese hints, game breaks | Engineering | High | High |
| S2.4 | **Bilingual stepping stones**: In song ngữ mode, start with Vietnamese sentence → single English keyword (not full translation). Gradually increase English ratio as child progresses | Content + PM | Low | Medium |

#### Experiments

| Exp | Hypothesis | Method | Metric | Threshold |
|-----|-----------|--------|--------|-----------|
| E2.1 | If we add a Starter level with single-word vocabulary, Pre-A1 children will complete ≥5 lessons in the first week (vs. current ~2) | Build 10-lesson Starter module. A/B test with new Pre-A1 users over 2 weeks | Lessons completed in Week 1 + Day 7 retention | ≥5 lessons; D7 retention +15pp |
| E2.2 | If Days 1-3 are fun-first (games + Vietnamese chat + easy words), 7-day retention will increase | Modify onboarding flow for new cohort. Compare D7 active rate vs. control | D7 active rate | Current → +20pp (from ~50% to 70% est.) |
| E2.3 | If Pika auto-simplifies when detecting child struggle, session length will increase | Prototype struggle detection (3+ failures → switch to easier content). Test with 50 users | Avg session length + completion rate | Session length +30%, completion +20% |

---

### O1: Speech Recognition Failures

> "Pika nghe rất tệ" / "giọng miền Nam Pika nghe ko rõ" / "trẻ chê Pika ngu"
> "trẻ trả lời đúng nhưng Pika cứ bảo sai" (churned user)

#### Solutions

| ID | Solution | Perspective | Effort | Impact |
|----|----------|------------|--------|--------|
| S1.1 | **Child-voice ASR tuning**: Fine-tune speech recognition model on Vietnamese children's voice data (ages 5-12). Collect opt-in voice samples from existing users for training | Engineering | High | Very High |
| S1.2 | **Lenient recognition mode for beginners**: Lower confidence threshold for Pre-A1/Starter. Accept approximate pronunciation. Only flag pronunciation when child is at A1+ and specifically in "practice mode" | Engineering | Medium | High |
| S1.3 | **Regional accent profiles**: Add Southern/Central Vietnamese accent support. Let parents set regional preference in app. Adjust phoneme mapping accordingly | Engineering | High | High |
| S1.4 | **Graceful failure responses**: When Pika doesn't understand, vary responses (stop "ù tai" repetition). Show what Pika heard on screen so child can adjust. After 2 failures, offer options: "Bạn muốn nói X hay Y?" | PM + Engineering | Low | Medium |

#### Experiments

| Exp | Hypothesis | Method | Metric | Threshold |
|-----|-----------|--------|--------|-----------|
| E1.1 | If we lower ASR confidence threshold for Starter/Pre-A1, recognition success rate will increase without degrading learning quality | A/B test: lower threshold by 20% for new Pre-A1 users. Monitor recognition rate + false positive rate | ASR success rate; false positive ≤15% | Success rate from ~60% → 80% |
| E1.2 | If Pika varies failure responses and shows what it heard, child frustration (measured by session abandonment after ASR fail) will decrease | Deploy new failure UX to 50% of users | Session abandonment rate after ASR failure | Drop from est. ~40% → ≤20% |
| E1.3 | If we collect 1000+ child voice samples and fine-tune ASR, overall recognition accuracy improves | Opt-in voice data collection program → retrain model | ASR word error rate (WER) | WER reduction ≥30% |

---

### O3: Child Can't Engage Independently

> "Chỉ dùng khi bố mẹ động viên, ngồi cùng"
> "Pika phải giúp trẻ nói chuyện hào hứng, không cần bố mẹ ngồi cạnh"
> "con bận đi học thêm và bố mẹ cũng bận không cho dùng được"

#### Solutions

| ID | Solution | Perspective | Effort | Impact |
|----|----------|------------|--------|--------|
| S3.1 | **Proactive engagement engine**: Pika initiates conversation at scheduled times with personalized hooks: "Hôm nay ở trường có gì vui không?" / "Mình chơi trò đoán con vật nhé!" — no English pressure, just pull the child in | PM + Design | Medium | Very High |
| S3.2 | **Struggle-to-fun fallback**: When child disengages (silence >15s, repeated "không biết"), Pika auto-switches to games, storytelling, or Vietnamese chat before the child walks away. Re-introduce learning content after re-engagement | Engineering + PM | Medium | High |
| S3.3 | **Pika "personality moments"**: Give Pika unprompted personality quirks — random fun facts, silly songs, "guess what happened to me today" stories — that make the child curious to come back even without a parent pushing | Content + Design | Low | Medium |
| S3.4 | **Parent async task assignment**: Parents set a daily "mission" via app (e.g., "Learn 3 animal names today"). Pika presents it as a fun quest. Child can complete it independently. Parent gets completion notification | PM + Engineering | Medium | High |

#### Experiments

| Exp | Hypothesis | Method | Metric | Threshold |
|-----|-----------|--------|--------|-----------|
| E3.1 | If Pika proactively initiates fun interactions at set times, unprompted engagement (sessions without parent intervention) will increase | Deploy scheduled proactive prompts for test group. Track who initiates: child, parent, or Pika | % sessions child-initiated or Pika-initiated (no parent) | From est. ~30% → 60% |
| E3.2 | If Pika falls back to games/chat when detecting disengagement, session completion rate will improve | Prototype disengagement detection + auto-fallback. A/B test | Session abandonment rate + avg session length | Abandonment −30%, session length +25% |
| E3.3 | If parents can set daily missions, child daily active rate will increase (because the child has a clear "thing to do" with Pika) | Build MVP mission feature (3 template missions). Test with 30 families for 2 weeks | Days active per week + mission completion rate | Active days from ~3 → 5/week |

---

## Secondary Opportunities — Solutions Sketch

### O6: Parents Lack Visibility into Learning

| Solution | Description |
|----------|-------------|
| S6.1 | **Daily conversation summary**: Push notification to parent app with 3-line summary of what child discussed/learned today |
| S6.2 | **Weekly learning report**: Vocabulary learned, pronunciation progress, time spent, topics covered. Sent via app + optional email |
| S6.3 | **Real-time Pika status**: Show in parent app whether Pika is sleeping, chatting, or in lesson mode |

*Why this matters for renewal*: Parents who can see tangible learning progress will perceive higher ROI → higher willingness to pay 120k/month.

### O5: Parents Want Custom Content

| Solution | Description |
|----------|-------------|
| S5.1 | **Custom vocabulary list**: Parents add words via app → Pika incorporates them into games and quizzes |
| S5.2 | **Photo-to-lesson**: Parents photograph textbook page → Pika creates a practice session from it |
| S5.3 | **Topic scheduling**: Parents choose this week's conversation themes (animals, weather, family) |

*Why this matters for value*: Aligns Pika with what child learns at school/tutoring → perceived as complementary, not competing with other education spend.

---

## Full Tree Visualization

```
                    ┌─────────────────────────────────────────────┐
                    │          DESIRED OUTCOME                     │
                    │  30-day renewal: 15% → 35%                   │
                    │  (Active ≥15d, ≥2 quality sessions/day,      │
                    │   60% willing to renew, 60% close rate)       │
                    └───────────────────┬─────────────────────────┘
                                        │
             ┌──────────────────────────┼──────────────────────────┐
             │                          │                          │
    ┌────────▼────────┐      ┌─────────▼─────────┐     ┌─────────▼─────────┐
    │  O2: BEGINNER   │      │ O1: SPEECH RECOG  │     │ O3: INDEPENDENT   │
    │  CONTENT TOO    │      │ FAILURES          │     │ ENGAGEMENT        │
    │  HARD           │      │                   │     │                   │
    │  Score: 0.81    │      │ Score: 0.80       │     │ Score: 0.68       │
    │  → KR1, KR2     │      │ → KR2             │     │ → KR1             │
    └───────┬─────────┘      └────────┬──────────┘     └────────┬──────────┘
            │                         │                          │
     ┌──────┼──────┐          ┌───────┼──────┐          ┌───────┼──────┐
     │      │      │          │       │      │          │       │      │
   S2.1   S2.2   S2.3      S1.1    S1.2   S1.4      S3.1    S3.2   S3.4
  Starter Gentle  Adaptive Child   Lenient Graceful Proactive Struggle Parent
  Level  Onboard Difficulty Voice   Mode   Failure  Engage   Fallback Mission
         Flow    Engine    Tuning         Response  Engine
     │      │      │          │       │      │          │       │      │
   E2.1   E2.2   E2.3      E1.3    E1.1   E1.2      E3.1    E3.2   E3.3
  10-les  Fun-   Struggle  Voice   Lower  Varied   Scheduled Disengage Daily
  Starter first  detect    data    thresh response  prompts  detect   mission
  A/B     D1-3   test      collect A/B    A/B      test     A/B      MVP


             ┌──────────────────────────┐──────────────────────────┐
             │                                                     │
    ┌────────▼────────┐                                 ┌─────────▼─────────┐
    │  O6: PARENT     │                                 │ O5: CUSTOM        │
    │  VISIBILITY     │                                 │ CONTENT           │
    │  Score: 0.72    │                                 │ Score: 0.76       │
    │  → KR3          │                                 │ → KR2             │
    └───────┬─────────┘                                 └────────┬──────────┘
            │                                                     │
     ┌──────┼──────┐                                       ┌──────┼──────┐
   S6.1   S6.2   S6.3                                    S5.1   S5.2   S5.3
  Daily  Weekly  Real-time                              Custom Photo-  Topic
  Summary Report Status                                 Vocab  Lesson  Schedule
```

---

## Recommended Execution Sequence

### Sprint 1-2 (Now → Mid-April): Quick wins + foundations
- **E1.1**: Lower ASR threshold for Pre-A1 (low effort, immediate impact)
- **E1.2**: Deploy varied ASR failure responses (low effort)
- **E2.2**: Implement fun-first Days 1-3 onboarding (medium effort, highest retention impact)
- WiFi credential persistence (quick engineering fix)
- Voice-command sleep mode (quick fix)

### Sprint 3-4 (Mid-April → Mid-May): Core content + engagement
- **E2.1**: Build and test Starter level module (10 lessons)
- **E3.1**: Deploy proactive engagement engine
- **E3.3**: MVP parent mission feature
- **S6.1**: Daily conversation summary to parent app

### Sprint 5-6 (Mid-May → End June): Deep improvements + renewal prep
- **E1.3**: Child voice ASR retraining (with collected data)
- **E2.3**: Adaptive difficulty engine
- **E3.2**: Struggle-to-fun fallback system
- **S6.2**: Weekly learning report (key for renewal conversion — parents see ROI before subscription decision)
- **S5.1**: Custom vocabulary input

### July 1: Renewal at 120k/month begins
By this point, users should have experienced:
- Smooth first week (no excitement cliff)
- Reliable speech recognition
- Child engages independently most days
- Parents receive weekly progress reports showing tangible improvement
- → Parent perceives clear ROI → willing to pay 120k/month

---

## Key Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| ASR improvement takes longer than expected | Blocks O1, degrades O2 | Ship lenient mode (S1.2) as interim fix; it's low-effort |
| Starter content doesn't retain Pre-A1 kids | Blocks KR1 | Test E2.2 (fun-first onboarding) in parallel — retention can improve even before Starter content is ready |
| Parents don't see learning reports before renewal decision | Blocks KR3 | Prioritize S6.2 weekly report by Sprint 5 at latest |
| Proactive engagement feels annoying not fun | Hurts O3 | User test S3.1 with 10 families before wide rollout |

---

## How This Tree Connects to Pika's Value Layers

| Opportunity | Primary Value Layer | Why |
|-------------|-------------------|-----|
| O2: Beginner content | **Layer A** (English Speaking Companion) | Fixes the core learning loop for the largest incoming segment |
| O1: Speech recognition | **Layer A + D** | ASR is infrastructure — blocks both learning (A) and emotional bond through conversation (D) |
| O3: Independent engagement | **Layer D** (Attachment & Presence) | Habit formation and emotional continuity require the child to *want* to engage without being told |
| O6: Parent visibility | **Stakeholder: Parent as guardian** | Parents are buyers — they need to see value to renew |
| O5: Custom content | **Stakeholder: Parent as co-creator** | Enables the "co-creation" role defined in Pika's value direction |

---

*This OST should be reviewed and updated weekly as experiment results come in. Kill solutions that don't validate. Explore new branches as you learn.*

*Built using the Opportunity Solution Tree framework (Teresa Torres, Continuous Discovery Habits) with Opportunity Scoring (Dan Olsen, The Lean Product Playbook).*
