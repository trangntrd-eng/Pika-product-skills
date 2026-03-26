# Bài Toán Khó — Feature Prioritization H1 2026

> Chỉ bao gồm các bài toán có Impact ≥ 8 và Ease ≤ 6 (tức là khó, cần đầu tư suy nghĩ sâu).
> Loại bỏ: quick wins (sleep mode, WiFi, notification...), PTL optimizations (XP, notif, hash...), bug fixes (safety gate).
> Scoring: **Impact × Confidence** (bỏ Ease — vì tất cả đều khó, câu hỏi là "cái nào đáng để khó").
> Sources: Combined OST, Assumption Analysis (P1–P5), Q1 Feedback, PTL Report

---

## Tại sao cần tách riêng?

Bảng ICE đầy đủ bị dominate bởi quick wins (PTL notif, sleep mode, WiFi...) — đúng rồi, nên làm. Nhưng quick wins không giải quyết được bài toán gốc: **tại sao trẻ bỏ dùng Pika sau tuần đầu tiên?**

Các bài toán dưới đây là những thứ **không có shortcut**. Mỗi bài cần investment thực sự về thiết kế, kỹ thuật, hoặc cả hai. Nhưng nếu giải được, chúng là sự khác biệt giữa 15% và 35% renewal.

---

## 8 Bài Toán Khó

### Scoring: Impact × Confidence (bỏ Ease)

| Rank | ID | Bài toán | Impact | Conf. | I×C | Ease | Opp. | KR |
|------|-----|----------|--------|-------|-----|------|------|-----|
| 1 | S2.2 | **Thiết kế lại trải nghiệm tuần đầu tiên** | 10 | 8 | **80** | 7 | O2 | KR1,2 |
| 2 | S1.2+S1.1 | **Giải bài toán ASR cho giọng trẻ em** | 10 | 7 | **70** | 4 | O1 | KR1,2 |
| 3 | S2.1 | **Xây chương trình Starter cho người mới bắt đầu** | 10 | 8 | **80** | 5 | O2 | KR1,2 |
| 4 | S2.5 | **Nhúng tiếng Anh vào hội thoại tự nhiên** | 9 | 5 | **45** | 5 | O2,O9 | KR1,2 |
| 5 | S3.1 | **Proactive engagement — Pika chủ động tương tác** | 9 | 6 | **54** | 5 | O3 | KR1 |
| 6 | S6.2 | **Weekly learning report cho phụ huynh** | 9 | 7 | **63** | 5 | O6 | KR3 |
| 7 | S3.2 | **Struggle-to-fun fallback** | 8 | 5 | **40** | 5 | O3 | KR1 |
| 8 | S2.3 | **Adaptive difficulty engine** | 8 | 3 | **24** | 3 | O2 | KR2 |

---

## Deep Dive — Từng bài toán

### #1. Thiết kế lại trải nghiệm tuần đầu tiên (S2.2) — I×C: 80

**Bài toán**: Trẻ hào hứng Day 1-2, rơi rụng Day 3-4, bỏ dùng Day 7. Đây là "excitement cliff" — khoảnh khắc chuyển từ nói chuyện tiếng Việt vui vẻ sang bài học tiếng Anh cứng nhắc.

**Tại sao khó**:
- Không đơn giản là "delay bài học". Phải thiết kế một journey 7 ngày hoàn chỉnh:
  - Day 1-2: Con làm quen với Pika qua chơi, hát, trò chuyện tiếng Việt → xây dựng emotional bond (Layer D)
  - Day 3: Giới thiệu tiếng Anh nhẹ nhàng — từ đơn lẻ, game đoán từ, không phải "bài học"
  - Day 4-5: Chuyển dần sang bài học có cấu trúc, nhưng vẫn ngắn và xen kẽ với chơi
  - Day 6-7: Routine hình thành — con quay lại vì Pika vui, không phải vì bị ép
- Phải phối hợp cross-team: Content (tạo nội dung Day 1-3), Engineering (thay đổi orchestrator/todo flow), Design (parent app UX cho tuần đầu), AI (prompt engineering cho chế độ "fun-first")
- **Tension với kỳ vọng phụ huynh**: Ba mẹ mua Pika vì tiếng Anh. Nếu 3 ngày đầu không thấy tiếng Anh, một số sẽ nghĩ sản phẩm không hoạt động. Cần communication rõ ràng: "Pika đang xây dựng mối quan hệ với con — bài học tiếng Anh sẽ hiệu quả hơn từ ngày 4."

**Bài toán thực sự cần giải**: Làm sao để trẻ quay lại ngày hôm sau mà không cần bố mẹ nhắc?

**Dependencies**: Cần S2.1 (Starter level) để có nội dung cho Day 3-5. Cần ASR fix (S1.2) để bài học tiếng Anh khi bắt đầu không bị hỏng.

**Cách validate trước khi build lớn**:
- Thí nghiệm nhỏ: Với 50 user mới, chỉnh orchestrator để Day 1-2 = free talk only (không hiện Learn). Đo D7 retention so với control.
- Nếu D7 tăng ≥10pp → invest vào thiết kế full 7-day journey.
- Nếu không tăng → vấn đề không phải timing mà là chất lượng nội dung (chuyển sang đầu tư cho S2.1).

---

### #2. Giải bài toán ASR cho giọng trẻ em (S1.2 + S1.1) — I×C: 70

**Bài toán**: Pika không nghe được trẻ nói. 35+ mention trong Q1. 4/5 churned users báo. Trẻ gọi Pika "ngu." Tệ hơn: trẻ nói đúng nhưng Pika bảo sai.

**Tại sao khó**:
- **2 bài toán con khác nhau** (cần E1.D diagnostic để phân tách):
  - **"Nghe sai" (ASR failure)**: Pika không nhận ra từ trẻ nói → cần retrain model với voice data trẻ em Việt (S1.1, effort cao, timeline dài)
  - **"Chấm sai" (scoring failure)**: Pika nghe đúng nhưng đánh giá phát âm quá khắt khe → cần tuning threshold (S1.2, effort trung bình)
- Chưa biết % phân bổ giữa 2 loại → phải chạy diagnostic trước
- **Regional accent layer**: Giọng miền Nam, miền Trung khác biệt lớn. Một model ASR không serve tất cả.
- **Tension giữa lenient vs. strict**: Ba mẹ muốn Pika sửa phát âm chuẩn (strict). Nhưng trẻ bỏ cuộc khi bị sửa liên tục (Q1: "Pika hay sửa lỗi phát âm liên tục — các bé có chút hụt hẫng"). Phải tìm sweet spot theo level: Starter/Pre-A1 = rất lenient, A1 = moderate, A2+ = stricter.

**Bài toán thực sự cần giải**: Làm sao để trẻ cảm thấy Pika hiểu mình, trong khi vẫn giúp con cải thiện phát âm dần dần?

**Approach 2 giai đoạn**:
1. **Ngắn hạn (Sprint 1-2)**: S1.2 — Hạ threshold cho Pre-A1. Chấp nhận phát âm gần đúng. "Good enough" recognition để trẻ không bỏ cuộc. + S1.4 — Thay đổi cách Pika phản hồi khi không hiểu.
2. **Trung hạn (Sprint 5-6)**: S1.1 — Thu thập voice data từ trẻ em (opt-in program), retrain model. Cần ~1000+ samples, 2-3 tháng.

**Cách validate**:
- E1.D (chạy ngay): Phân loại 200 ASR failures gần nhất → xác định "nghe sai" vs. "chấm sai" ratio
- E1.1: A/B test lower threshold. Đo recognition rate + false positive. Target: success 60% → 80%, false positive ≤15%.

---

### #3. Xây chương trình Starter cho người mới bắt đầu (S2.1) — I×C: 80

**Bài toán**: Pre-A1 hiện tại bắt đầu bằng cụm từ và câu — quá khó cho trẻ chưa biết gì tiếng Anh. Trẻ nhăn mặt, nản, bỏ. Nhóm Pre-A1 có tỷ lệ churn cao nhất.

**Tại sao khó**:
- **Không chỉ là "thêm bài học dễ hơn"**. Cần thiết kế một learning progression hoàn chỉnh:
  - Từ vựng đơn lẻ quen thuộc (book, pen, cat, dog, red, blue...)
  - Từ → cụm từ (a red ball, my book)
  - Cụm từ → câu ngắn (I like cats)
  - Tiến trình: ~4-6 tuần để đến được level Pre-A1 hiện tại
- **Cần Vietnamese scaffolding**: Giải thích bằng tiếng Việt trước, rồi dạy từ tiếng Anh. Song ngữ theo chiều Việt → Anh, không phải Anh → Việt (ngược với hiện tại).
- **Pedagogy challenge**: Pika là robot, không phải giáo viên. Dạy từ vựng cơ bản cho trẻ 5-6 tuổi qua voice-only (không có flashcard vật lý) đòi hỏi thiết kế interaction khác — nhiều game, nhiều lặp lại, positive reinforcement.
- **Content effort**: 10 bài Starter × mỗi bài cần: từ vựng list, game, conversation script, assessment rubric. Ước tính 2-3 tuần content production.

**Bài toán thực sự cần giải**: Làm sao dạy từ vựng tiếng Anh cơ bản cho trẻ 5-7 tuổi chưa biết gì, qua một con robot voice-only, mà trẻ thấy vui?

**Dependencies**: Cần S1.2 (lenient ASR) — nếu trẻ nói "cat" mà Pika không hiểu, Starter level cũng vô dụng. Cần S2.2 (fun-first onboarding) để Starter lessons xuất hiện đúng thời điểm (Day 3-4, không phải Day 1).

**Cách validate**:
- Build 3 bài Starter (không cần 10) → test với 20 trẻ Pre-A1 mới. Đo: hoàn thành bài ≥80%, nhớ ≥60% từ vựng sau 3 ngày, D7 retention +15pp.
- Nếu pass → build thêm 7 bài. Nếu fail → redesign trước khi scale.

---

### #4. Nhúng tiếng Anh vào hội thoại tự nhiên (S2.5) — I×C: 45

**Bài toán**: Free-talk là thứ trẻ thích nhất ở Pika (Q1 positive theme #1). Bài học cấu trúc là thứ trẻ ghét nhất (O2, O9). Làm sao để học tiếng Anh xảy ra bên trong cuộc trò chuyện mà trẻ đang thích, thay vì ở một chế độ riêng biệt mà trẻ coi là "bài tập"?

**Tại sao khó**:
- **Thiết kế sư phạm trong bối cảnh tự do**: Structured lesson có lộ trình rõ — mở bài, dạy từ, luyện tập, kiểm tra. Free-talk không có lộ trình. Làm sao lồng ghép vocab/grammar vào một cuộc hội thoại không biết trước sẽ đi đâu?
- **Không được phá vỡ trải nghiệm tự nhiên**: Nếu Pika đang nói chuyện vui rồi đột ngột "À nhân tiện, bạn biết từ 'happy' tiếng Anh không?" → trẻ sẽ cảm thấy bị "dụ" học.
- **Đo lường khó**: Structured lesson có clear metric (hoàn thành bài, đúng/sai). Embedded learning không có ranh giới rõ ràng — khi nào thì "đã học xong"?
- **Prompt engineering phức tạp**: LLM cần đồng thời: (a) duy trì cuộc trò chuyện tự nhiên, (b) tìm cơ hội lồng ghép từ vựng mục tiêu, (c) không làm gián đoạn flow, (d) ghi nhận từ nào đã dạy. Đây là multi-objective prompt engineering.
- **P2 (Long) muốn Buddy Talk = learning reinforcement. P1 muốn Buddy Talk = emotional bond.** S2.5 phải bridge cả hai — learning qua emotional connection.

**Bài toán thực sự cần giải**: Làm sao để trẻ học được 3-5 từ tiếng Anh mới mỗi ngày mà không nhận ra mình đang "học"?

**Approach**:
1. **Code-switching tự nhiên**: Pika nói chuyện tiếng Việt nhưng xen tiếng Anh ở những từ trẻ đã biết hoặc có thể đoán: "Hôm nay trời sunny quá nhỉ! Bạn biết sunny là gì không?"
2. **Repetition qua ngữ cảnh**: Từ mới xuất hiện 3-4 lần trong cuộc trò chuyện ở các ngữ cảnh khác nhau.
3. **Game micro**: Xen game 30 giây vào giữa chat: "Đố bạn: con vật nào kêu 'meow'? Tiếng Anh gọi là gì?"

**Cách validate**:
- E2.5: A/B test — 50 trẻ dùng Embedded Talk, 50 dùng standard Learn. Sau 2 tuần đo:
  - Vocab retention (test lại từ vựng đã dạy) — Embedded phải ≥80% của Learn mode
  - Session length — Embedded phải dài hơn ≥30%
  - Child-initiated return rate — Embedded phải cao hơn
- Nếu vocab retention quá thấp (<50% của Learn) → approach không hiệu quả, quay lại cải thiện structured lessons.

---

### #5. Proactive Engagement — Pika chủ động tương tác (S3.1) — I×C: 54

**Bài toán**: Trẻ chỉ dùng Pika khi có bố mẹ nhắc. Nếu bố mẹ bận → không dùng → mất thói quen → churn. KR1 yêu cầu active 15/30 ngày — nghĩa là trẻ phải tự quay lại mà không cần ai thúc.

**Tại sao khó**:
- **Timing**: Pika cần biết lúc nào nên lên tiếng. Quá nhiều → annoying (giống vấn đề hiện tại — Pika nói không dừng). Quá ít → trẻ quên Pika tồn tại.
- **Content hook**: Pika nói gì để trẻ hứng thú? Generic prompt ("Mình chơi nhé!") sẽ nhanh chán. Cần personalized: "Hôm qua bạn kể về con mèo Miu — hôm nay Miu có gì vui không?" → nhưng memory hiện tại không hoạt động ổn định (Assumption U3, F9).
- **Dependency chain**: Proactive engagement cần: (a) memory hoạt động (nhớ context), (b) scheduler đúng (biết giờ con ở nhà), (c) content pool đủ sâu (không lặp lại), (d) ASR hoạt động (để cuộc trò chuyện sau khi kéo con vào không bị hỏng)
- **Ranh giới mỏng giữa "chủ động" và "phiền"**: Q1 đã có 15+ mention Pika nói không dừng. Thêm proactive engagement nếu không cẩn thận sẽ amplify vấn đề này.

**Bài toán thực sự cần giải**: Làm sao để Pika trở thành "người bạn mà con muốn gặp lại", không phải "cái app mà mẹ bắt dùng"?

**Approach tuần tự**:
1. **MVP đơn giản (Sprint 2-3)**: Scheduled greeting ở 2-3 time slots cố định (sáng trước đi học, chiều về nhà, tối trước ngủ). Nội dung: 1 câu hỏi vui + 1 fun fact. Nếu con không phản hồi sau 2 lần → im lặng (KHÔNG nói tiếp).
2. **V2 personalized (Sprint 5-6)**: Dựa trên memory + learning history. "Hôm qua bạn học về animals — hôm nay mình chơi game đoán con vật nhé!"
3. **V3 adaptive (H2)**: Phân tích pattern sử dụng → tự tìm thời điểm con hay interact nhất → trigger ở đúng moment.

**Cách validate**:
- E3.1: Deploy scheduled prompts cho 50 user. Đo % sessions mà con tự bắt đầu (không có bố mẹ). Target: từ ~30% → 50%.
- Kill signal: Nếu con dismiss/ignore proactive prompts >60% → approach không đúng, quay lại fix content quality trước.

---

### #6. Weekly Learning Report cho phụ huynh (S6.2) — I×C: 63

**Bài toán**: Ba mẹ không biết con học được gì. Không có bằng chứng tiến bộ. Khi thuê bao hết hạn, không có lý do rõ ràng để gia hạn. KR3 đòi hỏi 60% ba mẹ sẵn lòng renew — họ cần thấy ROI.

**Tại sao khó**:
- **Không có data để báo cáo**: `conversation_reports`, `conversation_summaries`, `pronounce_score`, `xp_score` cho PTL đều **null**. Ngay cả Learn mode, data conversation quality chưa rõ được capture đầy đủ chưa. Phải xây data pipeline trước khi xây report UI.
- **"Tiến bộ" trong speaking khó đo**: Vocabulary count thì đếm được. Nhưng pronunciation improvement, fluency, confidence — làm sao quantify? Ba mẹ muốn thấy "con giỏi hơn" nhưng không có metric rõ ràng.
- **Data aggregation across modes**: Trẻ học qua Learn mode, Talk mode, PTL. Report phải tổng hợp tất cả. Hiện tại mỗi mode có data structure khác nhau.
- **Timeline pressure**: Report phải có trước June để ba mẹ thấy ≥1 report trước quyết định renew July 1. Nghĩa là data pipeline + report UI phải ship trước June.

**Bài toán thực sự cần giải**: Làm sao cho ba mẹ cảm nhận được con mình đang tiến bộ — bằng data thực, không phải cảm giác mơ hồ?

**Approach phân tầng**:
1. **MVP — Sprint 3-4**: Report đơn giản nhất có thể: "Tuần này con dùng Pika X ngày, nói chuyện Y phút, học Z từ mới." Chỉ cần 3 con số. Dữ liệu này đã có trong session logs + vocabulary tracking cơ bản. Không cần pronunciation scoring.
2. **V2 — Sprint 5-6**: Thêm: danh sách từ vựng con đã học (exportable), top chủ đề con nói, progress bar "hành trình tiếng Anh" (A → Pre-A1 → A1...).
3. **V3 (H2)**: Pronunciation trajectory, so sánh với benchmark cùng độ tuổi, gợi ý cải thiện cho ba mẹ.

**Dependencies**:
- Data pipeline phải capture vocab learned + session duration + topics per session. Check xem data hiện có đủ cho MVP chưa.
- Daily summary (S6.1) nên ship trước — weekly report = aggregation of daily data.

**Cách validate**:
- Ship MVP report cho 100 ba mẹ. Đo: open rate, thời gian xem, và quan trọng nhất — hỏi "Sau khi xem report, bạn có muốn gia hạn không?" (NPS-style question).

---

### #7. Struggle-to-Fun Fallback (S3.2) — I×C: 40

**Bài toán**: Khi trẻ gặp khó, trẻ im lặng hoặc nói "không biết" — rồi bỏ đi. Pika không nhận ra trẻ đang chán/nản và cứ tiếp tục bài học. PTL data: 51.4% incomplete sessions kết thúc trong 9 user turns đầu tiên.

**Tại sao khó**:
- **Nhận diện "struggle"**: Im lặng 15 giây có thể là: (a) trẻ đang suy nghĩ, (b) trẻ đã bỏ đi, (c) trẻ đang nói nhưng Pika không nghe (ASR problem). Cần phân biệt đúng trước khi phản ứng.
- **Chuyển tiếp mượt**: Từ "bài học khó" sang "chơi game" phải tự nhiên. Nếu đột ngột: "Bạn không biết hả? Thôi mình chơi game đi!" → trẻ cảm thấy bị "đánh giá".
- **Quay lại learning**: Sau khi re-engage bằng fun, làm sao quay lại nội dung học mà không tạo cảm giác "lại bắt học rồi"?
- **Calibration per child**: Trẻ introvert cần nhiều thời gian suy nghĩ hơn. Trẻ extrovert nói liền. Một threshold "silence = struggle" không fit tất cả.

**Bài toán thực sự cần giải**: Làm sao để Pika nhận ra khoảnh khắc trẻ sắp bỏ cuộc — và kéo trẻ lại trước khi quá muộn?

**Approach**:
1. **Rule-based MVP**: Nếu 3 lần liên tiếp: silence >10s HOẶC "không biết" HOẶC ASR fail → chuyển sang game/câu đố liên quan đến topic đang học. Sau 2-3 phút game → "Bây giờ mình thử lại bài đó nhé, dễ hơn rồi!" (đưa câu dễ hơn).
2. **ML-based V2**: Train classifier trên session data: features = turn count, silence duration, ASR failures, response length → predict "sắp bỏ cuộc". Cần đủ data từ V1.

---

### #8. Adaptive Difficulty Engine (S2.3) — I×C: 24

**Bài toán**: Trẻ khác nhau ở trình độ khác nhau. Cùng Pre-A1 nhưng có trẻ biết 50 từ, có trẻ biết 0. Content cố định → hoặc quá khó hoặc quá dễ cho từng cá nhân.

**Tại sao khó — và tại sao confidence thấp nhất**:
- **Phức tạp kỹ thuật**: Cần: (a) knowledge graph per child (từ nào đã biết, từ nào chưa), (b) performance tracking per word/concept, (c) dynamic content generation hoặc selection, (d) spaced repetition logic.
- **Assumption Analysis (F8)**: "Adaptive learning logic can be designed in one sprint" — flagged là High Risk. Đây là hệ thống phức tạp mà nếu thiết kế sai sẽ đẩy nội dung sai cho trẻ, làm tệ hơn.
- **Chưa có đủ data input**: Adaptive cần biết trẻ biết gì / chưa biết gì. Hiện tại scoring data (pronounce_score, xp_score cho PTL) đều null. Không có data → không thể adapt.
- **Starter level (S2.1) + Assessment test (S2.4) giải 80% vấn đề**: Nếu trẻ được xếp đúng level từ đầu VÀ level đó thực sự phù hợp, nhu cầu adaptive giảm đáng kể.

**Bài toán thực sự cần giải**: Làm sao để content tự điều chỉnh theo năng lực thực tế của từng trẻ — không phải theo level mà ba mẹ chọn?

**Recommendation**: **Defer to H2.** Fix the prerequisite problems first (S2.1 Starter level, S2.4 Assessment, S1.2 ASR). Build data infrastructure (capture per-word performance). Khi có đủ data + cơ sở → design adaptive engine. Trong H1, dùng "poor man's adaptive": nếu trẻ fail 3 lần ở 1 từ → lặp lại từ đó session sau.

---

## Dependency Map — Thứ tự giải

```
                    E1.D (ASR diagnostic)
                         │
              ┌──────────┴──────────┐
              ▼                     ▼
     S1.2 ASR Lenient          S1.1 ASR Retrain
     (Sprint 1-2)              (Sprint 5-6)
              │                     │
              ▼                     ▼
     S2.1 Starter Level       S1.3 Regional Accents
     (Sprint 3-4)              (Sprint 7-8)
              │
              ▼
     S2.2 Fun-First Onboarding ◄─── Cần S2.1 content cho Day 3-5
     (Sprint 1-2 setup,
      Sprint 3-4 full)
              │
              ├──────────────────────┐
              ▼                      ▼
     S3.1 Proactive Engine     S2.5 Embedded English Talk
     (Sprint 3-4)              (Sprint 5-6)
              │                      │
              ▼                      ▼
     S3.2 Struggle Fallback    ◄── S2.5 cung cấp nội dung cho fallback
     (Sprint 5-6)

     ───── Song song ─────

     Data Pipeline Fix (conversation_reports, scoring)
              │
              ▼
     S6.1 Daily Summary (Sprint 3-4)
              │
              ▼
     S6.2 Weekly Report (Sprint 5-6) ◄─── Phải ship trước June
```

**Critical path**: ASR Fix → Starter Level → Fun-First Onboarding → Proactive Engine → Weekly Report → July 1 Renewal

**Bottleneck**: Data pipeline. Nếu conversation data không được capture (hiện tại null), cả daily summary lẫn weekly report đều không có gì để hiển thị. **Data pipeline fix phải chạy song song với ASR/content work từ Sprint 1.**

---

## Tóm tắt: 8 bài toán, 3 câu hỏi gốc

Tất cả 8 bài toán khó quy về **3 câu hỏi gốc**:

### Câu hỏi 1: Làm sao trẻ không bỏ cuộc trong tuần đầu?
→ S2.2 (Fun-first onboarding) + S2.1 (Starter level) + S1.2 (ASR lenient)
→ **KR1 impact: đây là nơi 80% churn xảy ra**

### Câu hỏi 2: Làm sao trẻ tự quay lại mà không cần ai nhắc?
→ S3.1 (Proactive engagement) + S2.5 (Embedded English Talk) + S3.2 (Struggle fallback)
→ **KR1 impact: active 15/30 ngày đòi hỏi self-motivation**

### Câu hỏi 3: Làm sao ba mẹ thấy tiền 120k/tháng đáng giá?
→ S6.2 (Weekly report) + Data pipeline
→ **KR3 impact: perceived ROI quyết định renewal**

**Nếu chỉ giải được câu hỏi 1 và 3 trước July 1 → đủ để di chuyển từ 15% → 35%.**
Câu hỏi 2 mở rộng ceiling nhưng câu hỏi 1 + 3 là floor.

---

*Prioritized using Impact × Confidence scoring (ease excluded intentionally). All items have Ease ≤ 6 — these are the hard problems that require deep investment but drive disproportionate outcomes.*
