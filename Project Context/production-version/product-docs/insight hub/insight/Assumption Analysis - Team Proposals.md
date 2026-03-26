# Assumption Analysis — Team Proposals (March 2026)

> Framework: Identify Assumptions (Existing Product) — Value, Usability, Viability, Feasibility
> Devil's advocate analysis from PM, Designer, and Engineer perspectives
> Cross-referenced with: H1 2026 Goals, Q1 Customer Feedback Report, OST, Pika Value Direction

---

## Proposals Evaluated

| # | Proposal | Author | Core Idea |
|---|----------|--------|-----------|
| P1 | Pika V2 Strategy | (Strategy doc) | 4-layer value framework: functional dependence, personalized chit-chat, adaptive influence, Pika as family member |
| P2 | Backlog Observation | Long | Optimize Learning content intelligence, Buddy Talk, lesson creation templates, todo flow |
| P3 | User Interview Insights | Dịu | Churn findings from 5 churned + 3 active users — ASR, content difficulty, parent guidance gaps |
| P4 | Parental Roadmap Aligning | (Strategy doc) | Parent activation, hook UX loop, app redesign, onboarding, badge system, parent-child engagement |
| P5 | Robot Roadmap — Q1 | (Roadmap) | Feature timeline across 10 pillars: Orchestrator, Buddy Talk, Parental Control, Gamification, Onboarding, Learning Design, Content, Core AI, Extended Value, Product MKT |

---

## P1: Pika V2 Strategy

### Summary
A comprehensive strategic vision positioning Pika as a "Learning Companion & Life Companion" across 4 value layers (Key Value → Value Assist → Value Imprint → Attachment & Presence). Core strategies: functional dependence through daily utility, attraction via personalized chit-chat, and value imprint through 8 character pillars.

### Assumptions Identified

#### VALUE — Will this create value for customers?

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| V1 | Parents will pay 120k/month for a "life companion" beyond English learning | High | Low | Q1 data shows parents bought Pika primarily for English. "Life companion" value (Layer B-D) is nice-to-have but not what parents open their wallets for. If English learning (Layer A) doesn't work well, Layers B-D won't save renewal. | Survey 50 parents: "Would you renew Pika if English learning stayed the same but it helped with daily routines?" vs. "Would you renew if English improved but nothing else changed?" |
| V2 | "Functional dependence" will form within weeks/months, not years | High | Low | The strategy references academic research on robot adoption showing users drop off after the "honeymoon phase." Current data shows this happens by Day 3-4 for Pika — much faster than the strategy accounts for. The functional dependence thesis assumes Pika survives the first week, but the excitement cliff kills engagement before dependence can form. | Track D7/D14/D30 retention by usage pattern. Does any user segment show increasing (not flat/declining) daily usage after Week 1? |
| V3 | Children aged 5-12 will develop "functional reliance" on an AI robot | Medium | Low | Adults form tool habits (ChatGPT, Google). Children's attention and interests shift rapidly (parents noted "2-4 tuần đổi sở thích/lần"). Functional dependence may not apply the same way to children. The emotional bond (Layer D) may be more realistic than functional reliance (Layer B). | Cohort analysis: compare retention curves of children who primarily use free-talk (Layer D) vs. those who primarily use structured learning (Layer A). Which group retains longer? |
| V4 | The "Adaptive Influence Framework" — nudging children's behavior through conversation — is valued by parents | Medium | Medium | Some parents want this (character building), but others may find it overreaching or creepy. No Q1 feedback specifically asked for behavior modification. Parents' top requests were: better ASR, easier content, custom vocab, progress reports. | Parent focus group: present the Adaptive Influence concept. Measure reaction: "love it" vs. "that's fine" vs. "that's uncomfortable." |
| V5 | Pika can credibly expand beyond English to Math, Science, History, Geography (Layer B) without becoming a "mediocre everything" | High | Low | Stretching into academic assistance for multiple subjects risks diluting the English identity (Layer A) before it's even working well. Q1 data shows English learning isn't solid yet — ASR issues, content too hard, beginner curriculum missing. Adding more subjects now could spread engineering resources too thin. | Before building multi-subject: fix English first. Track if parents who see English improvement are more likely to request other subjects. |

#### USABILITY — Will users figure out how to use this?

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| U1 | Parents understand the 4-layer value model and can navigate between learning modes, daily assistance, and free-talk | High | Low | Q1 feedback shows parents already struggle with basic app UX. Many don't know Pika has daily activities beyond lessons. Dịu's interviews confirm: "pH không biết mà cứ nghĩ chỉ có nói chuyện thôi." A 4-layer system will be even harder to understand. | Usability test: give 10 parents the V2 prototype. Can they find and use Layer A vs. B vs. D features without guidance? |
| U2 | "Personalized chit-chat" will feel natural enough that children aged 5-7 can engage without adult help | Medium | Medium | Free-talk already works well for verbal children (Q1 positive theme). But younger/shyer children struggle without parent presence (churn data Theme 8). Personalization requires the child to share information — young children may not do this unprompted. | Track: do children under 7 self-initiate chit-chat sessions at the same rate as 8-12 year olds? |
| U3 | The memory/personalization system ("Pika remembers you") will work reliably enough to build trust | High | Low | Q1 data includes a parent reporting: "Pika đến hôm nay vẫn k nhớ gì về bé hết. Đang nói chuyện tự động khởi động lại hoặc tự nhảy sang chương trình học và quên hết." If memory is unreliable, it actively damages trust — worse than no memory at all. | Test memory persistence across 100 sessions with 20 users. Measure: does Pika correctly recall name, interests, and conversation context after restart? Target: >95% accuracy. |

#### VIABILITY — Can the business support this?

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| B1 | The team can execute on 4 value layers + multi-subject content + adaptive influence + personalization simultaneously while also fixing critical V1 issues (ASR, beginner content, sleep mode, WiFi) | Very High | Very Low | This is the biggest risk. The V2 strategy is ambitious and comprehensive, but Q1 data screams that the basics aren't working yet. If the team splits focus between "fix V1 problems" and "build V2 vision," neither gets done well. The H1 goal (15% → 35% renewal) has a July 1 deadline — 3 months away. | Capacity planning: list all V1 fixes needed + V2 features planned. Does the team have bandwidth for both? If not, what gets cut? |
| B2 | 120k/month pricing is sustainable when parents can compare to free alternatives (Duolingo Lily, ChatGPT) | Medium | Medium | Multiple parents already compare Pika unfavorably to ChatGPT ("Pika không trả lời được" vs. "cùng từ đó tôi nói cho ChatGPT thì lại ổn"). As free AI gets better at English tutoring, the subscription must justify its physical presence + child-specific design. | Competitive price sensitivity test: survey parents on willingness to pay at 80k, 120k, 150k given current feature set vs. planned V2 features. |

#### FEASIBILITY — Can it be built?

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| F1 | Personalized memory at scale (each Pika remembers each child's context, preferences, learning history) is technically achievable with current infrastructure | High | Medium | Per-child state management, context retrieval, and persistence across sessions/restarts is non-trivial. Current evidence suggests memory doesn't persist reliably. Scaling this to thousands of devices adds complexity. | Technical spike: build a memory persistence prototype. Test with 50 devices over 2 weeks. Measure context recall accuracy and latency impact. |
| F2 | "Adaptive Influence Framework" can be implemented in LLM prompting without unpredictable behavior | High | Low | LLMs can be inconsistent. Designing AI that subtly influences children's behavior requires extremely careful prompt engineering and safety guardrails. One wrong response could create parent backlash. | Red-team testing: have 5 adults role-play as children with various emotional states. Does the adaptive framework respond appropriately 100% of the time? Any harmful or inappropriate responses? |
| F3 | Content library ("deep knowledge on every child interest") can be built fast enough for V2 launch | Medium | Low | Building a comprehensive, age-appropriate, factually accurate content library across "mọi sở thích của trẻ em" is a massive content effort. LLM knowledge alone isn't enough — needs curation for child safety and age-appropriateness. | Start with 10 most popular interest topics (from user data). Build content for those. Measure if chit-chat quality improves measurably vs. current generic responses. |

### Overall Assessment — P1

**Strengths**: Visionary and well-reasoned strategic framework. Strong theoretical grounding. Correctly identifies that novelty wears off and Pika needs to become "assimilated into daily life." Layers are logically structured.

**Critical concern**: The strategy optimizes for the long game (functional dependence, presence, value imprint) while Q1 data shows users are churning in the first week due to basic problems (ASR, content difficulty). **The V2 vision is the right destination, but the bridge from V1's broken state to V2's vision is missing.** The strategy needs a "V1.5" phase that fixes the fundamentals before layering on advanced features.

**Recommendation**: Sequence as — Fix V1 basics (Sprint 1-4) → Build V2 Layer A properly (Sprint 5-8) → Then Layer D + B (Sprint 9+). Don't attempt Layers B, C, D until Layer A is solid.

---

## P2: Backlog Observation (Long)

### Summary
Four concrete optimization areas: (1) Make learning content smarter (ASR accuracy + pronunciation correction), (2) Buddy Talk integration with daily lessons, (3) Lesson creation template diversity, (4) Todo flow optimization for D1→D7 retention. Includes self-reflective questioning about assumptions.

### Assumptions Identified

#### VALUE

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| V6 | Fixing pronunciation correction (intent fallback/false/silent/idk) will make parents feel Pika is "smart" | Medium | Medium | Q1 data supports this — parents want accurate recognition and correction. However, the current complaint is more fundamental: Pika can't hear the child at all (ASR failure), not just pronunciation correction quality. Fixing correction logic on top of broken ASR is like polishing a car that won't start. | Measure: what % of failed interactions are ASR failures (Pika hears wrong words) vs. pronunciation assessment failures (Pika hears right words but scores wrong)? Fix the higher-volume problem first. |
| V7 | Buddy Talk integrating daily lessons will increase perceived learning value | Medium | Medium | Good hypothesis. Parents want coherent daily experiences ("1 set trải nghiệm mỗi ngày phải thật sự liên quan đến nhau"). But risk: if Buddy Talk becomes "homework review" it loses the fun factor that makes free-talk Pika's strongest engagement driver. | A/B test: Buddy Talk with lesson integration vs. Buddy Talk as pure fun conversation. Compare session length, child-initiated return rate, and parent satisfaction. |
| V8 | "Phụ huynh muốn template học thuật để tự triển khai tạo bài" — parents will actively create custom lessons | Medium | Low | Q1 data shows most parents don't even use the app's existing features fully (Dịu: "Ph báo ít dùng"). Expecting parents to design lesson templates is asking for even higher engagement with a tool they barely open. Only power users (~10-15%) would use this. | Track current "tạo bài" feature usage rate. If <10% of parents use the existing simple version, a more complex template system won't be adopted widely. |

#### USABILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| U4 | "Thanh năng lượng đo độ chính xác" (accuracy energy bar) will help children understand pronunciation feedback | Low | Medium | Good UX idea. Visual feedback is more intuitive than verbal correction for children. Risk is minor: some younger children may not understand the bar metaphor. | Prototype the energy bar with 10 children (ages 5-8). Can they understand "higher = better pronunciation" without explanation? |
| U5 | The D1→D7 churn problem is caused by "disconnected activities across days" rather than fundamental content/ASR issues | High | Low | Long wisely flags this as uncertain ("giả định đầu chưa thực sự rõ ràng"). Q1 data and churn interviews strongly suggest the primary D1→D7 churn driver is the excitement cliff (fun Vietnamese → hard English), not disconnected todo flow. Optimizing the todo flow won't help if children abandon Pika before reaching Day 3's todo. | Compare D1→D7 retention of: (a) users who completed Day 1 todo vs. (b) users who didn't. If retention is similar for both groups, the todo flow isn't the bottleneck — the content itself is. |

#### FEASIBILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| F4 | Pronunciation correction can be made accurate enough to satisfy parents while remaining pedagogically appropriate for children | High | Medium | There's a tension: parents want strict correction ("chính xác"), but children disengage from strict correction (Q1: "Pika hay sửa lỗi phát âm liên tục — các bé có chút hụt hẫng"). Finding the right balance is hard. | Test 3 correction intensity levels (lenient/moderate/strict) with 30 children. Measure: session length, return rate, and parent satisfaction for each level. |
| F5 | "Review lại toàn bộ template của phần Learn ở các lộ trình" can be done quickly | Medium | Medium | Template review across all learning paths is a significant content + engineering effort. If it takes weeks, it delays more impactful work (Starter level, ASR fixes). | Estimate: how many templates exist? How many hours per template to review and update? Is this a 1-week or 1-month effort? |

### Overall Assessment — P2

**Strengths**: Most grounded proposal of the four. Directly addresses real user pain points from Q1 data. Long demonstrates good PM instinct by questioning his own assumptions ("giả định đầu chưa thực sự rõ ràng") and advocating for validation before execution. The 4 observation areas are well-scoped.

**Critical concern**: The proposal treats learning content optimization and Buddy Talk as parallel workstreams, but they share a dependency — ASR. If Pika can't understand the child, neither smart pronunciation correction nor Buddy Talk integration will matter. **ASR is the prerequisite, not a parallel track.**

**Recommendation**:
1. Reorder: ASR accuracy → Pronunciation correction logic → Buddy Talk integration → Todo flow
2. The D1→D7 hypothesis needs validation before building solutions. Run the data analysis suggested in U5 first.
3. The "energy bar" idea (U4) is a quick, high-value UX win — prioritize it.

---

## P3: User Interview Insights (Dịu)

### Summary
Field research notes from 5 churned + 3 active user interviews. Key findings: (1) ASR failures are the top churn driver (4/5 churned parents reported), (2) Pre-A1 content is too hard for true beginners, (3) Parents don't understand Pika's daily activity system, (4) Children perceive Pika as a "learning tool" not a "friend" when parents assign lessons constantly, (5) Parents want homework help but Pika solves problems incorrectly.

### Assumptions Identified

These aren't assumptions in the interview data itself, but assumptions that would arise if we act on the findings:

#### VALUE

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| V9 | "Guide PH không ép trẻ nói tiếng anh khi chưa phù hợp" — parent education will change parent behavior | Medium | Low | Parents bought Pika specifically for English learning. Telling them "don't push English" contradicts their purchase motivation. Even with guidance, many parents will still push because that's why they spent money. | Test: send parent guidance messages (via app notification) during Week 1. Track if parents who receive guidance have different child usage patterns vs. control group. |
| V10 | "Pika feedback ngược lại giúp bố mẹ" — Pika proactively advising parents on appropriate difficulty levels will be welcomed | Low | Medium | Good idea with low risk. Parents want guidance (Q1: multiple requests for learning reports and recommendations). This aligns with the "parent as co-creator" stakeholder role in the Value Direction. | Prototype: after each session, Pika sends parent a brief note: "Hôm nay con gặp khó khăn với [X]. Gợi ý: [Y]." Measure parent read rate and satisfaction. |
| V11 | Homework help (BTVN) is a viable feature if accuracy improves | Medium | Medium | Dịu reports a parent tried homework help but "Pika giải sai nên hơi thất vọng." Math/Science accuracy from LLMs is improving but still unreliable for Vietnamese curriculum. Shipping unreliable homework help is worse than not having it — it erodes trust. | Benchmark: test Pika's accuracy on 100 grade 1-5 math problems from Vietnamese textbooks. If accuracy <90%, don't ship as a feature — position as "practice together" not "Pika solves it for you." |
| V12 | The finding "trẻ cảm thấy Pika như 1 công cụ học" can be fixed by reducing parent-assigned lessons | Medium | Medium | Accurate diagnosis from Dịu. But the solution isn't just fewer lessons — it's that Pika's default mode needs to feel like play, not school. If the todo system opens with "Time for your lesson!" instead of "Hey, want to play a game?", the tool perception persists regardless of lesson frequency. | Test: change the daily Pika greeting from lesson-oriented to play-oriented for new users. Measure if "tool perception" (tracked via session type: lesson vs. free-talk ratio) changes. |

#### USABILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| U6 | "PH không biết mà cứ nghĩ chỉ có nói chuyện thôi" — better onboarding will fix the feature discovery problem | Medium | Medium | Onboarding helps, but parents skip tutorials. The real fix may be making features discoverable in-context (Pika suggests activities, app surfaces relevant features at the right time) rather than front-loading education. | A/B: (a) improved onboarding tutorial vs. (b) contextual feature suggestions during first week. Which drives higher feature adoption? |
| U7 | Sample size (5 churned + 3 active) is sufficient to draw reliable conclusions | High | Low | 8 interviews are directionally useful but not statistically significant. 4/5 reporting ASR issues is compelling but could be biased by who agreed to talk. The low response rate (many refused/busy) suggests the actual churned population may have different reasons. | Supplement with: (a) in-app exit survey for all churning users (automated, higher response rate), (b) ASR error log analysis (behavioral data, not self-report). |

### Overall Assessment — P3

**Strengths**: The most valuable proposal for decision-making. Primary research with real churned users — exactly the data the Q1 report flagged as a gap. Dịu's findings independently confirm the Q1 report's top themes (ASR, content difficulty, parent confusion). The insight about "Pika perceived as a tool not a friend" is novel and important.

**Critical concern**: Small sample size (U7). The insights are strong directional signals but should not be treated as definitive. The "guide parents" recommendation (V9) may be harder than it sounds — you're asking parents to change behavior that's driven by their purchase motivation.

**Recommendation**:
1. Treat these findings as high-confidence hypotheses (they align with 150+ Q1 data points), but validate with behavioral data (ASR logs, session analytics)
2. The "Pika as tool not friend" insight should directly inform the onboarding redesign — make the first experience feel like play, not school
3. Scale the interview program: target 20+ churned users for statistically meaningful patterns
4. The parent feedback feature (V10) is low-risk, high-value — build it

---

## P4: Parental Roadmap Aligning

### Summary
Focuses entirely on the parent side of the equation. Two major initiatives: (P1) Parent Activation — ensure parents understand robot capabilities, know how to use features, and receive adequate feedback; (P2) Build a hook UX loop for parents — engage → see child use → receive proof of value → re-engage. Includes app redesign, onboarding revamp, badge system, usage guide, and parent-child engagement moments.

### Assumptions Identified

#### VALUE

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| V13 | "Trải nghiệm học và Retention của những user có bố mẹ hỗ trợ và tham gia sâu vào việc học là tốt hơn" — parent involvement directly improves child retention | Medium | Medium | Likely true based on Q1 data (guided users score 7.5/10 vs. self-guided 6.3/10). However, this creates a dependency: if retention requires parent involvement, scalability is limited. Many parents are too busy (churn data: "con bận đi học thêm và bố mẹ cũng bận"). The ideal product should work independently AND be better with parent involvement — not require it. | Segment analysis: compare D30 retention for (a) high parent-app-engagement vs. (b) low parent-app-engagement families. If (b) always churns, the product has a structural dependency problem that no amount of parent UX can fix. |
| V14 | Parents will engage with a "hook UX loop" (engage → see result → receive proof → re-engage) | Medium | Medium | The loop design is sound in theory (trigger → action → reward → investment). But Q1 and P3 data show parents barely use the app now. The loop assumes parents will open the app frequently enough for the loop to fire. If the trigger mechanism is weak (just push notifications), many parents will ignore it. | Measure current parent app open frequency. If average is <1x/week, the hook loop has no surface area to work. Must first solve: why don't parents open the app? |
| V15 | "Cẩm nang sử dụng robot" (in-app usage guide) will drive feature discovery and adoption | Medium | Low | Usage guides are typically low-engagement content. Parents don't read manuals — they learn by doing or being guided in-context. P3 confirms: parents don't explore the app. A static guide is unlikely to change that. | A/B: (a) in-app usage guide vs. (b) contextual tooltips + proactive Pika suggestions during first 7 days. Which drives higher feature adoption? |
| V16 | A badge system and parent-set rewards will motivate children to use Pika more | Low | Medium | Gamification can work for children. Customer check-up data shows kids like earning stars and diamonds. However, extrinsic motivation (badges, rewards) can undermine intrinsic motivation (genuine curiosity about Pika). If children only engage for badges, usage drops when novelty of badges wears off. | Track: do children who earn badges increase session frequency? Does the effect persist after 2 weeks, or does it decay? |
| V17 | "Bố mẹ treo thưởng thực tế cho các thành tựu" — parents will actively set up real-world rewards tied to Pika achievements | High | Low | This assumes parents will (a) open the app regularly, (b) configure rewards, (c) follow through on delivering them. Current data shows most parents barely use existing app features. Adding a rewards configuration layer on top of an already underused app is unlikely to get traction beyond the most engaged ~10% of parents. | Survey parents: "Would you set up real-world rewards for Pika achievements? How often would you check?" If intent is <30%, deprioritize. |

#### USABILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| U8 | The proposed parent activation 3-phase model (Nhận biết → Dùng thử → Hình thành thói quen) can happen within the first week | High | Low | The activation model is theoretically sound but ambitious. Parents need to: (1) understand all features, (2) try them, (3) form habits — all within the same window where the child is hitting the excitement cliff (Day 3-4). If the child loses interest before the parent is activated, the parent activation becomes moot. | Critical path analysis: does child activation or parent activation need to happen first? If child engagement drops by Day 4, parent activation by Day 7 is too late. **Child engagement must be secured before parent activation loop can work.** |
| U9 | Redesigning onboarding to show "use cases instead of features" will significantly improve activation | Low | Medium | Good UX principle. Use-case framing is better than feature listing. However, onboarding redesign alone won't overcome the core product issues (ASR, content difficulty). If the onboarding says "Pika helps your child practice English!" but the child's first English experience is frustrating, the onboarding created an expectation that the product failed to meet. | Test: improved onboarding + current product vs. current onboarding + improved product (ASR fix + Starter level). Which group retains better at D7? Hypothesis: the product improvement group wins. |
| U10 | "Refactor home dashboard" will increase parent engagement with the app | Medium | Medium | Dashboard redesign is necessary (current UX complaints are real) but not sufficient. The dashboard can be beautiful, but if the content on it isn't compelling (no meaningful reports, no clear value proof), parents still won't return. Reports/feedback content must exist before the dashboard is optimized. | Ship basic daily report first (even with ugly UX), measure if parents engage with the content. If yes, then redesign the dashboard. If no, the problem isn't UX — it's content. |

#### VIABILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| B3 | All proposed initiatives (L0 app redesign + L1 onboarding + L1 dashboard + L1 badge system + L1 parent rewards + L2 usage guide + L2 learning features) can be executed within H1 | Very High | Very Low | This is 7+ initiatives across design, engineering, and content. The proposal doesn't prioritize — everything is presented as L0/L1/L2 but even the "L0" (app redesign/refactor) is a major effort. Combined with P1's V2 features and P2's content optimizations, the total scope far exceeds any realistic team capacity for 3 months. | Force-rank: if you could only ship 2 of these 7 initiatives before July 1, which 2 would have the most impact on the 15% → 35% renewal goal? (Hypothesis: daily report + onboarding redesign) |
| B4 | Investing heavily in the parent experience will improve retention more than investing in the child experience | High | Medium | This is the core strategic bet of P4. The logic is: "if parents are activated and see value, they'll keep the subscription." But the Q1 data shows children drive usage — if the child stops using Pika, no amount of parent app polish will save the subscription. **The child experience is upstream of the parent experience.** | Correlation analysis: is D30 retention better predicted by (a) child daily active minutes or (b) parent app opens per week? If (a), fix child experience first. |

#### FEASIBILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| F6 | "Chứng minh qua thời gian dài — trajectory" (long-term value proof via reports) can be generated with current data infrastructure | Medium | Medium | Showing "con đã đi ngủ đúng giờ hơn trong tháng qua" requires longitudinal data tracking, habit compliance scoring, and trend analysis. Does the current backend capture this data? If not, the reporting layer needs a data infrastructure investment first. | Audit: what data points does Pika currently log per session? Is there enough to generate meaningful weekly/monthly progress reports? |
| F7 | The hook loop can generate meaningful "instant proof" (Lv1: "Pika nhắc con đi ngủ, con đã chào Pika để đi ngủ luôn") | Medium | Low | This requires Pika to reliably detect and report specific child behaviors in real-time. Current Pika can't reliably understand what children say (ASR issues). If Pika reports "con đã chào Pika" when the child actually said something else, the proof is false and trust erodes. **Accurate reporting depends on fixing ASR first.** | Test: compare Pika's session summary accuracy against a human reviewer for 50 sessions. If agreement rate <80%, the reporting will mislead parents. |

### Overall Assessment — P4

**Strengths**: The most structured and systematically designed proposal. Correctly identifies that parent activation is a key lever for renewal (parents are the buyers). The hook loop model (engage → see → prove → re-engage) is well-reasoned. The focus on "chứng minh giá trị" (proving value) is directly aligned with KR3 (60% parents willing to renew).

**Critical concern — the chicken-and-egg problem**: P4 invests heavily in the parent experience, but the parent experience depends on the child experience working. The hook loop needs content to report on ("Hôm nay con học được 5 từ mới"), but if learning sessions are broken (ASR failures, content too hard), there's nothing good to report. **You can't build a compelling parent dashboard on top of a broken child product.** The proposal's dependency on other teams fixing the child experience is implicit but critical.

**Second concern — scope**: 7+ initiatives without clear prioritization or sequencing. The L0/L1/L2 labels don't map to a timeline. With 3 months to July 1, only 2-3 of these can ship properly.

**Recommendation**:
1. **Sequence**: Fix child experience first (ASR + beginner content) → Then build daily report (the minimal "proof of value" for parents) → Then redesign onboarding → Then dashboard + badges
2. **The daily report is the highest-ROI parent feature**: It's the minimum viable "proof of value" that drives renewal intent. Ship this before anything else on the parent side.
3. **Deprioritize for H1**: Badge system (V16), parent real-world rewards (V17), and the usage guide (V15). These are nice-to-have but won't move the 15% → 35% renewal needle if the core child experience isn't fixed.
4. **The onboarding redesign (U9) should ship alongside the Starter level + fun-first first week** — don't redesign onboarding for the current broken product; redesign it for the improved product.

---

## P5: Robot Roadmap — Q1 (Feature Timeline)

### Summary
An execution roadmap spanning February–April 2026 across 10 pillars: Orchestrator (re-opening, transitions, in-session requests), Buddy Talk (memory, personality, topics), Parental Control (custom lessons, notifications, remote control), Gamification (ranking, badges, virtual gifts), Onboarding (parent guide, first lessons/talks), Learning Design (pronunciation, assessment, adaptive learning, embedded English in Talk), Content Production (Pre-A1 through B1), Core AI & Tech (STT, TTS, cost, scale, wakeword), Extended Value (parent/child assistant, STEM, social sciences, other languages), and Product Marketing (virtual Pika for trials).

### Assumptions Identified

#### VALUE

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| V18 | All 10 pillars are equally important and should be developed in parallel | Very High | Very Low | This is the roadmap's biggest risk. 10 pillars × multiple features per pillar = 30+ workstreams. Q1 data shows 2-3 problems account for ~80% of churn (ASR, beginner content, independent engagement). Spreading resources across all pillars means none get fixed deeply enough to move the retention needle. The roadmap treats everything as "Iterate" or "RnD" without clear prioritization of what matters most for the 15% → 35% renewal goal. | Force-rank: which 5 features on this roadmap, if shipped perfectly, would have the most impact on D7 retention? Focus there. |
| V19 | "Extended Value Proposition" (STEM, social sciences, other languages) should be developed in Q1 alongside core English fixes | High | Low | The roadmap shows STEM content pipeline and "Social sciences v1" in W4/Feb–W1/Mar, while Core AI (STT/TTS) has no timeline at all. This means new subjects are being built before the speech technology that powers them is fixed. Q1 data: parents bought Pika for English, English doesn't work yet, and now resources are going to Math/History/Korean. One churned parent said explicitly: "Pika giải sai" about homework help. | Delay all Extended Value until Core AI (STT) quality reaches a baseline threshold. Track: do parents who see English improvement organically request other subjects? |
| V20 | "Ranking — cơ chế xếp hạng leo rank" will incentivize children to return | Medium | Medium | Competitive ranking can motivate older children (9-12) but may discourage younger children (5-7) who consistently rank low. The Pre-A1 segment (highest churn risk) would likely rank lowest, potentially accelerating their disengagement rather than preventing it. | If implemented, segment by age/level. Don't show cross-level rankings. Test with A1+ children first. |
| V21 | "Virtual gift-exchange" and "Badge" systems will improve retention | Medium | Low | Gamification features are marked as "RnD" with no timeline — meaning they're ideas, not committed. The risk is that they're investigated in parallel, consuming design/research bandwidth that could go toward higher-impact work (e.g., researching why the first-week experience fails). | Only pursue after D7 retention improves to >60%. Gamification amplifies a working product; it can't fix a broken one. |
| V22 | "Embedded English practice in Talk mode" (learning through casual conversation) will be more effective than structured lessons | Medium | Medium | This is actually one of the most promising ideas on the roadmap — it aligns with Q1 data showing free-talk is the #1 engagement driver while structured lessons cause frustration. If English learning can be woven into the conversations children already enjoy, it could solve the "Pika feels like a tool not a friend" problem (P3 insight). But the risk is execution: embedding grammar/vocab into natural chat without making it feel forced. | A/B: children using embedded-English Talk mode vs. standard Learn mode. Compare vocabulary retention AND session enjoyment. |

#### USABILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| U11 | "First lessons — các bài học đầu tiên khớp trình độ hơn" will solve the early churn problem | Medium | Medium | Correctly identified as a priority (v2 in W3/Feb). But "khớp trình độ hơn" is vague — does this mean easier Pre-A1? A new Starter level? Better assessment? The roadmap also shows "Assessment test — đẩy bài test đầu vào lên app" but as a separate item. These are deeply linked: you can't match level without first assessing level accurately. | Ship assessment test BEFORE or WITH the first-lesson redesign. Measure: do children who take the assessment test have better D7 retention (because they're matched to the right level)? |
| U12 | "To-do list customization — Research tập user có nhu cầu customize" is a necessary research item | Low | Medium | Low-risk item. But it's marked without a timeline, suggesting it may languish. P4's analysis suggests parents already struggle with the default todo flow — customization adds complexity on top of a confusing base. | Research is fine, but keep scope small: 5-10 parent interviews about todo usage. Don't build customization until the default flow is proven to work. |
| U13 | The "Parental guide — tối ưu luồng dẫn dắt trên app" (v2 in W1/Mar) will be delivered on a working product | Medium | Medium | If parental onboarding is redesigned in W1/Mar but Core AI (STT) fixes have no timeline, the guide will onboard parents to a product with known broken speech recognition. The parent guide creates expectations ("Pika helps your child practice English!") that the product can't deliver, which actually worsens disappointment. | Sequence: ship meaningful product improvements first (even small ones) → then redesign onboarding to showcase the improved product. |

#### VIABILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| B5 | The roadmap is achievable with current team capacity | Very High | Very Low | 30+ features across 10 pillars in ~12 weeks. Even with "v1" scoping, this is an extremely ambitious plan. The roadmap shows items in W3-W4/Feb that aren't checked off, and the March-April columns are mostly empty — suggesting the team is already behind schedule. No items are explicitly deprioritized or cut. | Retrospective: how many of the W1-W4/Feb items actually shipped on time? If <50%, the March-April plan needs to be cut by half. |
| B6 | "Other Language (Tiếng Trung / tiếng Hàn) — Ghép model tiếng Hàn / Anh" (W2/Feb) is worth pursuing now | High | Very Low | Adding Korean/Chinese language support while English — the core product — has fundamental ASR and content issues is a significant misallocation of resources. There is zero Q1 demand data for other languages (only 2 anecdotal Facebook comments about Chinese). This is a classic "shiny new feature" distraction from fixing the core. | Cut entirely from H1. Revisit when English renewal rate hits 35% target. |
| B7 | "AI Cost" and "Scale CCU" items (Core AI) having no timeline is acceptable | High | Medium | These operational items are listed without any schedule. If AI cost isn't optimized, scaling could become financially unsustainable. If CCU capacity isn't planned, a successful marketing push could crash the system. These are infrastructure foundations that should be scheduled, not left open-ended. | Assign specific sprint targets for AI cost reduction and CCU capacity planning. |

#### FEASIBILITY

| # | Assumption | Risk | Confidence | What Could Go Wrong | How to Test |
|---|-----------|------|------------|---------------------|-------------|
| F8 | "Adaptive learning logic — thiết kế cơ chế tạo bài học củng cố kiến thức" (RnD, v1 in W1/Mar) can be designed and validated in one sprint | High | Low | Adaptive learning is a complex system requiring: performance data tracking, knowledge gap identification, dynamic content generation, and pedagogical validation. "v1" of an adaptive system is still a significant engineering and learning design effort. Shipping a poorly designed adaptive system could push wrong content to children, worsening the experience. | Scope "v1" extremely tightly: adaptive = "if child fails a word 3 times, repeat it next session." Don't attempt full adaptive logic in one sprint. |
| F9 | "Memory — top high-value use cases: nhớ memory trong ngày, memory người thân, chủ động follow-up events" can work reliably | High | Low | As flagged in P1 analysis (U3), memory persistence is currently broken. The roadmap shows Memory as v2.1 (W3/Feb) and v2.2 (W1/Mar), suggesting it's being iterated. But if the fundamental memory architecture doesn't persist across restarts, v2.1 and v2.2 are built on a broken foundation. | Before shipping v2.2: run reliability test. If memory fails >5% of the time across restarts, fix architecture before adding high-value use cases. |
| F10 | "STT" (Speech-to-Text) having no timeline means it's not being prioritized | Very High | N/A | This is the most alarming item on the entire roadmap. STT is listed under "Core AI & Tech" with **no timeline, no version, no description**. Yet STT (ASR/speech recognition) is the #1 problem across all data sources — 35+ Q1 mentions, 4/5 churned users, every proposal acknowledges it. The roadmap implicitly assumes either (a) STT will be fixed by someone else, or (b) it doesn't need a timeline. Both are dangerous. | **Assign STT a P0 timeline immediately.** This is the single most impactful item that's missing from the roadmap's schedule. |

### Overall Assessment — P5

**Strengths**: Comprehensive coverage across all product areas. Shows the team is thinking about the full system (not just one pillar). The "Iterate" vs. "RnD" distinction is useful for distinguishing quick improvements from exploratory work. Some items are well-aligned with Q1 insights: first-lesson redesign, pronunciation assistant, onboarding guide.

**Critical concerns**:

1. **STT has no timeline (F10)**: The #1 user complaint, confirmed across 4 data sources and 4 team proposals, is not scheduled. This is the single most important gap in the roadmap.

2. **No prioritization across pillars**: 10 pillars are treated equally. The roadmap needs a forcing function: "Which 3 pillars drive 80% of the retention improvement?" (Answer from Q1 data: Core AI/STT, Learning Design/Content, Onboarding.)

3. **Extended Value too early (V19, B6)**: STEM subjects and Korean/Chinese language are being developed while English fundamentals are broken. This is resource dilution.

4. **Behind schedule**: Feb items without completion marks and empty March-April columns suggest the team is already overcommitted.

**Recommendation**:
1. **Add STT to the roadmap with a W1/Mar or W2/Mar target** — even a "lenient mode" interim fix
2. **Cut or defer**: Other Languages (B6), Virtual gift-exchange, Badge (V21), STEM/Social Sciences content for H1
3. **Elevate**: First lessons + Assessment test (U11) should be paired and fast-tracked
4. **"Embedded English in Talk" (V22) is the sleeper hit** — align it with P2's Buddy Talk integration work. This could be the breakthrough that makes learning feel like play instead of school

---

## Cross-Proposal Alignment Matrix

### Where proposals agree (high confidence — act on these)

| Theme | P1 | P2 | P3 | P4 | P5 | Q1 Report | Action |
|-------|----|----|-----|----|----|-----------|--------|
| ASR is broken, #1 problem | Implicit | Yes | Yes (4/5 churned) | Implicit | Listed, **no timeline** | 35+ mentions | **Fix immediately. P5 must schedule STT.** |
| Beginner content too hard | Implicit | Mentioned | Yes | Implicit | Yes (First lessons v2) | 30+ mentions | **Build Starter level** |
| Parents don't understand product | Yes | Yes (D1→D7) | Yes | Yes (core thesis) | Yes (Parental guide v2) | 12+ mentions | **Redesign first-week experience** |
| Parents need proof of value | Implicit | Implicit | Yes | Yes (hook loop) | Yes (Notification) | Yes | **Build daily/weekly report** |
| Personalization/memory matters | Yes (core) | Yes (Buddy Talk) | Implicit | Implicit | Yes (Memory v2.1/2.2) | Yes | **Fix memory reliability first** |
| Pronunciation correction | Implicit | Yes | Yes | Implicit | Yes (Pron. assistant) | 20+ mentions | **Iterate — but ASR comes first** |

### Where proposals diverge (validate first)

| Tension | P1 | P2 | P3 | P4 | P5 | Risk |
|---------|----|----|-----|----|----|------|
| **What to fix first** | Long-term vision (Layers A-D) | Learning content + Buddy Talk | ASR + content level matching | Parent activation + hook loop | Everything in parallel (10 pillars) | P2+P3 align on "fix child basics"; P1+P4 lean "build new systems"; P5 tries all at once |
| **Who drives retention** | Both | Child (content) | Child (ASR + content) | Parent (activation) | Implicit: all equal | Q1 data: child is upstream. **Child experience is prerequisite.** |
| **Scope** | Very broad (4 layers) | Focused (4 items) | N/A (research) | Broad (7+ initiatives) | Very broad (10 pillars, 30+ items) | P1, P4, P5 risk overextension. P2 is most realistic. |
| **Buddy Talk role** | Emotional attachment | Learning reinforcement | Kids like free-talk | Not addressed | Both: personality + embedded English | P5's "Embedded English in Talk" could bridge fun vs. learning tension |
| **Parent engagement** | "Co-creator" (high) | "Observer" (medium) | "Confused user" (low) | "Active hook loop" (high) | Mixed: custom lessons + notifications | P3's "confused user" matches reality best |
| **Expand to new subjects/languages now?** | Yes (Layer B) | No (focus on learning) | No (fix English) | Not addressed | Yes (STEM, Korean, Chinese in Q1) | **No. English isn't working. Defer to H2.** |

---

## Consolidated Risk Ranking

Across all proposals, ranked by danger to H1 goals:

| Rank | Assumption | Source | Risk | Why It's Dangerous |
|------|-----------|--------|------|-------------------|
| 1 | **STT/ASR — the #1 problem — has no timeline on the roadmap** (F10) | P5 | Very High | Every data source and every proposal acknowledges ASR is broken. The execution roadmap doesn't schedule fixing it. This is the single biggest gap. |
| 2 | **The team can execute 10 pillars / 30+ features AND fix V1 basics in 3 months** (B1, B3, B5) | P1, P4, P5 | Very High | If capacity is spread across everything, nothing ships well by July 1. P5's Feb items already appear behind schedule. |
| 3 | **Functional dependence will form before children lose interest** (V2) | P1 | High | Excitement cliff at Day 3-4 kills engagement before dependence can form |
| 4 | **Parent activation can succeed while child experience is broken** (B4) | P4 | High | No compelling data for reports if sessions are broken. Parent loop has nothing to loop on. |
| 5 | **Expanding to STEM/Korean/Chinese now is worthwhile** (V19, B6) | P1, P5 | High | English isn't working. Resources diverted to new subjects/languages dilute the fix effort. Zero validated demand. |
| 6 | **D1→D7 churn is caused by disconnected todo flow** (U5) | P2 | High | Probably wrong — Q1 + P3 data points to content difficulty + ASR |
| 7 | **Memory/personalization works reliably** (U3, F1, F9) | P1, P5 | High | Current evidence says it doesn't. P5 is building Memory v2.1/v2.2 on a broken foundation. |
| 8 | **Parent activation 3 phases can happen within first week** (U8) | P4 | High | Child may already be disengaged by the time parent is "activated" |
| 9 | **Adaptive learning logic can be designed in one sprint** (F8) | P5 | High | Adaptive learning is complex. A poorly designed system pushes wrong content, worsening experience. |
| 10 | **Parents will actively create custom lessons / set up rewards** (V8, V17) | P2, P4 | Medium | Most parents barely use existing app features |
| 11 | **8 churned user interviews are sufficient** (U7) | P3 | High | Need larger sample + behavioral data |
| 12 | **Parent education will change pushing behavior** (V9) | P3 | Medium | Contradicts purchase motivation |

---

## Recommended Validation Plan

### This Week (use existing data)

| # | Question | Method |
|---|----------|--------|
| 1 | Is D1→D7 churn caused by todo flow or content/ASR? (U5) | Session logs: compare retention of todo-completers vs. non-completers |
| 2 | Does parent app engagement predict child retention? (B4) | Correlation analysis: parent app opens vs. child D30 retention |
| 3 | What % of parents use "tạo bài" feature? (V8) | Analytics query |
| 4 | What % of ASR failures are "heard wrong" vs. "scored wrong"? (V6) | ASR error log categorization |
| 5 | Does Pika's memory persist across sessions? (U3) | Test 20 devices: restart and check context recall |

### This Sprint (quick tests)

| # | Question | Experiment |
|---|----------|-----------|
| 6 | Will parents read Pika's session feedback? (V10, V14) | Push 1 test summary notification to 100 parents. Measure open rate + click-through. |
| 7 | Can children understand the pronunciation energy bar? (U4) | Paper prototype with 10 kids, 1 day |
| 8 | Does fun-first Day 1 greeting improve child return rate? (V12) | A/B: play-oriented vs. lesson-oriented first interaction |

### Next Sprint (requires build)

| # | Question | Experiment |
|---|----------|-----------|
| 9 | Does a Starter level improve D7 retention for Pre-A1? (P2, P3 aligned) | Build 10-lesson Starter module, test with new cohort |
| 10 | Does improved onboarding or improved product drive retention more? (U9) | A/B: new onboarding + old product vs. old onboarding + new product (ASR fix + Starter) |

---

## Summary Verdicts

| Proposal | Verdict | Key Strength | Biggest Risk | Recommendation |
|----------|---------|-------------|-------------|----------------|
| **P1: V2 Strategy** | Right vision, wrong timing | Strategic north star for long-term | Team can't execute V1 fixes + V2 simultaneously (B1) | Adopt as north star. Phase execution: V1 fixes first → Layer A → Layer D → B/C |
| **P2: Backlog (Long)** | Most actionable now | Directly addresses real pain points. Good self-questioning instinct | D1→D7 todo flow hypothesis may be wrong (U5) | Reorder: ASR → pronunciation logic → Buddy Talk → todo flow. Validate U5 with data first |
| **P3: Interviews (Dịu)** | Best evidence for decisions | Primary research confirming Q1 themes + novel "tool vs. friend" insight | Small sample size (U7) | Scale to 20+ interviews. Build the parent feedback feature (V10). Use "tool vs friend" insight in onboarding redesign |
| **P4: Parental Roadmap** | Strong framework, premature execution | Systematic activation + hook model. Correctly targets parent renewal intent | Child experience is upstream — can't build parent proof on broken child product (B4) | Ship daily report first (highest ROI). Sequence: fix child experience → daily report → onboarding redesign → dashboard. Deprioritize badges and rewards for H1 |
| **P5: Q1 Roadmap** | Comprehensive but unfocused; critical gap on STT | Covers all product areas. "Embedded English in Talk" is a sleeper hit (V22) | STT has no timeline (F10). 10 pillars / 30+ items exceed capacity (B5). New subjects/languages too early (B6) | **Schedule STT as P0.** Cut Korean/Chinese and STEM for H1. Focus 3 pillars: Core AI, Learning Design, Onboarding. Fast-track "Embedded English in Talk" + First lessons redesign. |

### The One Strategic Question All Proposals Must Answer

**If you can only do 3 things before July 1, which 3 move the needle from 15% → 35% renewal?**

Based on this analysis: **(1) Fix ASR for children's voices, (2) Build Starter level for true beginners, (3) Ship daily/weekly parent report proving child progress.** Everything else is important but secondary to these three.

---

*Analysis follows the Identify Assumptions (Existing Product) framework — PM, Designer, and Engineer perspectives across Value, Usability, Viability, and Feasibility risk categories.*
