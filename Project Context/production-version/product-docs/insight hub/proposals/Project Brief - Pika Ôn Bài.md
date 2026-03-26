# Project Brief: Pika Ôn Bài
### Ôn tập tiếng Anh theo SGK trên Robot Pika

**Author**: Trang Nguyen
**Date**: 25/03/2026
**Status**: Draft — Pending validation

---

## 1. Summary

Thêm tính năng "Ôn Bài" vào Robot Pika, cho phép trẻ ôn tập từ vựng và luyện đề kiểm tra theo đúng unit SGK tiếng Anh con đang học trên trường. Mục tiêu: tăng tỉ lệ gia hạn thuê bao từ 15% lên 30%+ bằng cách cho phụ huynh thấy con tiến bộ theo thước đo mà họ hiểu — bài học trên trường.

---

## 2. Background

### Chuyện gì đang xảy ra?

Robot Pika có product-market fit về mặt cảm xúc — trẻ thích Pika, PH tự hào sản phẩm Việt (NPS 7.5 với nhóm có mentor hỗ trợ). Tuy nhiên, **85% PH không gia hạn thuê bao** sau khi hết gói.

Trong đợt Customer check-up tháng 3/2026 (22 PH có feedback chi tiết):

- **59% PH nói "chờ xem kết quả rồi gia hạn"** — nhưng không có công cụ nào cho họ thấy kết quả
- PH đang đánh giá tiến bộ bằng cách... hỏi con vài từ vựng rồi đoán — rất không đáng tin cậy
- 12/22 PH không biết tiếng Anh hoặc quá bận → không thể tự dạy con

### Tín hiệu từ CSKH

Linh (CSKH) chia sẻ pattern từ nhiều cuộc gọi:

> *"Em thấy nhu cầu nhiều lắm luôn. Nhiều bố mẹ ko biết tiếng Anh nên cũng ko dạy được con."*
>
> *"Bố mẹ kiểu có kì vọng con vẫn nâng được điểm số trên lớp mà vẫn có thể giao tiếp nói chuyện được."*
>
> *"Chương trình trên trường ạ... Hiện tại trên trường nhiều trường cho học đăng kí bổ sung tiếng Anh nhưng bố mẹ ko thấy tiến bộ hoặc ko có người đưa đón con."*

### Tại sao bây giờ?

1. **Renewal rate 15%** là rủi ro kinh doanh lớn nhất — target H1 2026 là 35%
2. V2 strategy đã xác định "Show the Receipt" (cho PH thấy bằng chứng tiến bộ) là 1 trong 3 core strategies
3. Roadmap đã có S2.6 (School Alignment Orchestrator) planned cho Q4 2026 — concept này accelerate S2.6 thành MVP sớm hơn
4. Pika đã có ~50% content overlap với SGK lớp 3 → không cần build from scratch

---

## 3. Objective

### Objective
Tăng tỉ lệ gia hạn thuê bao bằng cách biến Pika từ "bạn chơi tiếng Anh" thành "gia sư TA tại nhà ôn bài theo SGK", cho PH thấy con tiến bộ theo thước đo trường học.

### Alignment với chiến lược
- **V2 Strategy — "Show the Receipt"**: Parent report theo unit SGK chính là "receipt" rõ ràng nhất
- **H1 2026 Goal**: Tăng renewal 15% → 35%
- **Layer A (Key Value)**: Nâng cấp English learning từ free-form thành structured + school-aligned

### Key Results

| KR | Baseline | Target | Timeline |
|----|----------|--------|----------|
| KR1: Renewal intent (survey) trong nhóm pilot | 15% | ≥30% | Sau 8 tuần pilot |
| KR2: Weekly usage frequency (nhóm dùng Ôn Bài) | 3.2 ngày/tuần | ≥4 ngày/tuần | Sau 4 tuần |
| KR3: Parent report open rate | 0% (chưa có) | ≥50% | Sau 4 tuần |
| KR4: Vocab retention (từ nhớ sau 1 tuần ôn) | Không đo được | ≥70% | Sau 4 tuần |
| KR5: Parent NPS (nhóm pilot) | 6.3/10 | ≥7.5/10 | Sau 8 tuần |

---

## 4. Market Segment

### Primary: PH trường công, con lớp 3-4, học sách Global Success

**Profile:**
- Con 7-9 tuổi, đang học tiếng Anh chính thức năm đầu tiên (lớp 3) hoặc năm thứ hai (lớp 4)
- PH không biết tiếng Anh hoặc không tự tin dạy con
- Đã mua Robot Pika (hardware 2.5M VND) → có intent đầu tư cho việc học TA của con
- Muốn con "nâng điểm trên trường + giao tiếp được" — cả hai, không phải chọn một
- Đang tìm giải pháp thay thế cho trung tâm TA (tốn thời gian đưa đón, không thấy tiến bộ)

**Job to be done:**
> "Giúp con giỏi hơn ở trường, và cho tôi thấy điều đó đang xảy ra — mà không cần tôi phải biết tiếng Anh hay ngồi cạnh con."

**Ước tính quy mô:**
- 5,426 PH đã mua Pika → ước tính ~60% có con lớp 3-4 = ~3,200 PH tiềm năng
- Nếu ~50% dùng Global Success = ~1,600 PH trong target segment

### Secondary (mở rộng sau):
- PH con lớp 5 (Global Success)
- PH con học sách i-Learn Smart Start hoặc Family and Friends (trường tư)

---

## 5. Value Proposition

### Cho trẻ:

| Trước (hiện tại) | Sau (có Pika Ôn Bài) |
|---|---|
| Pika dạy tiếng Anh theo curriculum riêng, không liên quan bài trên trường | Pika ôn đúng từ vựng Unit 6 con đang học trên lớp |
| Học xong không biết mình nhớ bao nhiêu | Pika nói "Con nhớ 8/10 từ, hơn tuần trước 2 từ!" |
| Trước ngày kiểm tra không biết ôn gì | "Pika ơi luyện đề Unit 5-6 đi!" — có sẵn 10 câu luyện |
| Gặp từ khó thì bỏ qua | Pika hỏi lại từ con quên sau 5 phút, 1 ngày, 3 ngày (spaced repetition) |

### Cho phụ huynh:

| Trước | Sau |
|---|---|
| Không biết con học Pika có tiến bộ không | Nhận báo cáo tuần: "Con nhớ 9/10 từ Unit 6, tuần trước 6/10" |
| Muốn ôn bài cho con nhưng không biết TA | Pika ôn thay, PH chỉ cần chọn unit |
| Không có lý do gia hạn — "để con học hết rồi tính" | Thấy con tiến bộ rõ ràng → "tiếp tục đi, đang tốt mà" |
| So sánh Pika với gia sư 150-400k/buổi | Pika ôn bài 24/7 trong gói thuê bao 120k/tháng |

### Unique Value — so với đối thủ

| Đối thủ | Họ | Pika Ôn Bài |
|---|---|---|
| VietJack / Loigiaihay | Tra đáp án → con copy | Con phải **nói, nhớ, luyện** |
| Monkey / ELSA | Curriculum riêng | **Theo đúng unit SGK trên trường** |
| Gia sư 1:1 | 150-400k/buổi, cần đặt lịch | 24/7, sẵn sàng trong thuê bao |
| AMES Online | Lớp nhóm 8-15 người | 1:1 với con |

**Không đối thủ nào đang owns positioning "ôn bài SGK bằng AI voice".**

---

## 6. Solution

### 6.1 User Flow

```
[Setup 1 lần trên app PH]
PH mở app → Cài đặt học tập → Chọn lớp (3/4) → Chọn sách (Global Success) → Chọn unit hiện tại
                                                                                        │
                                                                                        ▼
                                                                              Pika nhận config
                                                                                        │
                                                    ┌───────────────────────────────────┤
                                                    ▼                                   ▼
                                        Con: "Pika ôn bài đi!"              Con: "Pika luyện đề đi!"
                                                    │                                   │
                                                    ▼                                   ▼
                                           Mode 1: Ôn Bài                    Mode 2: Luyện Đề
                                        (quiz từ vựng theo unit)          (10 câu giả lập kiểm tra)
                                                    │                                   │
                                                    └───────────────┬───────────────────┘
                                                                    ▼
                                                        Kết thúc session
                                                    Score + từ nhớ/quên
                                                                    │
                                                                    ▼
                                                    Push report cho PH cuối tuần
                                                "Con nhớ 9/10 từ Unit 6 (tuần trước: 6/10)"
```

### 6.2 Mode 1: Ôn Bài (Spaced Repetition Quiz)

**Trigger**: Con nói "Pika ơi, ôn bài đi" hoặc PH giao bài ôn trên app

**Flow**:
1. Pika xác nhận unit: "Mình ôn Unit 6 - Our School nhé!"
2. Quiz từ vựng 2 chiều:
   - Pika nói tiếng Anh → con nói nghĩa tiếng Việt
   - Pika nói tiếng Việt → con nói từ tiếng Anh
3. Luyện phát âm: Pika đọc → con nhắc lại → Pika feedback
4. Ghép câu đơn giản: "Đặt câu với từ 'pencil'" → con nói câu
5. Spaced repetition: từ sai được hỏi lại sau 3-5 phút → 1 ngày → 3 ngày
6. Kết thúc: "Con nhớ 8/10 từ, giỏi lắm! Lần trước 6/10 — tiến bộ rồi!"

**Thời lượng**: 10-15 phút/session

**Content cần tạo cho mỗi unit:**
- Danh sách 10-15 từ vựng chính (extract từ SGK)
- 3-5 cấu trúc câu mẫu
- Pronunciation targets (âm khó cho trẻ Việt)

### 6.3 Mode 2: Luyện Đề (Test Simulation)

**Trigger**: Con nói "Pika ơi, luyện đề đi" hoặc gần ngày kiểm tra

**Flow**:
1. Pika xác nhận scope: "Luyện đề Unit 5-6 nhé! 10 câu, sẵn sàng chưa?"
2. Mix 6 dạng bài phổ biến nhất (chiếm ~75% điểm thi thực tế):

| Dạng bài | Ví dụ voice adaptation | Số câu |
|---|---|---|
| Trắc nghiệm (A/B/C) | "This is ___ ruler. A - a, B - an, C - the" | 3 |
| Sắp xếp từ thành câu | "is / This / school / my — con ghép thành câu đi" | 2 |
| Nghe hiểu | Pika đọc đoạn → hỏi câu hỏi | 2 |
| True/False | "A pencil is used for cutting. True or false?" | 1 |
| Odd one out | "pen, ruler, apple, eraser — từ nào khác loại?" | 1 |
| Hoàn thành hội thoại | Pika: "What's this?" → Con: "It's a ___" | 1 |

3. Sau mỗi câu: giải thích ngắn nếu sai
4. Kết thúc: Score + phân tích điểm yếu + đề xuất ôn lại

**Content cần tạo:**
- 10-15 câu hỏi/unit × 20 unit = 200-300 câu tổng
- Phân loại theo dạng bài và độ khó

### 6.4 Parent Report

**Push notification hàng tuần** (Chủ nhật tối hoặc thứ 2 sáng):

```
📊 Báo cáo tuần của [Tên con] (16-22/3)

📖 Ôn bài: Unit 6 - Our School
   • Từ vựng nhớ: 9/10 (tuần trước: 6/10) ↑
   • Từ cần ôn thêm: eraser, glue

📝 Luyện đề: 8/10 câu đúng
   • Mạnh: Từ vựng, Nghe hiểu
   • Cần cải thiện: Sắp xếp câu

⏱️ Thời gian học: 4 ngày, tổng 52 phút
```

**In-app detail view** (PH tap vào notification):
- Biểu đồ tiến bộ theo tuần (số từ nhớ, điểm luyện đề)
- Danh sách từ con đã nhớ vs chưa nhớ
- Gợi ý: "Con nên ôn thêm Unit 6 trước khi chuyển sang Unit 7"

### 6.5 Dạng bài KHÔNG hỗ trợ (và lý do)

| Dạng bài | Lý do không làm | Chiếm ~% đề thi |
|---|---|---|
| Nhìn tranh viết từ | Pika voice-first, không có màn hình hiển thị tranh | ~10% |
| Word search / Crossword | Cần visual + pen-and-paper | ~3% |
| Viết đoạn văn | Quá dài cho voice, cần viết tay | ~5% |
| Chép chính tả | Output = viết tay | ~5% |
| Nối bằng vẽ đường | Hành động vật lý | ~2% |

**Tổng phần không cover: ~25% đề thi** — acceptable vì 75% còn lại đã đủ tạo giá trị.

---

## 7. Assumptions & Risks

### Critical Assumptions (phải validate trước khi build)

| # | Assumption | Evidence hiện có | Rủi ro nếu sai | Cách validate | Khi nào |
|---|---|---|---|---|---|
| **A1** | PH sẽ gia hạn nếu thấy con ôn bài theo SGK | CSKH Linh: "nhu cầu nhiều lắm", 59% PH "chờ kết quả" | Build xong không move renewal | Phỏng vấn 5-7 PH, test concept reaction | Tuần 1 |
| **A2** | Đa số trẻ Pika đang học sách Global Success | Global Success = sách trường công phổ biến nhất | Map sai sách → content vô dụng | Hỏi PH trong phỏng vấn câu "con học sách gì" | Tuần 1 |
| **A3** | Voice-based quiz đủ hiệu quả để trẻ nhớ từ | Pika đã có adaptive learning + spaced repetition cơ bản | Trẻ cần visual, voice không đủ | Wizard-of-Oz: CSKH quiz 5-10 trẻ bằng voice, đo nhớ sau 3 ngày | Tuần 2 |
| **A4** | PH đọc báo cáo tuần | V2 Strategy đã xác định "Show the Receipt" | PH không mở notification → không thấy value | Fake door: gửi report mock cho 20 PH, đo open rate | Tuần 2 |
| **A5** | "Tiến bộ theo unit SGK" là thước đo PH thực sự dùng | CSKH: "sát chương trình trên trường" | PH muốn metric khác (điểm thi thực, so sánh bạn bè) | Phỏng vấn câu "PH đo tiến bộ bằng gì" | Tuần 1 |

### Technical Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| ASR chưa đủ tốt để nhận diện câu trả lời quiz | Cao (ASR success rate Pre-A1 = ~60%) | Cao — trẻ frustrate | Dùng ASR lenient mode (đang build Sprint 1) + accept approximate answers |
| Trẻ nói sai phát âm → Pika hiểu sai đáp án | Cao | Trung bình | Cho trẻ confirm: "Con nói B phải không?" + retry mechanism |
| Content quality quiz bank chưa đạt chuẩn sư phạm | Trung bình | Trung bình | Review với 1-2 GV tiếng Anh tiểu học trước khi launch |

### Business Risks

| Risk | Mitigation |
|---|---|
| PH kỳ vọng Pika = gia sư thật → thất vọng khi chỉ là quiz | Messaging rõ ràng: "Pika ôn từ vựng + luyện nói", không hứa "dạy kèm toàn diện" |
| Tạo kỳ vọng "tăng điểm" nhưng điểm không tăng → backlash | Không cam kết "tăng điểm", chỉ cam kết "ôn tập đều đặn theo bài trên trường" |
| Chỉ có Global Success → PH dùng sách khác thấy không phù hợp | Phase 1 target rõ ràng, survey PH trước để confirm sách phổ biến nhất |

---

## 8. Release Plan

### Phase 0: Validate (2 tuần)

| Tuần | Hoạt động | Output | Gate |
|------|-----------|--------|------|
| Tuần 1 | Phỏng vấn 5-7 PH (interview guide đã có) | Validate A1, A2, A5 | ≥4/7 PH phản ứng tích cực |
| Tuần 2 | Wizard-of-Oz test: CSKH quiz 5-10 trẻ bằng voice | Validate A3 | ≥60% trẻ nhớ từ sau 3 ngày |
| Tuần 2 | Fake door: gửi mock report cho 20 PH | Validate A4 | ≥40% PH mở + phản hồi tích cực |

**Go/No-go gate**: Nếu ≥3/5 assumptions validated → Go Phase 1. Nếu không → Pivot hoặc kill.

### Phase 1: MVP (4-6 tuần)

| Sprint | Scope | Deliverable |
|--------|-------|-------------|
| Sprint 1 (2 tuần) | Content: Map + tạo quiz bank Global Success lớp 3 (10 unit) | 100-150 câu quiz + 100-150 từ vựng |
| Sprint 2 (2 tuần) | Mode "Ôn Bài": voice quiz flow + spaced repetition | Feature trên Robot |
| Sprint 3 (2 tuần) | Parent report: weekly push + in-app detail + PH chọn unit trên app | Feature trên app PH |

**Pilot**: 30 users (chọn từ nhóm "chờ xem kết quả" trong survey)
**Đo**: Renewal intent, usage frequency, report open rate, NPS

### Phase 2: Expand (4 tuần, sau khi Phase 1 validated)

- Thêm **lớp 4** (10 unit Global Success)
- Thêm **Mode "Luyện Đề"** (test simulation)
- Parent report nâng cao: biểu đồ tiến bộ, so sánh với tuần trước
- **Gate**: Renewal intent ≥25% trong pilot Phase 1

### Phase 3: Scale (Backlog — dựa trên data Phase 1-2)

- Thêm sách i-Learn Smart Start, Family and Friends
- Thêm lớp 5
- Mode "Giải Thích" (grammar explainer) + "Kiểm Tra Bài Làm" (homework checker)
- Chương trình GV kết hợp Pika (separate initiative, cần validate riêng)
- B2B: cho trường/trung tâm tạo learning path trên Pika (align với S2.7 trong roadmap)

---

## 9. Dependencies

| Dependency | Team | Status | Impact nếu delay |
|---|---|---|---|
| ASR lenient mode cho beginners | Engineering | Sprint 1 H1 roadmap — đang build | Trẻ frustrate khi quiz → trải nghiệm tệ |
| Parent app notification system | Mobile | Đang build trong P1 Parental Roadmap | Không gửi được report → PH không thấy value |
| Content review bởi GV tiếng Anh | Học liệu + External | Chưa bắt đầu | Quiz không chuẩn → mất uy tín |
| PTL (Photo-to-Lesson) infra | Engineering | Đã có | Leverage cho giao bài ôn |

---

## 10. Appendix

### A. Desk Research Summary

**SGK tiếng Anh tiểu học VN:**
- 3 bộ sách phổ biến: Global Success (Bộ GD — trường công), i-Learn Smart Start (Pearson — tăng cường), Family and Friends (Oxford — trường tư)
- Global Success lớp 3: 10 unit (Hello, Names, Friends, Bodies, Activities, School, Toys, Pets, Colours, Neighbourhood)
- Global Success lớp 4: 10 unit (Greetings, Nationalities, Days, Birthday, Abilities, Places, Hobbies, Subjects, Activities, Past)

**Đề thi tiếng Anh tiểu học:**
- 28 dạng bài tập, chia 6 nhóm (Listening, Reading, Vocabulary, Grammar, Writing, Speaking)
- Pika có thể hỗ trợ ~75% tổng điểm kiểm tra bằng voice
- 6 dạng bài phổ biến nhất đều voice-friendly

**Competitive landscape:**
- Không đối thủ nào owns "ôn bài SGK bằng AI voice"
- Monkey/ELSA: curriculum riêng, không theo SGK
- VietJack/Loigiaihay: tra đáp án, không luyện tập
- Gia sư 1:1: 150-400k/buổi, cần đặt lịch
- Khoảng trống rõ ràng cho Pika

### B. Content Overlap Analysis

| Lớp | Overlap Pika ↔ Global Success | Gap chính |
|-----|-------------------------------|-----------|
| Lớp 3 | ~50% (5/10 unit) | Body parts, Colours, Toys, Neighbourhood |
| Lớp 4 | ~35% (3-4/10 unit) | Nationalities, Days/Months, Directions, Subjects |
| Lớp 5 | ~20% (2/10 unit) | Hầu hết unit — quá nhiều gap, deprioritize |

### C. Customer Feedback Highlights (Mar 2026)

- Điểm hài lòng trung bình: **8.1/10** (14 PH cho điểm)
- Top pain: Pika ngắt lời (8/22), nhận diện phát âm sai (7/22), Pika nói lan man (5/22)
- Top delight: Trò chơi/gamification (16/22), trẻ tự học được (12/22), Pika = bạn đồng hành (6/22)
- Gia hạn: 18% sẽ gia hạn, **59% chờ xem kết quả**, 14% phụ thuộc cải thiện SP, 9% khó gia hạn

### D. Interview Guide (đã soạn sẵn)

Phỏng vấn sâu 5-7 PH, 20-25 phút qua điện thoại, do CSKH thực hiện. Focus:
1. Bức tranh học TA hiện tại của con (trường + ngoài)
2. PH đo "tiến bộ" bằng gì (moment of delight vs anxiety)
3. Con đang học sách gì, ôn kiểm tra kiểu gì, hay mất điểm phần nào
4. Reaction khi nghe concept "Pika giao bài theo unit trường"
5. Willingness to pay

Template ghi chép đã chuẩn bị sẵn.
