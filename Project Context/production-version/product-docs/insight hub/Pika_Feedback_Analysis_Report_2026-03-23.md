# Feedback Analysis Report — Pika Robot

**Date**: 2026-03-23
**Feedback analyzed**: ~80+ responses (từ 7 nguồn dữ liệu)
**Sources**: Form survey (CSV), Facebook community posts, user interviews (churn + active), focus group interviews, follow-up interviews, internal team observations
**Period**: 11/2024 – 03/2026

---

## Overall Sentiment
- **Positive**: ~25% | **Neutral**: ~20% | **Negative**: ~55%
- **Average satisfaction score**: 6.2/10 (từ form survey, range 2–10)
- **Trend**: Đang cải thiện dần nhưng các vấn đề cốt lõi vẫn tồn tại

### Phân bổ điểm (Form Survey - 24 responses)
| Điểm | Số lượng | Tỷ lệ |
|-------|----------|--------|
| 9-10 (Promoters) | 5 | 21% |
| 7-8 (Passives) | 8 | 33% |
| 1-6 (Detractors) | 11 | 46% |

**NPS ước tính**: -25 (Detractors 46% - Promoters 21%)

---

## Top Themes

| # | Theme | Mentions | Sentiment | Segments Most Affected |
|---|-------|----------|-----------|----------------------|
| 1 | ASR (nhận diện giọng nói) kém | 30+ | Very Negative | Trẻ giọng miền Nam, trẻ nhỏ (3-6t), trẻ nói tiếng Anh |
| 2 | Nội dung học quá khó / chưa phù hợp trình độ | 25+ | Negative | Trẻ mới bắt đầu, pre-A1 |
| 3 | Pika không vào chế độ ngủ / nói không ngừng | 15+ | Negative | Tất cả users |
| 4 | Thiếu từ vựng cơ bản & ôn luyện | 15+ | Negative | Trẻ lớp 1-2, mới học TA |
| 5 | App phụ huynh UX kém | 12+ | Negative | Phụ huynh |
| 6 | Pika cắt lời / thời gian chờ quá ngắn | 10+ | Negative | Trẻ nhỏ, trẻ chậm |
| 7 | WiFi disconnect / phải kết nối lại | 10+ | Negative | Tất cả users |
| 8 | Thiếu bài hát đa dạng | 8+ | Negative | Trẻ nhỏ (3-6t) |
| 9 | Trò chuyện hay nhưng lan man, thiếu chủ đề | 8+ | Mixed | Active users |
| 10 | Cá nhân hóa chưa đủ (đa profile, nhớ thông tin) | 8+ | Negative | Gia đình nhiều con |
| 11 | Pika dễ thương, giọng TA hay | 15+ | Positive | Tất cả |
| 12 | Trò chơi đoán / mở khóa kỹ năng hấp dẫn | 8+ | Positive | Trẻ 6-10t |

---

## Theme Deep-Dive

### Theme 1: ASR (Nhận diện giọng nói) kém — 30+ mentions, Very Negative

**What users are saying**:
> "Pika nghe rất tệ, không nghe được nhiều từ tiếng Anh" — Detractor, score 2
> "Trẻ nói Pika ngu... Pika nghe sai, không hiểu trẻ, trẻ phải nói đi nói lại nhiều lần" — Churn interview
> "Bé phải hét to mà thậm chí có nhiều lúc vẫn k nghe" — Community post
> "mình đọc theo mà hơn chục lần nó cứ bảo ko đúng" — Community post

**Root cause**:
- ASR chưa handle tốt giọng miền Nam, giọng miền Trung, giọng trẻ nhỏ
- Nhận diện tiếng Anh từ trẻ em (phát âm chưa chuẩn) rất kém
- Khi nghe sai, Pika phản hồi "linh tinh" → gây frustration cho trẻ → churn

**Impact**: **Rất cao** — Đây là nguyên nhân churn #1. 4/5 phụ huynh churn đều report vấn đề này. Trẻ chán vì nói mà Pika không hiểu.

**Recommendation**:
1. Ưu tiên P0: Cải thiện ASR cho giọng trẻ em (cả TV và TA)
2. Khi ASR không confident, thay vì phản hồi sai → hỏi lại nhẹ nhàng, không dùng lặp lại "ù tai"
3. Hỗ trợ đa giọng vùng miền (miền Nam, miền Trung)

---

### Theme 2: Nội dung học quá khó / không phù hợp trình độ — 25+ mentions, Negative

**What users are saying**:
> "pre-A1 vẫn khó cho trẻ, trẻ hay nhăn mặt khi không hiểu" — Churn interview
> "bé 6 tuổi mới tiếp xúc TA, câu học mở đầu đã khá dài... colecting cute things, making slime" — Score 10 nhưng góp ý mạnh
> "Chương trình học chưa phù hợp cho bé mới bắt đầu, phần song ngữ nói TV chậm nhưng TA còn nhanh quá" — Score 3

**Root cause**:
- Không có level thực sự "zero" cho trẻ chưa biết gì về TA
- Thiếu bước học từ vựng đơn lẻ cơ bản (book, pen, ball...) trước khi vào cụm/câu
- Tốc độ nói TA quá nhanh ngay cả ở chế độ "dễ nghe"
- PH chọn pre-A1 nhưng nội dung vẫn quá khó cho trẻ lớp 1

**Impact**: **Rất cao** — Trẻ không hiểu → chán → không muốn dùng → churn. Đặc biệt ảnh hưởng nhóm D1-D7 retention.

**Recommendation**:
1. Tạo level "Starter/Beginner" dưới pre-A1: học từ đơn, đồ vật xung quanh
2. Cho phép PH tùy chỉnh level chi tiết hơn
3. Giảm tốc độ nói TA ở level thấp
4. Guide PH không ép trẻ nói TA khi chưa sẵn sàng

---

### Theme 3: Pika không vào chế độ ngủ / nói không ngừng — 15+ mentions, Negative

**What users are saying**:
> "Pika vẫn tự chào tự chúc mãi ko ngừng" — Community post
> "phải có cách cho Pika ngủ bằng lệnh hoặc app. nó cứ nói liên hồi" — Community post
> "nó cứ tự dẫn chuyện khi không nhận được phản hồi" — Community post

**Root cause**: Thiếu logic timeout / sleep mode khi không có tương tác

**Impact**: **Trung bình-Cao** — Gây khó chịu, tạo ấn tượng robot "không thông minh"

**Recommendation**:
1. Tự động sleep sau 3-5 câu không có phản hồi
2. Hỗ trợ voice command "Pika đi ngủ đi" / "Good night Pika"
3. Nút tắt nhanh trên app

---

### Theme 4: Thiếu từ vựng cơ bản & ôn luyện — 15+ mentions, Negative

**What users are saying**:
> "cần thêm phần học từ vựng từng từ cho bé" — Score 8
> "các bạn mới học TA chủ yếu cần mở rộng vốn từ... bài học mỗi ngày có quá nhiều câu, các bạn chậm theo không kịp" — Community post
> "PH mong muốn bố mẹ có thể thêm từ mới lên app để pika và con cùng ôn lại" — Community post

**Root cause**: Giáo trình focus vào câu/cụm, thiếu phần drill từ vựng đơn lẻ

**Impact**: **Cao** — Trẻ mới học không có nền tảng từ vựng, không theo kịp bài

**Recommendation**:
1. Thêm module học từ vựng theo chủ đề (con vật, màu sắc, đồ dùng...)
2. Áp dụng Spaced Repetition (Ebbinghaus forgetting curve) để ôn từ
3. Cho PH thêm từ vựng custom qua app
4. Tích hợp flashcard hoặc quiz đố từ vựng

---

### Theme 5: App phụ huynh UX kém — 12+ mentions, Negative

**What users are saying**:
> "UI đẹp mà UX tệ... mất nửa màn hình hiện con pika mặc đồ bơi... nút LÊN LỊCH bị che" — Community post
> "phần lộ trình học thực sự tệ và bất tiện... ko biết bài nào chưa hoàn thiện" — Community post
> "UX lộ trình hơi khó hiểu, không biết bài nào con đã học hoặc chưa học" — Churn interview

**Root cause**: App ưu tiên visual design hơn usability; thiếu thông tin tiến độ rõ ràng

**Impact**: **Trung bình** — PH báo ít dùng app, chỉ dùng đổi lộ trình và set ngôn ngữ

**Recommendation**:
1. Redesign lộ trình học: hiển thị rõ bài đã học/chưa học, số sao
2. Đưa nút chức năng chính (lên lịch, giao bài) lên vị trí dễ thấy
3. Thêm notification khi con hoàn thành bài
4. Cho phép chỉnh sửa sở thích, thông tin cá nhân hóa trên app

---

### Theme 6: Pika cắt lời / thời gian chờ quá ngắn — 10+ mentions, Negative

**What users are saying**:
> "Pika ko cho con suy nghĩ, nếu con đang nói mà ngừng vài giây suy nghĩ thì Pika sẽ nói vào luôn" — Community post
> "Thời gian chờ phản hồi của bé hơi ngắn... chưa hết câu thì Pika đã cắt lời" — Community post
> "Pika phản xạ quá nhanh, bé ngập ngừng là Pika vào bắt chuyện luôn" — Score 6

**Root cause**: Silence detection threshold quá ngắn, không phân biệt pause vs. end-of-turn

**Impact**: **Cao** — Đặc biệt ảnh hưởng trẻ nhỏ (nói chậm, cần suy nghĩ), gây frustration

**Recommendation**:
1. Tăng silence threshold, đặc biệt cho trẻ nhỏ
2. Phân biệt giữa pause giữa câu và kết thúc lượt nói
3. Cho phép PH điều chỉnh tốc độ phản hồi

---

### Theme 7: WiFi disconnect / phải kết nối lại — 10+ mentions, Negative

**What users are saying**:
> "chuyển đổi giữa 2 mạng wifi... phải thiết lập lại từ đầu" — Score 8
> "rút sạc qua đêm thì không bắt lại được WIFI... ko lưu lại tín hiệu" — Community post

**Root cause**: Pika không lưu WiFi credentials sau khi ngắt kết nối / khởi động lại

**Impact**: **Trung bình** — Gây phiền nhưng không phải lý do churn chính

**Recommendation**: Lưu persistent WiFi credentials, tự động reconnect

---

## Segment Analysis

| Segment | Volume | Avg Sentiment | Top Theme | Key Difference |
|---------|--------|-------------|-----------|---------------|
| Trẻ 3-5 tuổi | ~15 | Negative | ASR kém + nội dung quá khó | Cần PH ngồi cạnh, ngôn ngữ chưa hoàn thiện, chưa phù hợp |
| Trẻ 6-8 tuổi (beginner) | ~25 | Mixed | Nội dung khó + thiếu từ vựng | Cần level "zero", học từ đơn trước |
| Trẻ 8-10 tuổi (có base) | ~15 | Positive-Mixed | Trò chuyện tốt, muốn thêm depth | Nhóm hài lòng nhất, muốn level cao hơn (B1+) |
| Trẻ 11+ tuổi | ~5 | Negative | Bận đi học, không dùng | Không phù hợp target |
| PH churn (5 interviews) | 5 | Very Negative | ASR + nội dung khó | 4/5 báo ASR sai, trẻ chán bỏ dùng |
| PH active (3 interviews) | 3 | Mixed-Positive | Muốn cải thiện depth | Vẫn dùng nhưng kỳ vọng cao hơn |

---

## Notable Quotes

> "Con thích Pika quá mẹ ơi, nói chuyện với Pika thật vui. Nhưng Pika ko cho con suy nghĩ" — PH active, con gái

> "Pika nghe quá kém, nội dung trò chuyện nhạt nhẽo khiến con không hứng thú" — Score 2, Detractor

> "Điều con thích ở Pika là vì con có thêm 1 người bạn" — Score 8, Passive

> "Dùng Pika mà mình rất tự hào về sản phẩm made in Việt Nam" — Score 6, nhưng emotional connection cao

> "Trẻ cảm thấy Pika ngu" — Churn interview (thẳng thắn từ trẻ)

> "tình cờ biết được thời điểm này bác Hiệp đang triển khai 1 con robot... quả là 1 công đôi việc. rất mong có thể được cùng con trải nghiệm sớm" — Early Adopter Survey, rất enthusiastic

---

## Insights từ Market Research (Focus Group & Follow-up Interviews)

### PH mong muốn gì từ robot:
1. **Robot là "người bạn", không phải "công cụ học"**: PH muốn robot tâm sự, hỏi về ngày hôm nay của con 5-10p đầu, sau đó mới học
2. **Thiên về giao tiếp > ngữ pháp**: Vietnam đang yếu kỹ năng giao tiếp, cần sửa phát âm và chấm điểm
3. **Báo cáo tiến độ chi tiết**: Tiến độ nhanh/chậm, bảng xếp hạng, phần trăm hoàn thành, đánh giá chất lượng (không chỉ lượng)
4. **Gamification mạnh**: Streak (kiểu Duolingo), sao, bảng xếp hạng, phần thưởng đặc biệt, events thi đua
5. **Cá nhân hóa sâu**: Nhớ sở thích, gọi tên, điều chỉnh theo trình độ từng bé, nhắc nhở theo lịch
6. **Phương pháp Spaced Repetition**: Nhắc lại từ vựng theo đường cong Ebbinghaus
7. **Nội dung chất lượng, không theo trend**: PH muốn giáo dục bền vững, không "mì ăn liền"
8. **Linh hoạt ngôn ngữ**: Cho chọn 100% TA, song ngữ, hoặc chỉ TV tùy level

---

## Trends (D1 → D7 Retention Observation - từ Backlog Observation)

- **D1-D7 retention thấp**: Nhiều case chán ngay từ ngày đầu
- **Giả thuyết 1**: Sự rời rạc giữa các ngày và hoạt động trong cùng 1 ngày
- **Giả thuyết 2 (mạnh hơn)**: User chưa hiểu sản phẩm, chưa biết dùng đúng cách → cần onboarding tốt hơn
- **Pattern churn**: ASR kém → trẻ frustrated → bỏ dùng (thường trong 1-2 tuần đầu)

---

## Actionable Insights (Xếp theo Priority)

### P0 — Critical (ảnh hưởng trực tiếp retention & churn)
1. **Cải thiện ASR cho giọng trẻ em** — Đây là "make or break". 4/5 PH churn báo vấn đề này
2. **Tạo level Starter dưới pre-A1** — Trẻ mới bắt đầu cần học từ đơn, không phải câu/cụm dài
3. **Fix sleep mode** — Pika phải tự ngủ khi không có response, hỗ trợ voice command ngủ

### P1 — High (ảnh hưởng satisfaction & engagement)
4. **Tăng silence threshold** — Đừng cắt lời trẻ khi đang suy nghĩ
5. **Thêm module từ vựng + Spaced Repetition** — Nhu cầu cao từ cả PH survey và community
6. **Cải thiện onboarding** — Guide PH hiểu cách dùng sản phẩm đúng, tránh ép trẻ
7. **Lưu WiFi persistent** — Quick fix, giảm friction đáng kể

### P2 — Medium (ảnh hưởng long-term value)
8. **Redesign app PH**: Lộ trình rõ ràng, notification, chỉnh cá nhân hóa
9. **Báo cáo tiến độ chi tiết cho PH** — Tuần/tháng, điểm mạnh/yếu, % hoàn thành
10. **Tích hợp nội dung học vào Buddy Talk** — Tạo trải nghiệm liền mạch learn → talk
11. **Gamification**: Streak, BXH, thưởng sao, events thi đua
12. **Hỗ trợ multi-profile** — Nhiều gia đình có 2-3 con dùng chung 1 Pika

### P3 — Nice to have
13. Thêm bài hát đa dạng (TV + TA)
14. Giọng miền Nam
15. Thêm level B1, B2
16. Thêm ngôn ngữ mới (tiếng Trung)

---

## Gaps — Những gì feedback chưa cho biết

1. **Chưa có data định lượng D1-D30 retention** chính xác theo cohort
2. **Chưa rõ tỷ lệ churn thực tế** và lý do chi tiết theo segment tuổi
3. **Chưa có A/B test** để validate giải pháp nào hiệu quả nhất cho ASR
4. **Thiếu feedback từ trẻ trực tiếp** (hầu hết qua PH) — cần quan sát trực tiếp hành vi trẻ dùng Pika
5. **Chưa đánh giá được hiệu quả học tập thực tế** — con có tiến bộ TA sau N tháng dùng không?
6. **Thiếu data về willingness to pay** cho subscription sau 6 tháng KM

---

## Suggested Follow-up Research

- "Muốn tạo **user personas** từ các pattern feedback này?"
- "Cần **triage top themes thành feature requests** trên backlog?"
- "Muốn **thiết kế interview script** để đào sâu vấn đề ASR và D1-D7 retention?"
