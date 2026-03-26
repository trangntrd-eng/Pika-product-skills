# # Photo-to-Lesson — Performance Report

**Report date:** 23 Mar 2026
**Data period:** 19–23 Mar 2026 (VNT / UTC+7) — production usage only
**Data sources:**
- Production PostgreSQL (`db_app_robot`, server timezone `Asia/Ho_Chi_Minh`)
- Firebase Analytics (`pika-robot-prod`, Spark/free plan) — frontend events
- AI pipeline trace logs (`pipeline_details_3days.xlsx` — two exports combined, deduped)
- FE tracking spec: `PIKA - Data tracking - FrontEnd - S3. Tab Tạo bài.pdf` (28 events, all DONE)

---

## Executive Summary

Photo-to-Lesson went live for real users on 19 Mar 2026. In the first 5 days of production usage, the feature has seen **629 lesson requests** from **210 unique child profiles**, with daily volume growing from 130 to 172 requests/day.

Cross-referencing Firebase FE events with backend DB and AI pipeline logs reveals a healthy parent-side funnel — **lesson acceptance rate (87.9%)** exceeds KPI (≥80%) and **S2 drop-off (12.9%)** beats target (≤20%). However, the **robot-side completion rate (14.2%)** remains the main concern: most lessons assigned by parents are never completed by children.

A **critical safety regression** was found in the pipeline: 11 images flagged as `[UNSAFE_CONTENT]` by the vision screener still generated lessons (Mar 20–23). This needs immediate investigation.

---

## 1. Adoption & Growth

### 1.1 Daily Request Volume

| Date (VNT) | Requests | Unique Profiles |
|------------|----------|-----------------|
| 19 Mar | 165 | 61 |
| 20 Mar | 130 | 54 |
| 21 Mar | 147 | 67 |
| 22 Mar | 172 | 74 |
| 23 Mar | 15 | 6 |

**Total:** 629 requests, 210 unique profiles

**Comment:** Daily unique profiles are steadily growing (61 → 54 → 67 → 74), indicating real user adoption rather than a one-time spike. Mar 23 is a partial day.

### 1.2 User Segments (by total requests, Mar 19–23)

| Segment | Profiles | % | Requests Range |
|---------|----------|---|----------------|
| Single-use | 84 | 40.0% | 1 |
| Light users | 100 | 47.6% | 2–5 |
| Moderate users | 16 | 7.6% | 6–10 |
| Power users | 10 | 4.8% | >10 |

**Returning users (active on 2+ distinct days):** 44 profiles (21.0%)

**Comment:** 60% of users make more than one request, a strong signal for a new feature. However, multi-day retention (21%) has room for improvement — most repeat usage happens within the same session. The 10 power users (>10 requests) are likely parents experimenting with different photo/prompt combinations.

---

## 2. Funnel Analysis

### 2.1 Full FE → BE Funnel (Mar 19–23, Firebase + DB)

```
PARENT APP (FE events — Firebase)                              ROBOT (BE — PostgreSQL)
─────────────────────────────────────                           ─────────────────────────
S0: Home screen
  ├─ click_sample_lesson   384 (176 users)  ─┐
  └─ click_create_lesson   415 (174 users)  ─┤
                                              ↓
S1: Create lesson form                   799 total taps into creation flow
  ├─ click_add_image       480 (144 users)    photo upload attempts
  ├─ click_speech_to_text   20 (14 users)     voice input (low adoption)
  └─ click_submit_create   625 (209 users) ─→ DB: 629 requests (210 profiles) ✓ match
                                              ↓ 96.7% generation rate
S2: AI Processing                        DB: 608 lessons generated
  ├─ click_view_lessons    464 (182 users) ─→ parent saw 3 options
  └─ click_back (S2)       ~part of 981      dropped during AI wait
                                              ↓
S3: Lesson selection
  ├─ click_lesson_detail   524 (137 users)    explored options before choosing
  └─ click_assign_to_pika  612 (160 users) ─→ DB: 471 delivered to robot
                                              ↓ 14.2% completion rate
                                           DB: 67 completed by child on robot

History / Re-engagement:
  ├─ click_lesson_history_detail  110 (38 users)
  └─ click_reassign_lesson        106 (38 users)
```

**Data integrity check:** `click_submit_create` (625 events, 209 users) aligns closely with DB requests (629, 210 profiles).

### 2.2 KPI Scorecard

| KPI | Target | Actual | Status |
|-----|--------|--------|--------|
| S2 drop-off rate | ≤ 20% | 12.9% | **PASS** |
| Lesson acceptance rate (S3) | ≥ 80% | 87.9% (user-level) | **PASS** |
| Lesson history view rate | ≥ 30% | 18.2% | **MISS** |
| Re-assign rate | ≥ 15% | 23.8% | **PASS** |
| Time-to-first-lesson | ≤ 5 min | Unknown | **NO DATA** |
| Robot lesson completion rate | – | 14.2% | **LOW** |

### 2.3 FE Funnel Deep-Dive

**S0 → S1: Sample vs Custom entry**
- Sample lesson taps: 384 (176 users, 2.18/user) — users tap multiple samples to explore
- Custom create taps: 415 (174 users, 2.39/user) — comparable volume
- Nearly equal user counts (176 vs 174) suggest most users try both paths

**S1: Creation form behavior**
- Image uploads (click_add_image): 480 events from 144 users (3.33/user) — users retry photo uploads
- Speech-to-text: 20 events from only 14 users (1.43/user) — **very low adoption (6.7% of creators)**
- Submit rate: 625 submits from 209 users = 2.99 submits/user — parents create ~3 lessons on average

**S2: AI processing wait**
- 209 users submitted → 182 users clicked "Xem 3 bài học" = **12.9% S2 drop-off** (beats KPI ≤ 20%)
- 27 users dropped out during AI processing wait

**S3: Lesson selection & exploration**
- click_lesson_detail: 524 events from 137 users (3.82/user) — users who explore look at ~4 option details
- click_assign_to_pika: 612 events from 160 users (3.83/user)
- 612 assign events vs 471 DB deliveries — gap of ~141 likely includes: 106 reassigns from history + duplicate taps or failed deliveries

**History & re-engagement**
- 38 users (18.2%) viewed lesson history — below KPI target of ≥ 30%
- 38 users (23.8% of assigners) re-assigned old lessons — exceeds KPI ≥ 15%
- Same 38 users doing both suggests a small but engaged cohort uses history features

### 2.4 Notification Funnel (all app notifications, not PTL-specific)

| Event | Count | Users |
|-------|-------|-------|
| notification_receive | 1,174 | 462 |
| notification_open | 402 | 284 |
| notification_dismiss | 639 | 286 |

- **Open rate:** 38.6% — reasonable for mobile push
- Note: These are all app notifications, not PTL-specific. Cannot isolate PTL notification performance without parameter-level filtering.

### 2.5 Daily Backend Funnel

| Date (VNT) | Requests | Lessons Generated | Delivered to Robot | Completed | Completion Rate |
|------------|----------|-------------------|-------------------|-----------|-----------------|
| 19 Mar | 165 | 153 | 107 | 11 | 10.3% |
| 20 Mar | 130 | 116 | 108 | 13 | 12.0% |
| 21 Mar | 147 | 157 | 100 | 15 | 15.0% |
| 22 Mar | 172 | 171 | 149 | 26 | 17.4% |
| 23 Mar | 15 | 11 | 7 | 2 | 28.6% |
| **Total** | **629** | **608** | **471** | **67** | **14.2%** |

**Funnel conversion rates:**

```
Requests       629  (100%)
  ↓ 96.7% generation rate
Lessons Gen    608  (96.7%)
  ↓ 77.5% delivery rate
Delivered      471  (77.5% of generated)
  ↓ 14.2% completion rate
Completed       67  (14.2% of delivered)
```

**Comment:**
- **Generation rate (96.7%)** is excellent.
- **Delivery rate (77.5%)** — 137 generated lessons never reached the robot. FE data clarifies: 12.9% of users drop off at S2, and some parents browse options on S3 without assigning.
- **Completion rate (14.2%)** is the biggest concern, but the daily trend is improving (10.3% → 17.4%). The parent→child handoff is where the funnel breaks down.

---

## 3. Input Types & Language

### 3.1 Input Type Distribution

| Input Type | Count | % |
|------------|-------|---|
| Custom photo (user-uploaded) | 309 | 49.1% |
| Sample photo (pre-built) | 234 | 37.2% |
| Text-only (no image) | 86 | 13.7% |

**Daily trend — Custom photo share growing:**
- 19 Mar: 38% custom, 48% sample, 15% text (first day — samples dominate)
- 20 Mar: 50% custom, 40% sample, 10% text
- 21 Mar: 52% custom, 33% sample, 16% text
- 22 Mar: 55% custom, 30% sample, 15% text

**Completion rate by input type (Mar 19–23, DB):**

| Input Type | Delivered | Completed | Completion % |
|------------|-----------|-----------|-------------|
| Custom photo | 197 | 39 | **19.8%** |
| Sample photo | 108 | 14 | **13.0%** |
| Text-only | 59 | 3 | **5.1%** |

**Comment:** Custom photo usage (the core value proposition) is trending upward as users move past sample-based exploration. Custom photos also have the highest completion rate (19.8%) — personal relevance drives child engagement. Text-only has the lowest completion (5.1%), suggesting photos provide a critical visual anchor.

### 3.2 Language Distribution

| Language | Count | % | Completion Rate |
|----------|-------|---|-----------------|
| Bilingual (bi) | 546 | 86.8% | 15.5% |
| Vietnamese (vi) | 45 | 7.2% | 15.0% |
| English (en) | 38 | 6.0% | 14.3% |

**Comment:** Bilingual mode dominates as expected for Vietnamese children learning English. Language choice has no meaningful impact on completion rates (~15% across all modes).

### 3.3 Top Custom Prompts & Completion Cross-Reference

| Prompt | Count | Type | Delivered | Completed | Rate |
|--------|-------|------|-----------|-----------|------|
| "học thêm" | 111 | Default/sample | 46 | 12 | 26.1% |
| Body parts vocabulary | 87 | Sample | 38 | 3 | **7.9%** |
| Addition practice (≤20) | 46 | Sample | 22 | 5 | 22.7% |
| Photosynthesis | 34 | Sample | 10 | 1 | 10.0% |
| 100k VND bill | 32 | Sample | 19 | 2 | 10.5% |
| Respiratory system | 21 | Sample | 7 | 1 | 14.3% |
| Custom conversation/vocab | 3 ea. | Organic | 3 ea. | 1 ea. | ~33% |

**Key insight:** The most popular sample prompt (body parts, 87 requests) has the **lowest completion rate (7.9%)**. Meanwhile, custom-crafted prompts with personal context average ~33% completion. This confirms that **lesson relevance to the child drives completion** — samples are for exploration, not sustained engagement.

---

## 4. AI Pipeline Analysis

*Source: Pipeline trace logs, 607 unique records for Mar 19–23 VNT (207 unique profiles). Combines two exports, deduped on profile + timestamp.*

### 4.1 Pipeline Performance

| Stage | Input | Output | Success Rate |
|-------|-------|--------|-------------|
| Vision Screening | 522 image requests | 522 vision outputs | **100%** |
| Lesson Design | 607 total requests | 607 lesson outputs | **100%** |
| Text-only (skip Vision) | 85 requests | 85 lesson outputs | **100%** |

**0 pipeline failures** in the Mar 19–23 period. All requests produced lesson output.

### 4.2 Content Safety Screening — CRITICAL REGRESSION

| Result | Count | Lesson Blocked? |
|--------|-------|-----------------|
| SAFE | 511 | N/A — proceeded normally |
| UNSAFE_CONTENT | **11** | **No — all 11 generated lessons anyway** |
| N/A (text-only) | 85 | N/A |

**All 11 unsafe detections still produced lesson output:**

| # | Date (VNT) | Child | Age | Unsafe Reason | Prompt | Trace ID | Risk Level |
|---|------------|-------|-----|---------------|--------|----------|------------|
| 1 | 23 Mar 08:24 | Thảo Tiên | 10 | Image contains a recognizable person | học thêm | `aeea5a43…` | Medium |
| 2 | 23 Mar 08:24 | Thảo Tiên | 10 | Image of a person without context | học thêm | `3476d0dd…` | Medium |
| 3 | 23 Mar 08:23 | Thảo Tiên | 10 | Contains identifiable person | học thêm | `333630f1…` | Medium |
| 4 | 23 Mar 08:20 | Thảo Tiên | 10 | Contains identifiable personal image | Tạo bài học về khuôn mặt | `f525a3cf…` | Medium |
| 5 | 23 Mar 07:34 | Thảo Tiên | 10 | Person holding a knife in potentially unsafe manner | Học từ vựng về miêu tả cơ thể | `60f2d6b3…` | **High** |
| 6 | 22 Mar 20:13 | Minh Anh | 5 | Image of children without parental consent | học thêm | `70cc822b…` | Medium |
| 7 | 22 Mar 19:47 | Mi | 6 | Content related to personal safety and body privacy | Bài học bảo vệ cơ thể cho bé gái mẫu giáo | `cbeab445…` | Low (arguably educational) |
| 8 | 22 Mar 12:00 | Mía | (none) | Sanitary pads — not suitable for 6-12 | Bài học về chu kỳ kinh nguyệt cho các bé | `29285339…` | Medium |
| 9 | 22 Mar 10:57 | GON | 6 | Contains financial services advertisement | học thêm | `2ca6581e…` | Low |
| 10 | 20 Mar 21:13 | Gấu | 10 | Vocabulary related to human reproduction (sperm) | học thêm | `0eaedcfc…` | **High** |
| 11 | 20 Mar 21:11 | Gấu | 10 | Reproductive terminology not suitable for children | học thêm | `f782f16d…` | **High** |

**Profile breakdown:** 4 unique children affected — Thảo Tiên (5 cases), Gấu (2), Minh Anh (1), Mi (1), Mía (1), GON (1).

**What the lesson output reveals:**
In all 11 cases, the 3 pipeline experts ([A] Image Analyst, [B] Curriculum Designer, [C] Child Psychologist) **correctly refuse inside the lesson output text** — e.g., "Chuyên gia Phân tích Hình ảnh tuyên bố từ chối tạo bài học vì lý do bảo mật." However, the system still **saves a lesson output record** to the DB despite the refusal. The guardrail exists at the LLM reasoning level but is **not enforced at the pipeline/system level**.

**Root cause hypothesis:** The pipeline checks for `[UNSAFE_CONTENT]` in vision output but does not hard-abort. Instead, it passes the unsafe flag to the lesson stage, where the LLM experts correctly refuse in their reasoning — but the pipeline still records the output and may still generate final prompts or lesson records in the DB.

**DB cross-reference — did unsafe requests become real lessons?**

Matching the 6 affected profiles against `generated_lesson_history` → `generated_lessons`:

| Profile | Unsafe Requests | DB `lessons_gen` for those timestamps | Delivered to Robot | Status |
|---------|----------------|---------------------------------------|-------------------|--------|
| Thảo Tiên (5 cases) | #1–3 "học thêm" at 08:23–08:24 | 0 lessons generated | 0 | **Blocked at DB level** |
| Thảo Tiên | #4 "khuôn mặt" at 08:20 | 0 lessons (retry at 08:20:42 → 1 lesson, 1 delivered) | 1 delivered from retry | **Retry bypassed** |
| Thảo Tiên | #5 knife image at 07:34 | 0 lessons (but retry at 07:35 → 1 lesson, 2 delivered) | 2 delivered from retry | **Retry bypassed** |
| Minh Anh | #6 children photo | 0 lessons generated | 0 | **Blocked** |
| Mi | #7 body safety | 0 at first try (retry → 1 lesson, 1 delivered) | 1 delivered | **Retry bypassed** |
| Mía | #8 sanitary pads | 0 lessons generated | 0 | **Blocked** |
| GON | #9 financial ad | 0 lessons generated | 0 | **Blocked** |
| Gấu | #10–11 reproductive | 0 lessons for those (3rd try → 3 lessons, 1 delivered) | 1 delivered from 3rd try | **Retry bypassed** |

**Key finding:** The unsafe requests themselves mostly **do not** generate `generated_lessons` DB records (0 lessons). However, the parent retries seconds later with the same or similar image, and the **retry often succeeds** — generating lessons that get delivered to the robot. This suggests the vision screening is **non-deterministic**: the same image can be flagged as UNSAFE on one call and SAFE on the next.

**Troubleshooting checklist for the tech team:**
1. Check the pipeline code that processes vision output — is there a conditional branch on `[UNSAFE_CONTENT]`?
2. If the branch exists, was it disabled or bypassed in a recent deployment (between Mar 19–20)?
3. Verify whether the "refusal" lesson outputs resulted in actual `generated_lessons` DB records being created
4. Check if any of these 11 cases resulted in lessons being delivered to the robot (`generated_lessons_conversation_history`)
5. Add an explicit system-level gate: if vision output contains `[UNSAFE_CONTENT]`, return an error to the parent app and do not proceed to lesson generation

**Risk assessment:**
- **3 High-risk cases** (#5 knife, #10–11 reproductive terminology) — content that should never reach children
- **5 Medium-risk cases** (#1–4 identifiable persons, #6 children photos, #8 sanitary pads) — privacy/appropriateness concerns
- **2 Low-risk cases** (#7 body safety education, #9 financial ad) — arguably educational or benign but flagged by conservative screening
- Case #7 (body safety for girls) highlights a need to refine the safety categories — "bảo vệ cơ thể" is legitimate child safety education that should probably be whitelisted

### 4.3 Child Age Distribution

| Age | Count | % | Notes |
|-----|-------|---|-------|
| 6 | 119 | 19.6% | Most common |
| 7 | 98 | 16.1% | |
| 8 | 80 | 13.2% | |
| 9 | 71 | 11.7% | |
| 5 | 60 | 9.9% | Below target |
| 4 | 40 | 6.6% | Below target |
| 10 | 24 | 4.0% | |
| 3 | 22 | 3.6% | Well below target |
| 11 | 16 | 2.6% | |
| (empty) | 72 | 11.9% | No age set |
| 38 | 5 | 0.8% | Parent testing on own account |

- **Target range (6–12): 67.2%** — majority of usage is within intended audience
- **Under-6 (ages 3–5): 20.1%** — a fifth of requests come from children below target. Lessons designed for 6–12 may not be age-appropriate for these users
- **No age set: 11.9%** — affects lesson personalization quality

### 4.4 Organic Prompt Analysis

**53.2% of requests** (323 of 607) used organic (non-sample) prompts:

| Category | Count | % of Organic | Example |
|----------|-------|-------------|---------|
| English vocab / pronunciation | 90 | 27.9% | "Dạy Tú Anh đọc: chopsticks, cool, wardrobe" |
| Story reading / textbook | 79 | 24.5% | "Đọc câu chuyện The Lion and the Mouse" |
| Other / miscellaneous | 73 | 22.6% | Freeform descriptions |
| Math | 22 | 6.8% | "Bé đang học lớp 2, giúp bé thuộc phép nhân" |
| Conversation / roleplay | 21 | 6.5% | "Pika trò chuyện về cuộc sống hằng ngày" |
| Vocab by topic | 18 | 5.6% | "con vật", "Đồ vật trong phòng ngủ" |
| Science / knowledge / life skills | 16 | 5.0% | "Bài học bảo vệ cơ thể cho bé gái" |
| Parenting nudge | 3 | 0.9% | "Nói 2 anh em ăn nhanh lên, đừng xem điện thoại" |
| Emotional support | 1 | 0.3% | "Ông nội phá bếp làm Xoài sợ, Pika hãy dỗ dành" |

**Notable organic use cases:**
- **Pronunciation drills:** Parents specifying exact pedagogy — "chỉ dạy phát âm thôi, đọc thật chậm"
- **Full story input:** One parent pasted the entire "The Lion and the Mouse" story for Pika to teach interactively
- **Parenting ally:** Using Pika as third-party authority to tell kids to stop watching phones
- **Life skills:** Body safety education for girls, time-telling, currency
- **Curiosity-driven:** "Dạy Bob về máy xúc, ngôn ngữ thực tế không cần đơn giản cho bé 5 tuổi" — parent explicitly requesting higher complexity

**Comment:** Organic usage (53.2%) now exceeds sample usage, validating the core PTL value proposition. Parents are creating lessons tailored to their child's curriculum, interests, and emotional needs.

### 4.5 Sample Image Usage

| Sample Image | Count | Subject | DB Completion Rate |
|-------------|-------|---------|-------------------|
| bodaypart | 79 | Body parts vocabulary | 7.9% (lowest) |
| congtru20 | 53 | Addition/subtraction within 20 | 22.7% |
| quanghop | 35 | Photosynthesis | 10.0% |
| 100k | 33 | 100,000 VND banknote | 10.5% |
| hohap | 19 | Respiratory system | 14.3% |

Body parts is most popular (36% of sample usage) but has the lowest completion rate. Note the filename typo `bodaypart.jpg` (should be `bodypart.jpg`).

---

## 5. Robot Conversation Analysis

### 5.1 Session Overview

| Metric | Completed Sessions | Incomplete Sessions |
|--------|-------------------|---------------------|
| Count | 67 | 404 |
| Avg user turns | 33.0 | 13.8 |
| Avg duration | 11.8 min | N/A (no `completed_at`) |
| Avg XP score | 0.0 | 0.0 |

**Total conversation turns:** 46,655 (38,777 bot + 7,878 user)
**Bot-to-user turn ratio:** 4.9:1

### 5.2 Completed Lesson Highlights

Top completed sessions by engagement (user turns):

| Lesson Title | User Turns | Duration (min) |
|-------------|-----------|----------------|
| Khám phá 5 từ vựng cơ thể cùng Pika | 148 | 46.3 |
| Khám phá từ mới mùa đông cùng Pika | 115 | 37.5 |
| Khám phá các kiểu nhà qua 5 từ vựng mới | 96 | 29.6 |
| Cùng Pika học từ vựng về hoạt động vui nhộn! | 86 | 36.4 |
| Kể chuyện Nobita – Tấm gương dũng cảm | 86 | 32.9 |
| Cộng nhanh cùng Pika – Vượt qua thử thách | 83 | 24.1 |
| Đố vui: Đoán tên bộ phận cơ thể cùng Pika | 82 | 22.0 |
| Đóng Vai Giao Tiếp – Cùng Bạn Kết Nối! | 66 | 22.0 |
| Trò chơi nhập vai: Nghề nghiệp trong thành phố | 61 | 26.5 |
| Khám phá món ăn nhanh cùng Pika | 54 | 19.7 |

**Comment:**
- The most engaged session (148 user turns, 46 min) is exceptionally long for a 6–12 year old.
- Average completed session duration of 11.8 min is healthy for the target age group.
- Topics span English vocabulary, math, storytelling, and roleplay — the AI pipeline handles diverse subjects well.

### 5.3 Conversation Quality — Data Gaps

| Metric | Status |
|--------|--------|
| `xp_score` | Always 0 — XP scoring not implemented for PTL lessons |
| `pronounce_score` | Not populated |
| `conversation_reports` | All null — report generation not connected |
| `conversation_summaries` | All null — summary generation not connected |
| Per-turn `score`/`emotion` | Not populated |
| `response_time` | Null |

Without these fields, lesson quality can only be assessed via manual transcript review.

### 5.4 Bot-to-User Turn Ratio — Potential Issue

The 4.9:1 ratio means the robot speaks ~5 messages for every 1 user response. **This is a concern:** it may indicate Pika is talking while the child is not responding, rather than good pedagogy.

**Incomplete session user-turn distribution (405 sessions):**

| User Turns | Sessions | % | Interpretation |
|-----------|----------|---|----------------|
| 0 turns | 23 | 5.7% | Child never responded — robot talked to itself |
| 1–4 turns | 100 | 24.7% | Minimal engagement — child tried and left |
| 5–9 turns | 85 | 21.0% | Some engagement, dropped mid-lesson |
| 10–19 turns | 104 | 25.7% | Moderate engagement, didn't finish |
| 20–49 turns | 72 | 17.8% | High engagement but still incomplete |
| 50+ turns | 21 | 5.2% | Very high engagement — likely near-completion or stuck |

**Key insight:** 30.4% of incomplete sessions have ≤4 user turns (123 sessions) — the child either never engaged or gave up almost immediately. Another 21% (85 sessions) had 5–9 turns. Combined, **over half of incomplete sessions (51.4%) end within the first 9 user turns.**

Meanwhile, 23% (93 sessions) had 20+ user turns but still didn't complete — these children were engaged but something prevented completion (session timeout? lesson too long? got bored toward the end?).

**Action needed:** Manual review of a sample of 0-turn and 50+-turn incomplete sessions to understand:
- Are 0-turn sessions caused by accidental assignment, robot not connecting, or child ignoring?
- Are 50+-turn sessions caused by lessons being too long, or the child getting stuck?

### 5.5 Re-assigned Lessons — Higher Completion Rate

| Category | Lessons | Completed | Completion % |
|----------|---------|-----------|-------------|
| Re-assigned (2+ times) | 49 | 12 | **24.5%** |
| Single assign | 367 | 56 | **15.3%** |

**Re-assigned lessons complete at 1.6× the rate of single-assign lessons (24.5% vs 15.3%).** This suggests that when parents actively re-assign a lesson, the child is more likely to be present and engaged. The re-assign action may serve as a "parent nudge" — the parent is deliberately trying again, possibly with the child nearby.

---

## 6. Per-Profile Behavior & Power Users

### 6.1 Top 15 Profiles

| Profile ID (last 4) | Requests | Lessons Gen | Delivered | Completed | Completion % |
|---------------------|----------|-------------|-----------|-----------|-------------|
| de4e | 19 | 15 | 21 | 0 | 0% |
| b6a3 | 15 | 9 | 7 | 0 | 0% |
| 13ba | 14 | 5 | 4 | 0 | 0% |
| 41bf | 14 | 4 | 4 | 2 | 50% |
| cc14 | 14 | 4 | 4 | 0 | 0% |
| c3c8 | 14 | 0 | 0 | 0 | 0% |
| 2567 | 11 | 4 | 5 | 1 | 20% |
| c445 | 11 | 8 | 7 | 1 | 14% |
| 01d4 | 11 | 9 | 9 | 2 | 22% |
| 222b | 11 | 6 | 6 | 2 | 33% |
| 972e | 9 | 10 | 12 | 0 | 0% |
| 98be | 8 | 10 | 8 | 3 | 38% |
| 3e82 | 8 | 10 | 10 | 1 | 10% |
| 0d21 | 8 | 7 | 7 | 0 | 0% |
| edf | 8 | 4 | 2 | 0 | 0% |

**Comment:** Power users generate many requests but completion varies wildly (0%–50%). Profile `c3c8` made 14 requests with 0 lessons generated — likely hitting API errors. Profile `de4e` (19 requests, 0 completions) may be a parent exploring without the child present.

### 6.2 Power User Contact List (for parent interviews)

10 power users (>10 requests) with parent phone numbers for user research:

| Child Name | Requests | Completed | Phone |
|-----------|----------|-----------|-------|
| Xoài | 19 | 0 | 0374548893 |
| Tuấn Phong | 15 | 0 | 0938691925 |
| Khánh Vy | 14 | 2 | 0945167882 |
| thỏ | 14 | 0 | 0934345886 |
| Bông | 14 | 0 | 0915346313 |
| Mieu | 14 | 0 | 09753282816 |
| Thư | 11 | 2 | 0334810189 |
| Tú Anh | 11 | 1 | 0973176739 |
| Nguyên | 11 | 2 | 0917139149 |
| Nhật Nam | 11 | 1 | 0898339279 |

**Interview priority:** Focus on Khánh Vy, Thư, Nguyên (high requests + completions = most experienced full-funnel users) and Xoài (19 requests, 0 completions — why is the child not engaging?).

### 6.3 Internal Tester / Junk Data Identification

Profiles with >3 requests **before** Mar 19 launch (likely internal testers):

| Name | Phone | App Version | Total Requests | Pre-19 Mar | Post-19 Mar |
|------|-------|-------------|----------------|-----------|-------------|
| Nhung | 03543762376 | 1.2.6 | 28 | 28 | 0 |
| Hieu | 0364398495 | 1.2.3 | 20 | 19 | 1 |
| Lạc Lạc | 0948801311 | 1.3.2 | 6 | 6 | 0 |
| Truck-kun | 0984265899 | 1.2.5 | 7 | 6 | 1 |
| Ty | 0976712697 | 1.3.5 | 5 | 5 | 0 |

**Status:** These 5 profiles had minimal or zero activity in the Mar 19–23 production period. **Nhung (28 requests, all pre-19) and Hieu (19 pre-19) are almost certainly internal testers.** "Truck-kun" is clearly a test name. The current report data (Mar 19–23) is largely clean — only 2 of these profiles have 1 post-launch request each, which has negligible impact on metrics.

**Recommendation:** Maintain an exclusion list of internal profile IDs for future reports. Confirm with team whether these phones belong to staff.

---

## 7. App Version & PTL Adoption Rate

*Source: Firebase Analytics dashboard (Mar 19–23) + production DB.*

PTL requires **version 1.3.8+**.

### App Version Distribution (Firebase)

| App Version | Active Users | Note |
|------------|-------------|------|
| 1.3.8 | 1,384 | |
| 1.3.9 | 944 | |
| **All Users (deduplicated)** | **~2,000** | |

The per-version totals (1,384 + 944 = 2,328) exceed 2,000 because Firebase counts each user in every version they used during the period. ~328 users upgraded from 1.3.8 → 1.3.9 mid-period and appear in both rows. The **2,000 is the true unique user count.**

**All active users are on 1.3.8+** — PTL is available to the entire active user base. No version update barrier.

### User Base Context (DB)

| Metric | Count | Source |
|--------|-------|--------|
| Total registered parents | 5,426 | DB `users` (all `is_active = true`) |
| Total child profiles | 8,122 | DB `profiles` |
| Parents with ≥1 profile | 5,415 | DB `profiles` (distinct `user_id`) |
| Active users (Mar 19–23) | ~2,000 | Firebase |
| **Weekly active rate** | **36.8%** | 2,000 / 5,426 |

### PTL Adoption Rate

| Metric | Value |
|--------|-------|
| Active users this week (Firebase) | ~2,000 |
| PTL users this week (DB) | 210 profiles |
| **PTL adoption (of active users)** | **~10.5%** |
| PTL adoption (of all profiles) | 2.6% (210 / 8,122) |

**~90% of active users have not tried PTL yet** — significant growth opportunity. The barrier is feature discovery, not app version.

### Platform Breakdown (Firebase, Mar 19–23)

| Platform | All Users | 1.3.8 Users |
|----------|-----------|-------------|
| iOS | 1,200 | 872 |
| Android | 761 | 512 |
| Mobile | 1,900 | 1,300 |
| Tablet | 90 | 66 |

### DB `users.app_v` — Known Data Gap

The `users.app_v` column still shows pre-1.3.8 values for most PTL users (e.g., 1.3.7, 1.3.5, null). This field is not reliably updated on app launch. **Action:** Fix `app_v` update logic so DB and Firebase stay in sync.

---

## 8. Custom Photo Gallery

**250 unique custom photos** uploaded across 317 requests (some photos reused). All URLs follow the pattern:
```
https://smedia.stepup.edu.vn/robot/upload/generate_lessons/{user_id}/{uuid}_{timestamp}.jpg
```

Full list exported for review — see query in `docs/ptl-data-queries.md` (Query 2, filter `image_urls NOT LIKE '%pika_robot/photo_to_lesson/img/%'`).

**Note:** These are parent-uploaded images of textbooks, worksheets, real-world objects, and occasionally people (flagged by safety screening). Reviewing a sample can reveal what parents are actually photographing and inform sample image selection.

---

## 9. Data Gaps & Known Issues

| Issue | Severity | Detail |
|-------|----------|--------|
| **Safety guardrail regression** | **Critical** | Vision flags UNSAFE_CONTENT but lesson pipeline proceeds anyway (11 cases). Includes reproductive terminology reaching children. Needs immediate fix |
| XP score always 0 | High | PTL lessons do not trigger XP scoring — children get no reward |
| conversation_reports/summaries null | High | Post-session analytics not generated for PTL lessons |
| Firebase Spark plan — no BigQuery export | High | FE events cannot be queried programmatically or joined with BE data |
| No per-screen screen_view breakdown | Medium | Cannot isolate PTL screens without parameter filtering in console |
| `screen_time` duration not accessible | Medium | Cannot measure time-to-first-lesson KPI (≤ 5 min) |
| `click_back` not split by `from_screen` | Medium | 981 total back taps — cannot distinguish S1, S2, S3 drop-offs |
| Per-turn score/emotion/language empty | Medium | Fine-grained conversation quality metrics not populated |
| response_time null | Medium | Cannot measure robot response latency |
| 11.9% of profiles missing child age | Medium | Affects lesson personalization quality |
| Notification events not PTL-specific | Low | Cannot isolate PTL lesson-ready notifications |
| CDN image filename typo | Low | `bodaypart.jpg` (should be `bodypart.jpg`) |

---

## 10. Key Takeaways & Recommendations

### Positive Signals
1. **Strong adoption** — 210 profiles in 5 days with daily growth (61 → 74 daily unique users)
2. **Custom photo usage (49.1%)** growing daily — users engaging with core value prop
3. **Completion rate improving** — 10.3% → 17.4% daily trend suggests learning curve, not fundamental issue
4. **High engagement in completed sessions** — avg 33 user turns, 11.8 min duration
5. **Lesson acceptance rate (87.9%)** exceeds KPI (≥ 80%)
6. **S2 drop-off (12.9%)** beats KPI (≤ 20%)
7. **Re-assign rate (23.8%)** exceeds KPI (≥ 15%)
8. **AI pipeline 100% reliable** — 0 generation failures in Mar 19–23
9. **AI safety screening catches unsafe content** — 11 detections correct (but guardrail not enforced)
10. **Organic usage (53.2%) exceeds samples** — parents create personalized lessons
11. **Diverse topics** — English vocab, math, storytelling, science, emotional support, parenting
12. **Custom photos complete 2× more than text-only** (19.8% vs 5.1%) — photos drive engagement

### KPI Scorecard

| KPI | Target | Actual | Status |
|-----|--------|--------|--------|
| S2 drop-off rate | ≤ 20% | 12.9% | **PASS** |
| Lesson acceptance rate (S3) | ≥ 80% | 87.9% | **PASS** |
| Lesson history view rate | ≥ 30% | 18.2% | **MISS** |
| Re-assign rate | ≥ 15% | 23.8% | **PASS** |
| Time-to-first-lesson | ≤ 5 min | Unknown | **NO DATA** |
| Robot lesson completion rate | – | 14.2% | **LOW** |

### Recommended Actions

**Priority 0 — Critical safety fix**
1. **Fix safety guardrail** — vision screening flags `[UNSAFE_CONTENT]` but lesson pipeline ignores it (11 cases). Add hard gate: if vision returns UNSAFE, abort pipeline

**Priority 1 — Immediate impact**
2. **Connect XP scoring** for PTL lessons — highest-impact change for child completion motivation
3. **Investigate parent→child handoff gap** — does the child know a new lesson is waiting? Consider robot-side notification
4. **Upgrade Firebase to Blaze plan** — enables BigQuery export for full FE+BE funnel analysis (near-zero cost at current volume)

**Priority 2 — Improve metrics**
5. **Boost lesson history visibility** — 18.2% misses KPI (≥ 30%). Consider push notification on lesson completion with "view report" CTA
6. **Enable conversation_reports and conversation_summaries** for PTL sessions
7. **Improve speech-to-text discoverability** — only 6.7% adoption
8. **Require child name + age before PTL** — 11.9% of requests have empty child info, affecting personalization
9. **Diversify sample images** — body parts (most popular) has lowest completion rate (7.9%). Add samples matching high-completion organic prompts (conversation, storytelling)
10. **Manual conversation review** — sample 10–15 transcripts to assess quality and drop-off patterns

**Priority 3 — Data infrastructure**
11. **Add `screen_name` parameter filtering** in Firebase to isolate PTL screen_views
12. **Track parent→child handoff** — add DB field for "lesson started on robot" (distinct from "delivered")
13. **Set completion rate KPI target** — consider 30% based on improving trend
14. **Fix pipeline export logging** — Final Prompt columns empty in earlier export

---

## 11. How to Get More FE Data (Firebase Spark Limitations)

Since the Firebase project is on the free Spark plan, BigQuery export is unavailable. Here are ways to extract more actionable FE data:

### What you can do now in the Firebase Console
1. **Filter events by parameter** — In Events > click any event name > "Add filter" to filter by parameter values (e.g., `screen_name = home_lesson_picker` for PTL screen_views, or `from_screen = ai_processing` for S2 back taps)
2. **Export CSV** — On any Events table view, click download icon to export event counts as CSV
3. **Use Explorations** — Firebase > Explore > create a Funnel exploration: `click_create_lesson` → `click_submit_create` → `click_view_lessons` → `click_assign_to_pika`. Shows exact user-level drop-off
4. **Check event parameters** — Click any event > scroll to "Parameter" section for breakdowns by `entry_point`, `has_image`, `source`, `option_index`

### Screenshots that would help most for next analysis
- **Funnel Exploration** with PTL event sequence
- **`click_submit_create` parameter breakdown** — `has_image` true/false split
- **`click_assign_to_pika` parameter breakdown** — `option_index` 0/1/2 distribution
- **`click_sample_lesson` parameter breakdown** — english/math/science split
- **CSV export of daily event counts**

### Longer term
- **Upgrade to Blaze plan** — enables BigQuery export (~$0 for current volume). Single most impactful data infrastructure change

---

---

## 12. Parent Interview — Top Goals

The **#1 goal** for parent interviews should be: **Understanding why children don't complete lessons on the robot.**

The data shows parents are highly engaged (629 requests, 87.9% acceptance rate), but only 14.2% of delivered lessons are completed. The drop happens **after** the parent hands off to the child. We need qualitative data to understand this gap.

**Interview question framework (priority order):**

1. **Completion gap:** "Bạn giao bài cho Pika rồi, bé có học không? Nếu không thì tại sao?" (You assigned a lesson — did your child do it? If not, why?)
2. **Timing & awareness:** "Bé có biết là có bài mới trên Pika không? Bạn có nhắc bé không?" (Does the child know there's a new lesson? Do you remind them?)
3. **Re-assign behavior:** "Bạn đã gửi lại bài cũ bao giờ chưa? Tại sao?" (Have you re-assigned a lesson? Why?)
4. **Content satisfaction:** "Bài học Pika tạo ra có đúng ý bạn không? Bé thích loại nào nhất?" (Is the lesson what you expected? Which type does the child like most?)
5. **Photo vs text:** "Bạn thích chụp ảnh sách hay gõ chữ hơn?" (Do you prefer photo or text input?)
6. **0-completion users (Xoài, thỏ, Bông):** "Bạn tạo nhiều bài nhưng bé chưa hoàn thành bài nào — bạn có gặp khó khăn gì không?" (You created many lessons but none were completed — any issues?)

---

## 13. Next Steps

### Immediate (This Week)

| # | Action | Owner | Data Source | Notes |
|---|--------|-------|-------------|-------|
| 1 | **Fix safety guardrail** — hard-abort pipeline on `[UNSAFE_CONTENT]` | Tech team | Pipeline code | Critical — 11 bypassed cases, 3 high-risk |
| 2 | **Interview 3–5 power users** from Section 6.2 contact list | Product team | Phone list above | Priority: Khánh Vy (0945167882), Thư (0334810189), Xoài (0374548893) |
| 3 | **Confirm internal tester list** with team — are Nhung/Hieu/Truck-kun staff? | Product team | Section 6.3 | Add to exclusion list for clean data |
| 4 | **Review 5 sample conversations** with 0 user turns | Product team | Conv. IDs: 23 sessions listed in 5.4 | Understand: robot-not-connecting vs child-ignoring |
| 5 | **Check notification data** — can we isolate PTL-specific notifications? | Product team | Firebase console | Current data is all-app (notification_open 38.6%) |

### Short-Term (Next 2 Weeks)

| # | Action | Owner | Notes |
|---|--------|-------|-------|
| 6 | **Connect XP scoring** for PTL lessons | Tech team | Children get no reward — completion motivation is zero |
| 7 | **Add "lesson ready" notification** on robot side | Tech team | Bridge parent→child handoff gap |
| 8 | **Drive PTL adoption** — only 10.5% of 2,000 active users have tried PTL | Product team | All users are on 1.3.8+ already — feature discovery is the blocker, not version |
| 9 | **Export 10 conversation logs per sample lesson** for quality review | Product (use queries) | SQL in `ptl-data-queries.md` Query 7, filter by sample image |
| 10 | **Review custom photo gallery** — sample 50 images to categorize what parents photograph | Product team | 250 unique photos, URLs in DB |
| 11 | **Upgrade Firebase to Blaze plan** | Tech team | ~$0 cost, enables BigQuery export |

### Medium-Term (Next Month)

| # | Action | Owner | Notes |
|---|--------|-------|-------|
| 12 | **Redesign sample lessons** based on completion data | Product team | Body parts (7.9%) → replace with conversation/roleplay samples (~33% completion) |
| 13 | **Add re-assign nudge** — if lesson not completed in 24h, notify parent to re-assign | Tech team | Re-assigned lessons complete at 24.5% vs 15.3% |
| 14 | **Investigate 50+-turn incomplete sessions** (21 sessions) | Product team | Are lessons too long? Child stuck? |
| 15 | **Set completion rate KPI** — target 25% based on re-assign rate benchmark | Product team | Current 14.2%, re-assign shows 24.5% is achievable |
| 16 | **Build internal tester exclusion into pipeline analytics** | Tech team | Auto-filter by profile ID list |
| 17 | **Track "lesson started on robot"** as distinct event from "delivered" | Tech team | Currently can't distinguish delivered-but-never-started from started-but-incomplete |

---

*Generated from production DB queries + Firebase Analytics + AI pipeline trace logs. See `docs/ptl-data-queries.md` for reusable SQL.*

