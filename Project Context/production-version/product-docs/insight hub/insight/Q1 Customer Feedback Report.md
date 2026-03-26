# Q1 2026 Customer Feedback Analysis Report — Pika Robot

**Date**: 2026-03-24
**Feedback analyzed**: ~150+ responses across 4 sources
**Sources**:
1. Facebook community page comments (~60+ comments)
2. In-app survey / Google Forms (~25 responses)
3. Customer check-up interviews with mentor-guided users (~25 users)
4. Churned user interviews — dropped within 7 days (~45 users contacted, ~6 responded)

**Period**: January – March 2026
**Product**: Pika — AI English-learning robot for Vietnamese children

---

## Executive Summary

Pika generates strong emotional attachment — children love the character and free-talk conversations. However, **three critical issues drive dissatisfaction and churn**: poor speech recognition (especially for children's voices and regional accents), learning content that's too hard for true beginners, and the robot's inability to stop talking when asked. Churned user interviews confirm these same pain points, with the added insight that **children who can't engage independently (without a parent sitting next to them) drop off fastest**. The data strongly suggests that fixing ASR and beginner content would have the highest impact on retention.

---

## Overall Sentiment

| Source | Positive | Neutral | Negative | Avg Score |
|--------|----------|---------|----------|-----------|
| Facebook comments | ~30% | ~25% | ~45% | N/A |
| In-app survey (Form) | ~25% | ~20% | ~55% | 6.3/10 |
| Customer check-up (guided) | ~40% | ~35% | ~25% | 7.5/10 |
| Churned users (7D drop) | ~10% | ~20% | ~70% | ~5/10 (est.) |

**Key observation**: Mentor-guided users rate significantly higher (7.5 vs 6.3) than self-guided users, and dramatically higher than churned users. This validates that **guided onboarding and teacher support substantially improve outcomes**.

**Trend**: Negative sentiment concentrates around speech recognition and learning content. Positive sentiment clusters around the concept, Pika's personality/cuteness, and free-talk conversation quality.

---

## Top Themes

| # | Theme | Mentions | Sentiment | Sources | Priority |
|---|-------|----------|-----------|---------|----------|
| 1 | Speech recognition / voice understanding | 35+ | Very Negative | All 4 | Critical |
| 2 | Learning content too hard for beginners | 30+ | Negative | All 4 | Critical |
| 3 | Pika won't stop talking / no sleep command | 15+ | Negative | FB, Survey | High |
| 4 | WiFi reconnection issues | 12+ | Negative | FB, Survey | High |
| 5 | Vocabulary drill & custom content requests | 20+ | Neutral/Request | FB, Survey, Check-up | High |
| 6 | Parent app UX issues | 12+ | Negative | FB, Survey | Medium |
| 7 | Pika's "um" filler word habit | 8+ | Negative | FB | Medium |
| 8 | Child can't engage independently | 6+ | Negative | Churn, Survey | High |
| 9 | Free-talk conversation quality | 15+ | Positive | All 4 | Strength |
| 10 | Cute design & emotional bond | 20+ | Very Positive | FB, Survey | Strength |
| 11 | Response latency | 10+ | Negative | FB, Survey | Medium |

---

## Theme Deep-Dive

### Theme 1: Speech Recognition — 35+ mentions, CRITICAL

**What users are saying:**
> "Pika nghe rất tệ, không nghe được nhiều từ tiếng Anh"
> "phải nói đi nói lại"
> "giọng miền Nam nên Pika nghe ko rõ"
> "Có cần phải hét to với pika không?"
> "trẻ trả lời đúng nhưng Pika cứ bảo sai và hỏi lại nhiều lần nên khó chịu — trẻ chê Pika ngu" (churned user)

**Root cause**: ASR struggles with children's voices, Southern Vietnamese accents, and English pronunciation from young learners. Pronunciation correction mode is too strict — marks correct pronunciation as wrong repeatedly.

**Impact**: Primary driver of both frustration and churn. Children get frustrated and refuse to engage. Churned user interviews confirm this — kids who experience repeated ASR failures lose interest within the first week.

**Recommendation**:
1. Tune ASR sensitivity for children's voices and regional accents
2. Add "lenient mode" for beginners
3. Vary Pika's responses when it doesn't understand (stop repeating "ù tai")
4. When Pika misrecognizes, show what it heard so parent/child can adjust

---

### Theme 2: Learning Content Too Hard for Beginners — 30+ mentions, CRITICAL

**What users are saying:**
> "Pre A1 vẫn hơi khó cho các bé mới bắt đầu"
> "câu khá dài và khó với bé chưa có trình độ"
> "nên bắt đầu bằng những từ vựng cơ bản như book, pen, ball"
> "Bài học pre-A1 khó với trẻ, cháu nản → PH cần module song ngữ dễ hơn" (churned user)

**Churn data confirms**: A churned parent (child age 6) reported the child was initially excited to chat in Vietnamese but became discouraged once English content started — the sentences were too long and the child couldn't follow. Log data showed the child kept reverting to Vietnamese free-talk and avoided the English lessons entirely.

**Root cause**: Pre-A1 curriculum starts with phrases/sentences instead of individual basic vocabulary. No level differentiation for true beginners vs. kids with some English foundation. Bilingual mode forces long English sentences that overwhelm young learners.

**Impact**: Kids get discouraged within the first few sessions. This is a primary early churn driver — the "excitement cliff" happens when children move from fun Vietnamese chatting to structured English learning that's too hard.

**Recommendation**:
1. Add a "Starter" level below Pre-A1 with single-word vocabulary from daily life (colors, animals, food, school items)
2. In bilingual mode, start with short words/phrases before progressing to sentences
3. Slow down English speech speed further for lowest levels
4. Add Vietnamese scaffolding explanations for first-time learners

---

### Theme 3: Pika Won't Stop Talking / No Sleep Mode — 15+ mentions, HIGH

**What users are saying:**
> "bảo tạm biệt Pika nhưng Pika không tự vào chế độ ngủ"
> "Pika vẫn tự chào tự chúc mãi ko ngừng"
> "cứ tự dẫn chuyện khi không nhận được phản hồi"

**Root cause**: No voice-command sleep trigger. No auto-sleep after sustained silence. Pika generates conversation prompts even after explicit goodbye.

**Impact**: Frustrates both parents and children. Forces physical button press. Particularly annoying at bedtime.

**Recommendation**:
1. Add voice command for sleep ("Pika ngủ đi" / "Goodbye Pika")
2. Auto-sleep after 3-4 unanswered prompts
3. Stop conversation continuation after explicit goodbye

---

### Theme 4: WiFi Reconnection — 12+ mentions, HIGH

**What users are saying:**
> "mỗi lần mang lên xe dùng phải thiết lập lại kết nối wifi"
> "rút sạc qua đêm thì không bắt lại được WIFI"

**Churn data**: One churned user reported a connection error after initial setup that was never resolved — they stopped using the product entirely.

**Root cause**: Pika doesn't persist WiFi credentials across restarts or location changes.

**Recommendation**: Save multiple WiFi networks and auto-reconnect. This is a quick engineering win with high usability impact.

---

### Theme 5: Vocabulary Drill & Custom Content — 20+ mentions, HIGH

**What users are saying:**
> "app có thêm chức năng ôn luyện từ vựng phụ huynh có thể tự thêm"
> "phụ huynh có cách nào input tài liệu đọc/truyện kể vào Pika?"
> "tối đa hóa tính cá nhân của mỗi Pika"
> "muốn Pika có đoạn hội thoại luyện tập đơn giản để con biết cách nói câu"

**Root cause**: Parents want to supplement the fixed curriculum with their own vocabulary lists, stories, and topics aligned to what kids learn at school or tutoring centers.

**Recommendation**:
1. Add parent-facing vocab input on the app
2. Allow custom topics/stories upload
3. Show daily conversation summaries so parents can track discussions
4. Add structured vocab review/drill mode separate from lessons

---

### Theme 6: Parent App UX — 12+ mentions, MEDIUM

**What users are saying:**
> "UI thì đẹp mà UX thì tệ"
> "nút LÊN LỊCH bị che phải vuốt xuống mới thấy"
> "phần lộ trình học tệ và bất tiện"
> "ko sửa được sở thích"
> "Nên bổ sung để custom những thứ cá nhân hoá"

**Root cause**: App prioritizes aesthetics over usability. Key actions are hidden behind scrolling. No ability to update child profile (interests, habits) after onboarding.

**Recommendation**:
1. Redesign home screen to surface schedule + learning progress
2. Allow editing child profile (interests, name, age-appropriate settings)
3. Add remote status check (is Pika sleeping? learning? chatting?)
4. Add learning progress reports (weekly/monthly)

---

### Theme 7: Pika's "Um" Filler Sounds — 8+ mentions, MEDIUM

**What users are saying:**
> "Pika hay ờm quá, mỗi lần suy nghĩ lại kèm theo tiếng ờm"
> "trẻ dễ bị nhiễm vào phong cách nói vì 0-10 tuổi vẫn học theo bắt chước"
> "nghe bé hơn 3 tuổi nói theo style Pika mà hơi giật mình vì nghe như robot nói"

**Impact**: Parents are genuinely worried about children developing bad speech habits from Pika's filler sounds.

**Recommendation**: Replace "ờm" filler with silence or a visual "thinking" animation on screen.

---

### Theme 8: Child Can't Engage Independently — NEW from Churn Data, HIGH

**What churned users are saying:**
> "Chỉ dùng khi bố mẹ động viên, ngồi cùng"
> "Pika phải giúp trẻ nói chuyện hào hứng, không cần phải bố mẹ ngồi cạnh nữa"
> "Đã lâu không dùng — con bận đi học thêm và bố mẹ cũng bận không cho dùng được"

**Root cause**: Young or beginner children struggle to interact with Pika independently. When they hit language barriers, there's no adult to help, so they give up. Busy parents can't sit with the child every session.

**Impact**: This is a hidden churn driver — the product requires parent involvement that many families can't sustain daily.

**Recommendation**:
1. Improve Pika's ability to scaffold and simplify when a child struggles (detect confusion → switch to easier content)
2. Add guided conversation starters that don't require English proficiency
3. Make the first 2 weeks of interaction primarily fun/Vietnamese to build habit before introducing English lessons
4. Consider a "buddy mode" where Pika proactively engages the child with games when sensing disengagement

---

### Theme 9: Free-Talk Conversation Quality — STRENGTH

**What users are saying:**
> "Pika trả lời phản hồi lại rất thông minh"
> "nói chuyện rất vui"
> "Pika dễ thương, giọng phù hợp lứa tuổi"
> "Các cuộc trò chuyện nói tự do với bé, Pika làm rất tốt"

**Impact**: Key engagement and retention driver. Children bond emotionally with Pika through free-talk. This is the primary hook keeping users active.

**Recommendation**: Protect and strengthen this. Consider guided free-talk with parent-set topic suggestions for families wanting more structure. Add topical conversation modes (storytelling, games, Q&A about school).

---

### Theme 10: Cute Design & Emotional Bond — STRENGTH

> "Con cảm ơn mẹ" — child's first reaction seeing Pika
> "Pika dễ thương, giọng phù hợp lứa tuổi"
> "rất tự hào về sản phẩm made in Việt Nam"
> "bé ôm Pika ngủ"

**Impact**: Strong first impression and emotional attachment. Vietnamese-made pride is a genuine differentiator. This goodwill buys time for product improvements.

---

## Segment Analysis

| Segment | Volume | Avg Sentiment | Top Pain Point | Churn Risk |
|---------|--------|---------------|----------------|------------|
| **Pre-A1 / Beginner (5-6 yo)** | ~30% | Low (4-5/10) | Content too hard + ASR | Very High |
| **A1 (7-8 yo)** | ~35% | Medium (6-7/10) | Need vocab variety + more games | Medium |
| **A2 (9-13 yo)** | ~20% | Medium-High (7-8/10) | Want higher levels (B1+) + deeper content | Medium (outgrowing) |
| **Churned (7D drop)** | ~15% of sample | Very Low (~5/10) | ASR + content difficulty + can't engage independently | Already churned |
| **Parents (all segments)** | 100% | Mixed | App UX + learning reports + customization | Depends on child |

### Key Segment Insight
**Pre-A1 beginners are the highest-risk segment** and likely the largest incoming cohort (parents buying Pika for children with no English foundation). The current Pre-A1 curriculum does not serve them — it's designed for children who already know some English. Fixing this gap would directly reduce early churn.

---

## Churn Analysis (Dropped within 7 Days)

**Sample**: 45 users contacted, only ~6 provided detailed responses (13% response rate). Most were unreachable or declined.

### Churn Patterns

| Pattern | Frequency | Description |
|---------|-----------|-------------|
| **Excitement cliff** | Most common | Child excited at first (Vietnamese chat), drops off when English content begins |
| **ASR frustration** | High | Child gives up after repeated recognition failures |
| **Too busy** | Moderate | Child busy with school/tutoring, parents too busy to supervise |
| **Technical issues** | Low | WiFi/connection problems leading to abandonment |
| **Content mismatch** | Moderate | Content too easy (advanced kids) or too hard (beginners) |

### Critical Churn Insight
The typical churn journey is:
1. **Day 1-2**: Child is excited, chats with Pika in Vietnamese, plays games — high engagement
2. **Day 3-4**: Child tries English lessons or parents push English mode — hits difficulty wall
3. **Day 5-7**: Child repeatedly fails at ASR or can't follow lessons — frustration builds, engagement drops
4. **Day 7+**: Child stops asking to use Pika — product sits idle

**Implication**: The onboarding experience in the first week is make-or-break. If the child doesn't have a positive English learning experience within 7 days, they're unlikely to return without parent intervention.

---

## Customer Check-up Insights (Guided Learning Program)

From structured interviews with mentor-guided users (March 2026):

| Metric | Finding |
|--------|---------|
| **Vocabulary retention** | 70-90% for most children with guided practice |
| **Common pronunciation issue** | Missing ending sounds (/t/, /s/), multi-syllable words |
| **Most liked lessons** | Food topics, fishing game, guessing games, flashcards |
| **Most disliked lesson** | "Đánh thức rồng con" (Wake the Dragon) — repeatedly flagged as boring/hard |
| **Parent satisfaction** | 7-9/10 (significantly higher than self-guided) |
| **Learning frequency** | 4-6 days/week, 15-30 min/day |
| **Independence** | Most children learn independently; parents assign tasks via app |
| **Interest in teacher program** | Multiple parents expressed strong interest in paid teacher+Pika combo |
| **Subscription renewal intent** | Most say "let the child finish current plan first, then renew" |

**Key finding**: Children with mentor/teacher support show dramatically better outcomes than self-guided users — strong validation signal for a teacher-assisted product tier.

---

## Notable Quotes

> "Mẹ hơi thất vọng! Hi vọng team cải thiện nhanh và tốt hơn" — Parent, rating 3/10

> "Con thích Pika quá mẹ ơi, nói chuyện với Pika thật vui. Nhưng Pika ko cho con suy nghĩ" — Child, first day user

> "Mình rất tự hào về sản phẩm made in Việt Nam. Mong Pika ngày càng hoàn thiện" — Parent, rating 6/10

> "Pika nghe quá kém, nội dung trò chuyện nhạt nhẽo khiến con không hứng thú" — Parent, rating 2/10

> "trẻ trả lời đúng nhưng Pika cứ bảo sai và hỏi lại nhiều lần — trẻ chê Pika ngu" — Churned user parent, child age 10

> "Pika phải giúp trẻ nói chuyện hào hứng, không cần bố mẹ ngồi cạnh nữa" — Churned user parent

> "9/10, con chỉ thấy chán pika nói nhiều và lặp lại nhiều lần" — Child, age 9, check-up interview

---

## Actionable Recommendations (Prioritized)

### P0 — Critical (do now)
1. **Fix speech recognition** — Tune ASR for children's voices + Southern accents. Add lenient mode for beginners. This is the #1 driver of both frustration and churn across all data sources.
2. **Redesign beginner curriculum** — Add a true "Starter" level with single-word vocabulary (colors, animals, objects) before phrases. Directly addresses the Pre-A1 segment which has the highest churn rate.
3. **Improve first-week onboarding** — Keep Days 1-3 primarily fun (games, Vietnamese chat, easy words) to build habit before introducing harder English content. The "excitement cliff" at Day 3-4 is where most users are lost.

### P1 — High (next sprint)
4. **Add voice-activated sleep mode** — Quick win. "Pika ngủ đi" command + auto-sleep after 3-4 unanswered prompts.
5. **Persist WiFi credentials** — Save multiple networks, auto-reconnect on restart.
6. **Build Pika's scaffolding ability** — When child struggles, Pika should auto-simplify (shorter sentences, switch to Vietnamese hints, offer a game break) instead of repeating the same prompt.

### P2 — Medium (this quarter)
7. **Remove "ờm" filler sounds** — Replace with silent pause or visual thinking indicator.
8. **Parent app redesign** — Surface learning progress, allow profile editing, add remote status check.
9. **Custom vocabulary feature** — Let parents add words/topics through the app.
10. **Expand song library** — Current 2-3 songs on repeat is a common complaint.

### P3 — Strategic (next quarter)
11. **Teacher-assisted tier** — Customer check-up data strongly validates this. Parents are willing to pay for guided learning with a teacher + Pika combination.
12. **Add B1+ content** — Older/advanced children (A2 segment) are outgrowing current content and will churn without higher levels.
13. **Multi-child support** — Multiple parents asked about using one Pika for 2-3 children with separate profiles.

---

## Gaps & Recommended Follow-Up Research

| Gap | Why It Matters | Suggested Action |
|-----|---------------|-----------------|
| No formal NPS tracking | Can't benchmark or track satisfaction over time | Add standard NPS question to app |
| Low churn interview response rate (13%) | Silent churners may have different/worse reasons | Try in-app exit survey before subscription expires |
| No cohort analysis | Can't tell if product updates improve sentiment | Tag feedback by app version / firmware version |
| No competitive benchmarking | Parents mention Duolingo, Reading Eggs, Elixir — need systematic comparison | Run `/competitive-analysis` on key alternatives |
| Missing data on "happy path" | What do retained, highly engaged users do differently? | Interview top 10% active users to identify success patterns |
| Regional accent coverage unknown | How many users are affected by Southern/Central accent ASR issues? | Analyze ASR error logs by region |

---

## Suggested Next Steps

- **Create user personas** from these patterns (e.g., "Beginner Family", "Independent Learner", "Power Parent", "Outgrowing Student")
- **Triage top themes as feature requests** with impact/effort prioritization (RICE or ICE framework)
- **Design interview scripts** to go deeper on: (a) first-week experience for churned users, (b) what makes guided users more successful
- **Build an Opportunity Solution Tree** linking retention outcomes to the opportunities identified here
- **Run competitive analysis** on Duolingo Lily AI, Reading Eggs, Elixir robot, Babilala

---

*Report generated following the `/analyze-feedback` framework from PM Skills Marketplace. Data sources: Facebook community, Google Forms survey, customer check-up interviews, 7-day churn interviews.*
