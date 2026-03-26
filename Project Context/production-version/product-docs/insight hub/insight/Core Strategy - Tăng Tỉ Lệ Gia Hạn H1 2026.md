# Core Strategy — Tăng Tỉ Lệ Gia Hạn H1 2026

> Framework: Product Strategy Canvas (9 sections)
> Context: Pika Robot, AI English-learning companion cho trẻ tiểu học Việt Nam
> Goal: Renewal 15% → 35% tại mức giá 120k VND/tháng, bắt đầu 01/07/2026
> Sources: Q1 Feedback (150+), Assumption Analysis (P1–P5), PTL Report, Combined OST, Pika Value Direction

---

## Vấn đề chiến lược cần giải

Pika có **product-market fit ở tầng cảm xúc** — trẻ yêu Pika, phụ huynh tự hào sản phẩm Việt Nam. Nhưng **không có product-market fit ở tầng giá trị sử dụng** — 85% phụ huynh không gia hạn.

Q1 data cho thấy con đường từ "mua hàng" đến "gia hạn" bị đứt ở 3 điểm:

```
Mua Pika → [Tuần 1: Hào hứng] → [Day 3-4: Excitement cliff] → [Day 7+: Bỏ dùng] → [Day 30: Không gia hạn]
                ✓ Hoạt động              ✗ ASR hỏng                ✗ Không tự quay lại     ✗ Không thấy ROI
                                         ✗ Nội dung khó quá        ✗ Cần bố mẹ ngồi cạnh
```

**Chiến lược phải sửa 3 điểm đứt này — theo đúng thứ tự.**

---

## 1. Vision

> Pika là người bạn AI đầu tiên giúp trẻ tiểu học Việt Nam tự tin nói tiếng Anh — không phải bằng bài học, mà bằng tình bạn.

**H1 2026 vision (scoped)**: Mỗi gia đình mua Pika đều cảm nhận được tiến bộ tiếng Anh rõ ràng của con trong 30 ngày đầu tiên — đủ để ba mẹ tự nguyện trả 120k/tháng.

**Giá trị cốt lõi**:
- Với trẻ: Pika hiểu mình, Pika vui, mỗi ngày có lý do quay lại
- Với phụ huynh: Thấy con tiến bộ, thấy tiền mình chi đáng giá, không cần ngồi cạnh mỗi phiên

---

## 2. Phân khúc thị trường (theo JTBD, không theo demographics)

### Segment A — "Con chưa biết gì" (Pre-A1 Beginner) — ĐỘ ƯU TIÊN CAO NHẤT

**JTBD**: "Tôi muốn con làm quen với tiếng Anh từ sớm, nhưng con chưa biết từ nào cả. Tôi cần thứ gì đó dễ và vui để con không sợ tiếng Anh."

- Trẻ 5-7 tuổi, chưa học tiếng Anh hoặc biết vài từ đơn lẻ
- Phụ huynh thường không giỏi tiếng Anh → không thể kèm con
- **Đây là nhóm lớn nhất đến với Pika** và cũng là nhóm churn cao nhất
- Constraint: Con cần ba mẹ ngồi cạnh (O3), nội dung quá khó (O2), Pika không nghe được (O1)

**Tại sao segment này quyết định renewal rate**:
- Nếu nhóm này churn → renewal rate mãi thấp vì họ là majority
- Nếu nhóm này retain → word-of-mouth mạnh (ba mẹ Việt Nam chia sẻ trong cộng đồng)

### Segment B — "Con đang học nhưng cần luyện nói" (A1-A2)

**JTBD**: "Con đang học tiếng Anh ở trung tâm/trường nhưng không có ai để nói chuyện tiếng Anh ở nhà. Tôi muốn con có môi trường luyện nói hàng ngày."

- Trẻ 7-12 tuổi, đã có vốn từ cơ bản, đang học thêm ở nơi khác
- Phụ huynh coi Pika là bổ trợ, không phải thay thế giáo viên
- Satisfaction cao hơn (7-8/10 trong check-up) vì con đã biết đủ để tương tác
- **Rủi ro**: Con outgrow Pika nhanh nếu content không đi kịp (Q1: yêu cầu B1+)

### Segment C — "Phụ huynh chủ động" (Power Parent)

**JTBD**: "Tôi muốn kiểm soát con học gì, khi nào, và thấy kết quả rõ ràng. Tôi sẵn sàng đầu tư thời gian setup nếu output tốt."

- 10-15% user base, dùng PTL, tạo bài, giao bài hàng ngày
- Satisfaction phụ thuộc vào app UX + reporting + child completion
- **PTL data xác nhận nhóm này tồn tại**: 210 parents, 53.2% organic content, power users tạo 10+ bài
- Rủi ro: Nếu con không hoàn thành bài (PTL 14.2% completion), ba mẹ mất niềm tin

### Quyết định chiến lược: TẬP TRUNG VÀO SEGMENT A

Segment A quyết định volume. Segment B đã ổn (retention tốt hơn). Segment C là power users sẽ tự adapt. **Mọi quyết định product H1 phải ưu tiên: "Có giúp trẻ chưa biết tiếng Anh survive tuần đầu tiên không?"**

---

## 3. Relative Costs — Vị trí chi phí

**Unique value, not low cost.**

Pika không cạnh tranh bằng giá. 120k/tháng + ~2.5 triệu phần cứng là premium so với Duolingo (free), Reading Eggs (~100k/tháng), hay ChatGPT (free).

**Pika bán gì mà free AI không có?**
- Physical presence — con ôm Pika ngủ, Pika là "thành viên gia đình"
- Child-safe, designed for children — không có quảng cáo, nội dung không phù hợp, giới hạn thời gian
- No screen — ba mẹ Việt Nam lo lắng về screen time, Pika là giải pháp "học mà không nhìn màn hình"
- Vietnamese-first — hiểu giọng Việt, song ngữ tự nhiên, nội dung phù hợp văn hóa

**Chi phí so với giá trị nhận được**:
- 120k/tháng ≈ 4k/ngày ≈ rẻ hơn 1 cốc trà sữa
- So với trung tâm tiếng Anh: 500k-2 triệu/tháng
- **Nhưng ba mẹ so sánh với free ChatGPT**: "Pika không trả lời được" vs. "cùng từ đó tôi nói cho ChatGPT thì lại ổn" (Q1 data)

→ **Chiến lược giá**: Không giảm giá. Tăng perceived value. Ba mẹ phải thấy con tiến bộ rõ ràng — lúc đó 120k/tháng là rẻ.

---

## 4. Value Proposition — 3 đề xuất giá trị cốt lõi

### VP1: "Con tự tin nói tiếng Anh từng từ một" (cho Segment A)

| | |
|---|---|
| **What before** | Con sợ tiếng Anh, không biết từ nào, nhăn mặt khi nghe. Ba mẹ không giỏi tiếng Anh để dạy. |
| **How** | Pika bắt đầu bằng tình bạn (3 ngày đầu = chơi, hát, trò chuyện). Sau đó dạy từng từ qua game và conversation, không phải bài học cứng nhắc. Pika chấp nhận phát âm chưa chuẩn và khuyến khích thay vì sửa liên tục. |
| **What after** | Sau 30 ngày, con biết 50-100 từ tiếng Anh cơ bản, tự tin nói với Pika mà không cần ba mẹ ngồi cạnh. Ba mẹ nhận report hàng tuần thấy danh sách từ con học được. |
| **Alternatives hiện tại** | Không làm gì (đợi con lớn hơn), Duolingo (free nhưng screen-based, không có speaking practice thực sự), trung tâm (đắt, tốn thời gian đi lại) |

### VP2: "Mỗi tuần ba mẹ thấy con tiến bộ" (cho Segment A + C)

| | |
|---|---|
| **What before** | Ba mẹ chi tiền cho Pika nhưng không biết con có học được gì không. Con cầm Pika nói chuyện cả ngày nhưng ba mẹ không biết nội dung gì. Không có cơ sở để quyết định gia hạn. |
| **How** | Weekly report: số từ mới, chủ đề nói, thời gian dùng, pronunciation trajectory. Daily push: "Hôm nay con học được 3 từ mới: cat, dog, bird." PTL: ba mẹ tạo bài → con làm → ba mẹ xem kết quả. |
| **What after** | Ba mẹ mở app thứ Hai, thấy report tuần trước: "Con học được 15 từ mới, dùng Pika 5/7 ngày, pronunciation cải thiện 12%." → Quyết định gia hạn dễ dàng. |
| **Alternatives** | Trung tâm (có report card nhưng 2-3 tháng/lần), Duolingo (có streak/XP nhưng không có speaking assessment) |

### VP3: "Con có bạn để nói chuyện tiếng Anh mỗi ngày" (cho Segment B)

| | |
|---|---|
| **What before** | Con học tiếng Anh ở trung tâm 2 buổi/tuần nhưng 5 ngày còn lại không có ai nói tiếng Anh cùng. Kỹ năng nói không tiến bộ vì thiếu practice. |
| **How** | Pika chủ động mời con nói chuyện mỗi ngày. Embedded English trong hội thoại tự nhiên — con nói chuyện vui bằng tiếng Việt, Pika tự nhiên xen tiếng Anh. Vocabulary từ bài học ở trung tâm được ba mẹ input qua PTL → Pika lồng ghép vào conversation. |
| **What after** | Con nói tiếng Anh tự tin hơn, phản xạ nhanh hơn. Giáo viên ở trung tâm nhận thấy tiến bộ. Ba mẹ thấy Pika bổ trợ (không thay thế) trung tâm. |
| **Alternatives** | Nói chuyện với ba mẹ (nhưng ba mẹ không giỏi/không có thời gian), Duolingo Lily (free AI conversation nhưng text-based), không làm gì (chờ 2 buổi/tuần ở trung tâm) |

---

## 5. Trade-offs — KHÔNG LÀM GÌ TRONG H1

| Chúng tôi KHÔNG làm | Tại sao | Khi nào xem lại |
|---------------------|---------|-----------------|
| Mở rộng sang Toán/Văn/Khoa học/Lịch sử | Tiếng Anh là anchor value proposition. Chưa anchor được thì đừng mở rộng. Mỗi môn thêm = focus bị chia. | H2, nếu English renewal >35% |
| Thêm tiếng Trung/tiếng Hàn | Zero demand signal trong Q1 (chỉ 2 comment Facebook). Resource ASR cho 1 ngôn ngữ đã không đủ. | 2027, khi English model ổn định |
| Adaptive Influence Framework (nudge hành vi trẻ) | Cao risk (LLM unpredictable với trẻ em). Không có demand từ ba mẹ. Cần safety guardrails chưa có. | H2, với proper red-teaming |
| Full app redesign | Effort lớn, return không rõ. Ship targeted improvements (report, notifications) trước. | Sau July 1, khi biết ba mẹ thực sự dùng feature gì |
| Badge/leaderboard/gamification phức tạp | Gamification amplify sản phẩm tốt. Sản phẩm chưa tốt → gamification không cứu được. | Khi D7 retention >60% |
| Phục vụ trẻ dưới 5 tuổi | 20% PTL requests đến từ trẻ dưới 6. Nhưng ASR cho trẻ 5 tuổi (ngôn ngữ chưa hoàn chỉnh) là bài toán khác hẳn. Spread too thin. | 2027, với dedicated child-voice model |
| Robot cho người lớn / người già | Q1 có vài request. Hoàn toàn khác product. | Không xem lại — khác sản phẩm |

**Triết lý trade-off**: Mỗi "không" ở trên giải phóng engineering hours cho 3 điều duy nhất quan trọng: (1) ASR hoạt động, (2) tuần đầu không thất bại, (3) ba mẹ thấy con tiến bộ.

---

## 6. Key Metrics

### North Star Metric

**Số trẻ dùng Pika ≥15 ngày trong 30 ngày đầu** (= KR1)

Tại sao đây là North Star:
- Nếu trẻ dùng 15+ ngày → đã hình thành thói quen → ba mẹ sẽ thấy giá trị → renewal tự nhiên
- Metric này upstream của tất cả business outcomes: 15+ active days → more learning → parent sees progress → renews
- Hiện tại: 24%. Target: 80%.

### OMTM Q2/2026

**D7 retention rate (% trẻ còn active vào ngày thứ 7 sau khi bắt đầu dùng)**

Tại sao Q2 focus vào D7:
- Nếu trẻ survive tuần đầu → xác suất dùng 15+ ngày tăng mạnh
- D7 churn là nơi mất nhiều user nhất (excitement cliff Day 3-4)
- Tất cả hard problems #1-#3 đều nhắm vào D7
- Dễ đo, nhanh feedback loop (7 ngày thay vì 30 ngày)

### Supporting Metrics

| Metric | Hiện tại | Target H1 | Drives |
|--------|----------|-----------|--------|
| D7 retention | ~50% (est.) | 70% | KR1 |
| Avg session length | Unknown | ≥8 min | KR2 |
| Sessions/active day | Unknown | ≥2 | KR2 |
| ASR success rate (Pre-A1) | ~60% (est.) | 80% | KR1, KR2 |
| Weekly report open rate | N/A (chưa có) | ≥50% | KR3 |
| Parent NPS | ~6.3/10 | ≥7.5/10 | KR3 |
| PTL child completion rate | 14.2% | 30% | KR2 |

---

## 7. Growth — Chiến lược tăng trưởng

### Giai đoạn H1: Retention-Led Growth (không phải Acquisition-Led)

**Đừng tìm thêm khách hàng mới. Hãy giữ được khách hàng hiện tại.**

Tại sao:
- 5,426 registered parents. Chỉ 2,000 active/tuần. 3,426 đã trả tiền mua phần cứng nhưng không dùng.
- Renewal rate 15% = 85% khách hàng rời đi. Mỗi khách hàng mất = chi phí acquisition lãng phí.
- **Tăng renewal 15% → 35% trên base hiện tại có giá trị hơn tìm thêm 1,000 khách mới mà cũng chỉ giữ được 15%.**

### Flywheel: Retention → Word-of-Mouth → Growth

```
Trẻ dùng Pika hàng ngày
        ↓
Trẻ tiến bộ tiếng Anh
        ↓
Ba mẹ nhận weekly report, thấy tiến bộ
        ↓
Ba mẹ gia hạn (120k/tháng)
        ↓
Ba mẹ khoe trong group Facebook, chat nhóm phụ huynh
        ↓
Người quen mua Pika
        ↓
(Lặp lại)
```

**Cơ chế word-of-mouth cụ thể**:
- Weekly report có nút "Chia sẻ thành tích của con" → share lên Facebook/Zalo
- "Mình rất tự hào về sản phẩm made in Việt Nam" (Q1 quote) — đây là emotional trigger sẵn có
- Community Facebook group đã tồn tại (~1,000+ members) — nurture, không cần build

### Unit Economics (ước tính)

| Metric | Hiện tại | Target H1 |
|--------|----------|-----------|
| Hardware revenue / user | ~2.5M VND (one-time) | Không đổi |
| Monthly subscription | 120k VND | Bắt đầu July 1 |
| Renewal rate | 15% | 35% |
| LTV (12 tháng) | 2.5M + (0.15 × 12 × 120k) = 2.716M | 2.5M + (0.35 × 12 × 120k) = 3.004M |
| LTV increase | — | **+288k/user (+10.6%)** |
| At scale (5,000 users) | — | **+1.44 tỷ VND/năm incremental** |

---

## 8. Capabilities — Năng lực cần xây dựng

### Phải có trong H1 (build)

| Capability | Tại sao | Status |
|-----------|---------|--------|
| **Child-voice ASR** | Không nghe được trẻ = sản phẩm không hoạt động. Đây là table stake, không phải differentiator. | Không có timeline trên roadmap. P0. |
| **Beginner curriculum design** | Nhóm lớn nhất (Pre-A1) không có content phù hợp. Cần learning designer hiểu trẻ 5-7 tuổi + tiếng Anh cơ bản + voice-only interaction. | Thiếu. Cần hire hoặc contract. |
| **Data pipeline cho learning analytics** | `conversation_reports`, `pronounce_score` đều null. Không có data → không có weekly report → KR3 chết. | Chưa xây. Phải chạy song song Sprint 1. |
| **Prompt engineering cho "embedded learning"** | Nhúng tiếng Anh vào conversation tự nhiên đòi hỏi multi-objective prompting phức tạp. | Cần R&D, chưa ai làm. |

### Đối tác / Outsource

| Capability | Build vs. Partner | Lý do |
|-----------|-------------------|-------|
| Vietnamese child-voice training data | Partner | Thu thập từ trường học, chương trình nghiên cứu. Không tự thu thập được đủ nhanh. |
| Pedagogical expertise (English for young learners) | Contract | Cần chuyên gia giáo dục thiếu nhi, không cần full-time. |
| Content production (Starter lessons) | Hybrid | Design in-house, production có thể outsource. |

---

## 9. Can't/Won't — Defensibility

### Tại sao đối thủ không dễ copy?

| Barrier | Giải thích |
|---------|-----------|
| **Physical presence + emotional bond** | ChatGPT/Duolingo là app trên màn hình. Pika là thực thể vật lý trẻ ôm, đặt tên, coi là bạn. Không có app nào replicate được cảm xúc "con ôm Pika ngủ." Google/Apple có thể làm smart speaker cho trẻ nhưng không có hình dạng đáng yêu + brand identity dành riêng cho trẻ Việt. |
| **No-screen value** | Ba mẹ Việt Nam cực kỳ lo lắng về screen time. Pika là giải pháp duy nhất cho "học tiếng Anh mà không nhìn màn hình." Duolingo, Reading Eggs, mọi app — đều yêu cầu screen. |
| **Vietnamese-first design** | Hiểu giọng Việt (khi ASR được fix), song ngữ tự nhiên, nội dung phù hợp văn hóa Việt Nam. Global competitors (Moxie, Embodied Moxie) không có Vietnamese support. Chinese competitors (Luka, Elixir) có nhưng chất lượng tiếng Việt kém hơn sản phẩm nội địa. |
| **Data moat (building)** | Mỗi cuộc trò chuyện tạo ra data về cách trẻ Việt học tiếng Anh. Theo thời gian: hiểu pattern phát âm sai phổ biến, progression path tối ưu, content nào engage nhất. Đối thủ mới vào không có dataset này. |
| **Community + brand love** | "Rất tự hào về sản phẩm made in Việt Nam" — Q1 quote. Đây là emotional moat. Ba mẹ muốn Pika thành công vì nó là sản phẩm Việt. |

### Điểm yếu defensibility (phải acknowledge)

| Risk | Mức độ | Mitigation |
|------|--------|-----------|
| Free AI (ChatGPT, Gemini) ngày càng giỏi conversation | Cao | Pika vẫn có physical presence + child-safe + no-screen. Nhưng nếu AI quality gap quá lớn, ba mẹ sẽ chọn free. → Phải giữ conversation quality competitive. |
| Chinese hardware competitors (Elixir, Luka) vào Việt Nam | Trung bình | Giá rẻ hơn nhưng không có Vietnamese-first design. Pika's moat = ngôn ngữ + cộng đồng. |
| Chính Pika tự harm brand bằng trải nghiệm tệ | Cao | Đây là risk lớn nhất. 85% churn hiện tại = 85% ba mẹ có thể nói xấu. **Fix product quality IS the defensibility strategy.** |

---

## Đề Xuất: 3 Core Strategies cho Gia Hạn

Dựa trên toàn bộ phân tích, 3 chiến lược cốt lõi mà Pika cần thực thi — mỗi strategy map trực tiếp vào một điểm đứt trong customer journey.

### Strategy 1: "Survive the First Week" — Xóa Excitement Cliff

**Điểm đứt**: Day 3-4, khi trẻ chuyển từ nói chuyện tiếng Việt vui vẻ sang bài học tiếng Anh cứng nhắc.

**Chiến lược**: Thiết kế lại 7 ngày đầu tiên như một hành trình từ bạn bè → learning companion, không phải từ hộp hàng → phòng học.

| Ngày | Trải nghiệm | Mục tiêu |
|------|-------------|----------|
| 1-2 | Chơi, hát, trò chuyện tiếng Việt. Pika là bạn mới. | Emotional bond (Layer D) |
| 3 | Tiếng Anh nhẹ: từ đơn qua game đoán, không phải "bài học" | Exposure, không phải instruction |
| 4-5 | Starter lessons ngắn (5 phút) xen kẽ chơi. Pika chấp nhận phát âm gần đúng. | Learning habit bắt đầu hình thành |
| 6-7 | Routine ổn định: chơi + học + trò chuyện. Con quay lại vì Pika vui. | Habit formed → con tự dùng |

**Requires**: S2.2 (Fun-first onboarding) + S2.1 (Starter level) + S1.2 (ASR lenient mode)

**Success metric**: D7 retention từ ~50% → 70%

**Critical hypothesis**: *Nếu 3 ngày đầu không có bài học tiếng Anh, ba mẹ vẫn chấp nhận (không cảm thấy bị lừa).* Test bằng: parent satisfaction survey Day 3 cho nhóm fun-first vs. control.

---

### Strategy 2: "Learn Without Knowing" — Học qua Chơi, Không qua Bài

**Điểm đứt**: Trẻ coi Pika là "công cụ học" (P3 insight) → kháng cự. Free-talk là thứ trẻ thích nhất nhưng hiện tại không có learning value. Structured lessons có learning value nhưng trẻ ghét.

**Chiến lược**: Bridge the gap. Nhúng tiếng Anh vào chính những cuộc trò chuyện mà trẻ đang yêu thích, để trẻ học mà không nhận ra mình đang học.

**Cơ chế**:

```
Cuộc trò chuyện tiếng Việt tự nhiên
     ↓
Pika tự nhiên xen tiếng Anh ở keyword phù hợp
"Hôm nay trời đẹp quá nhỉ! Bạn biết 'sunny' là gì không? Đúng rồi — sunny!"
     ↓
Từ mới xuất hiện 3-4 lần trong conversation ở ngữ cảnh khác nhau
     ↓
Micro-game 30 giây xen giữa: "Đố bạn nhanh: con vật nào kêu 'woof'?"
     ↓
Cuối phiên: Pika tự nhiên tổng kết "Hôm nay mình học được 'sunny', 'cloud', 'rain' nè!"
     ↓
Data → daily summary cho ba mẹ: "Con học 3 từ mới về thời tiết"
```

**Requires**: S2.5 (Embedded English in Talk) + S3.1 (Proactive engagement) + S3.2 (Struggle fallback)

**Success metric**: Vocab retention ≥80% so với Learn mode, session length +30%, child-initiated return rate tăng

**Critical hypothesis**: *Trẻ có thể nhớ từ vựng được dạy trong conversation bằng hoặc gần bằng so với structured lesson.* Test bằng: A/B test vocab recall sau 1 tuần giữa Embedded Talk vs. standard Learn.

**Đây là strategy khó nhất nhưng nếu thành công, đây là game-changer**: Pika trở thành sản phẩm duy nhất trên thị trường dạy tiếng Anh qua tình bạn thay vì qua bài học. Không có đối thủ nào — kể cả Duolingo — làm được điều này vì họ không có voice-first + physical presence.

---

### Strategy 3: "Show the Receipt" — Cho Ba Mẹ Thấy ROI

**Điểm đứt**: Day 30, khi thuê bao hết hạn. Ba mẹ không có bằng chứng con tiến bộ → không có lý do gia hạn.

**Chiến lược**: Xây dựng "proof of value chain" — mỗi ngày một bằng chứng nhỏ, mỗi tuần một bằng chứng lớn, để đến ngày gia hạn ba mẹ đã bị thuyết phục.

**Cơ chế**:

```
Mỗi ngày:
  Push notification: "Hôm nay con học được: sunny, cloud, rain ☀️"
  → Ba mẹ mở app 10 giây, thấy giá trị nhỏ → micro-affirmation

Mỗi tuần (Thứ Hai):
  Weekly report:
  "Tuần 2: Con dùng Pika 5/7 ngày. Học 18 từ mới. Chủ đề: thời tiết, con vật.
   So với tuần 1: +6 từ, +1 ngày active. Con tiến bộ rõ!"
  → Ba mẹ thấy trajectory → macro-affirmation

Tuần 4 (trước khi renewal):
  Monthly summary:
  "Tháng đầu tiên với Pika: Con biết 52 từ tiếng Anh. Nói chuyện 4 tiếng.
   Top 5 chủ đề yêu thích: [list]. Con tự tin nói tiếng Anh hơn rõ rệt!"
  + CTA: "Gia hạn để con tiếp tục tiến bộ — chỉ 120k/tháng"
  → Ba mẹ quyết định dựa trên bằng chứng, không phải cảm giác
```

**Requires**: Data pipeline fix (capture vocab, session, pronunciation data) + S6.1 (Daily summary) + S6.2 (Weekly report)

**Success metric**: Weekly report open rate ≥50%. Parent NPS ≥7.5. Renewal intent survey ≥60%.

**Critical hypothesis**: *Ba mẹ nhận weekly report sẽ có renewal rate cao hơn đáng kể so với ba mẹ không nhận.* Test bằng: A/B — gửi report cho 50% users, so sánh renewal intent.

---

## Tổng kết: 3 Strategies = 3 Điểm Đứt = 1 Goal

```
Strategy 1                 Strategy 2                  Strategy 3
"Survive the              "Learn Without              "Show the
 First Week"               Knowing"                    Receipt"

Sửa Day 3-4          →   Sửa Day 7-30          →    Sửa Day 30+
Excitement cliff          Child disengagement         No reason to renew

S2.2 Fun-first            S2.5 Embedded English       S6.1 Daily summary
S2.1 Starter level        S3.1 Proactive engine       S6.2 Weekly report
S1.2 ASR lenient          S3.2 Struggle fallback      Data pipeline

D7 retention              Active days/month           Renewal rate
50% → 70%                 24% → 80% (15d/30d)        15% → 35%

Sprint 1-4                Sprint 3-6                  Sprint 3-6 (song song)
```

**Sequencing**: Strategy 1 phải đi trước vì nó là prerequisite. Nếu trẻ bỏ dùng Day 7, Strategy 2 và 3 không có đất để hoạt động. Strategy 2 và 3 chạy song song từ Sprint 3 (Strategy 2 cần content, Strategy 3 cần data — hai team khác nhau).

---

## Hypotheses That Must Be True

| # | Hypothesis | If Wrong... | How to Test |
|---|-----------|-------------|-------------|
| H1 | Trẻ Pre-A1 sẽ retain nếu 3 ngày đầu là chơi (không học) | Fun-first approach fails. Trẻ vẫn churn Day 7. | A/B: fun-first vs. current onboarding. Đo D7. |
| H2 | ASR lenient mode đủ tốt để trẻ không frustrate | Vẫn frustrate → vẫn churn. Phải đợi full ASR retrain. | A/B: lower threshold. Đo session abandonment. |
| H3 | Trẻ nhớ từ vựng qua embedded conversation | Không nhớ → Strategy 2 fails. Phải quay lại structured. | Vocab recall test: embedded vs. standard sau 1 tuần. |
| H4 | Ba mẹ nhận weekly report sẽ renew nhiều hơn | Report không đủ convince. Cần gì khác? | A/B: report vs. no-report. Đo renewal intent. |
| H5 | Ba mẹ chấp nhận 3 ngày đầu không có tiếng Anh | Ba mẹ complain "trả tiền mà 3 ngày chưa thấy gì" | Parent satisfaction survey Day 3. NPS ≥7. |
| H6 | 120k/tháng là mức giá ba mẹ chấp nhận khi thấy ROI | Giá vẫn quá cao dù thấy value → cần adjust | Price sensitivity survey at Day 25. |

---

## Kết luận

Pika không cần thêm tính năng. Pika cần **3 thứ hoạt động đúng**:

1. **Tuần đầu tiên không thất bại** (ASR + Starter content + Fun-first journey)
2. **Trẻ có lý do quay lại mỗi ngày** (Embedded English + Proactive engagement)
3. **Ba mẹ thấy con tiến bộ mỗi tuần** (Data pipeline + Weekly report)

Mọi thứ khác — multi-subject, gamification, adaptive AI, thêm ngôn ngữ — là tầng 2. Tầng 1 chưa có thì tầng 2 không có nền.

**Renewal rate sẽ tăng không phải vì Pika có thêm feature, mà vì Pika làm đúng 3 điều cơ bản.**

---

*Strategy canvas based on the 9-section Product Strategy Canvas framework. All insights sourced from Q1 Customer Feedback Report (150+ responses), Assumption Analysis (5 team proposals), PTL Performance Report (629 requests), Combined OST, and Pika Value Direction document.*
