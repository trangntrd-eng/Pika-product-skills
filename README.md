# Pika Product Skills — Bộ Kỹ Năng PM Cho Team Product Pika

> 84 skills, 40 workflows, 12 plugins — từ discovery đến learning design, execution, launch, và growth.
> Thiết kế riêng cho EdTech B2C nhắm đến trẻ em và phụ huynh.

---

## Bắt đầu nhanh

| Bạn muốn... | Dùng lệnh |
|---|---|
| Đánh giá project đang ở đâu | `/pm` |
| Chạy vòng discovery | `/discover` |
| Viết PRD | `/write-prd` |
| Thiết kế trải nghiệm học | `/learning-design` |
| Kiểm tra an toàn trẻ em | `/child-safety` |
| Thiết kế engagement & gamification | `/engagement-design` |
| Lên chiến lược sản phẩm | `/strategy` |
| Chuẩn bị launch | `/plan-launch` |

Hoặc dùng `/pm` để orchestrator tự đánh giá project và gợi ý bước tiếp theo.

---

## Cấu trúc tổng quan

Workspace này gồm **12 plugins** chia làm 3 nhóm:

### Nhóm 1 — PM Cốt Lõi (từ PM Skills Marketplace gốc)

Đây là bộ skill PM tổng quát, dùng được cho mọi loại sản phẩm:

| Plugin | Mô tả | Skills | Lệnh chính |
|--------|--------|--------|------------|
| **pm-product-discovery** | Ideation, thí nghiệm, giả định, phỏng vấn, OST | 13 | `/discover`, `/interview`, `/brainstorm` |
| **pm-product-strategy** | Vision, business model, pricing, SWOT, Porter | 12 | `/strategy`, `/business-model`, `/pricing` |
| **pm-execution** | PRD, OKR, roadmap, sprint, user stories | 15 | `/write-prd`, `/plan-okrs`, `/sprint` |
| **pm-market-research** | Persona, phân khúc, journey map, sizing | 7 | `/research-users`, `/competitive-analysis` |
| **pm-data-analytics** | SQL, phân tích cohort, A/B test | 3 | `/write-query`, `/analyze-cohorts` |
| **pm-go-to-market** | GTM, growth loops, beachhead, battlecard | 6 | `/plan-launch`, `/growth-strategy` |
| **pm-marketing-growth** | Positioning, North Star, naming | 5 | `/market-product`, `/north-star` |
| **pm-toolkit** | Resume review, NDA, privacy policy, grammar | 4 | `/write-prd`, `/proofread` |

### Nhóm 2 — EdTech Chuyên Sâu (mới tạo cho Pika)

Đây là 3 plugins đặc thù cho sản phẩm EdTech nhắm vào trẻ em — thứ mà bộ PM gốc không có:

| Plugin | Mô tả | Skills | Lệnh chính |
|--------|--------|--------|------------|
| **pm-learning-design** | Mục tiêu học tập, chương trình, mô hình sư phạm, đánh giá, feedback, đo lường hiệu quả | 7 | `/learning-design` |
| **pm-child-safety** | COPPA/GDPR-K, consent phụ huynh, age gating, data minimization, safe UX | 5 | `/child-safety` |
| **pm-engagement-design** | Gamification, progression, habit loop, social learning, parent engagement | 5 | `/engagement-design` |

### Nhóm 3 — Orchestrator (bộ điều phối)

| Plugin | Mô tả | Lệnh |
|--------|--------|------|
| **pm-orchestrator** | Đánh giá trạng thái project, gợi ý skill phù hợp, quản lý phụ thuộc giữa các bước, inject context từ artifacts trước đó | `/pm` |

---

## Orchestrator — Cách hoạt động

`/pm` là lệnh chính điều phối toàn bộ. Nó có 5 chế độ:

| Cách gọi | Chế độ | Ví dụ |
|-----------|--------|-------|
| `/pm` (không có gì thêm) | **Đánh giá** — project đang ở phase nào, thiếu gì, nên làm gì tiếp | `/pm` |
| `/pm` + deliverable cụ thể | **Thực thi** — kiểm tra phụ thuộc, inject context, chạy skill | `/pm Giúp mình viết PRD` |
| `/pm` + mục tiêu lớn | **Theo path** — chạy workflow nhiều bước với checkpoint | `/pm Chuẩn bị launch Photo-to-Lesson` |
| `/pm` + data mới | **Tiếp nhận** — ghi nhận data mới, gợi ý skill xử lý | `/pm Mình vừa phỏng vấn xong 5 user` |
| `/pm` + câu hỏi | **Tư vấn** — trả lời dựa trên toàn bộ context project | `/pm Nên ưu tiên retention hay acquisition?` |

### Lifecycle Phases

Orchestrator theo dõi project qua **7 phase** (bao gồm phase Learning Design mới cho EdTech):

```
Discovery → Strategy → Learning Design → Planning → Validation → Go-to-Market → Growth
```

Mỗi phase có exit criteria rõ ràng. Orchestrator sẽ cảnh báo nếu bạn nhảy phase mà chưa hoàn thành artifacts cần thiết.

### Paths dựng sẵn cho EdTech

| Path | Mô tả | Số bước |
|------|--------|---------|
| `edtech-new-learning-feature` | Từ learning objective → curriculum → pedagogy → PRD → test → efficacy | 15 |
| `edtech-retention-sprint` | Chẩn đoán retention → engagement → gamification → parent experience | 9 |
| `edtech-compliance-review` | COPPA audit → data minimization → consent → age gating → safe UX | 5 |
| `new-product` | Journey 0→1 đầy đủ (PM tổng quát) | 19 |
| `existing-product-feature` | Feature mới trên sản phẩm hiện có | 12 |
| `discovery-sprint` | Discovery nhanh 1 tuần | 7 |

---

## Chi tiết 3 Plugin EdTech Mới

### pm-learning-design — Thiết kế trải nghiệm học

Đây là plugin quan trọng nhất cho EdTech. Nó giải quyết câu hỏi: **"Feature này thực sự dạy được gì?"**

| Skill | Mô tả | Framework |
|-------|--------|-----------|
| `design-learning-objectives` | Xác định mục tiêu học tập theo Bloom's Taxonomy + Backward Design | Wiggins & McTighe, Anderson & Krathwohl |
| `select-pedagogy-model` | Chọn mô hình sư phạm phù hợp (spaced repetition, mastery, scaffolding, game-based...) | Bloom, Vygotsky, Gee, Ebbinghaus |
| `design-curriculum-structure` | Thiết kế cấu trúc chương trình: scope, sequence, module, unit, lesson | Bruner (Spiral Curriculum) |
| `design-assessment` | Thiết kế đánh giá formative + summative + diagnostic | Webb's DOK, Black & Wiliam |
| `design-feedback-system` | Thiết kế hệ thống feedback: phản hồi lỗi, growth mindset, báo cáo phụ huynh | Hattie & Timperley, Dweck |
| `design-learning-path` | Thiết kế lộ trình học adaptive: entry point, progression, review, edge case | Vygotsky (ZPD), Csikszentmihalyi (Flow) |
| `evaluate-learning-efficacy` | Đo lường hiệu quả học tập: pre/post test, effect size, Kirkpatrick model | Kirkpatrick, Hattie, Cohen |

**Khi nào dùng:** Trước khi viết PRD cho bất kỳ feature học tập nào. Learning design brief sẽ bổ sung cho PRD — PRD nói "build cái gì", learning design brief nói "dạy như thế nào".

### pm-child-safety — An toàn trẻ em & Compliance

| Skill | Mô tả | Áp dụng |
|-------|--------|---------|
| `assess-coppa-compliance` | Audit theo COPPA (US), GDPR-K (EU), và Nghị định 13/2023 (VN) | Khi launch feature mới, vào thị trường mới, hoặc review định kỳ |
| `design-parental-consent` | Thiết kế flow xin phép phụ huynh (5 bước: age gate → identify → notice → consent → confirm) | Khi thiết kế onboarding |
| `design-age-gating` | Phân quyền feature theo lứa tuổi (dựa trên Piaget) | Khi product phục vụ nhiều lứa tuổi |
| `audit-data-minimization` | Kiểm tra và giảm thiểu data thu thập từ trẻ em | Khi review privacy, chuẩn bị app store |
| `design-safe-ux` | Kiểm tra dark pattern, content safety, session management, communication safety | Khi thiết kế bất kỳ tương tác nào cho trẻ |

**Khi nào dùng:** Trước mỗi lần submit app store, khi thêm feature thu thập data mới, hoặc ít nhất mỗi năm 1 lần.

### pm-engagement-design — Engagement & Retention

| Skill | Mô tả | Framework |
|-------|--------|-----------|
| `design-gamification-system` | Thiết kế reward economy, badge, level gắn với learning milestone (không phải screen time) | SDT (Deci & Ryan), Octalysis (Yu-kai Chou) |
| `design-progression-mechanics` | Skill tree, difficulty curve, mastery visualization | Flow Theory (Csikszentmihalyi) |
| `design-habit-loops` | Trigger, streak (ethical), session start/end, re-engagement | Hooked (Nir Eyal) + ethical adaptation |
| `design-social-learning` | Family learning, peer challenge, collaborative goals (age-appropriate) | Vygotsky, Topping (Peer Tutoring) |
| `design-parent-engagement` | Dashboard phụ huynh, communication cadence, conversation starter, renewal support | Hattie (Parental Involvement d=0.51) |

**Khi nào dùng:** Sau khi đã có learning design. Engagement phục vụ learning, không phải ngược lại.

---

## Cách dùng trong thực tế

### Ví dụ 1: Thiết kế feature "Ôn Bài" mới

```
1. /pm                                    → Đánh giá trạng thái project
2. /discover Tính năng ôn bài cho Pika    → Discovery: persona, giả định, thí nghiệm
3. /learning-design Hệ thống ôn bài      → Learning objectives, pedagogy, curriculum
4. /engagement-design Ôn Bài              → Gamification, habit loop, parent dashboard
5. /child-safety Ôn Bài                   → Compliance check
6. /write-prd Ôn Bài                      → PRD (auto-inject learning design + engagement context)
```

### Ví dụ 2: Cải thiện retention H1 2026

```
1. /pm Retention đang giảm, nên làm gì?  → Orchestrator gợi ý retention sprint path
2. /analyze-feedback [đính kèm feedback]  → Phân tích feedback user
3. /engagement-design Cải thiện retention → Habit loop, gamification, parent engagement
4. /pm Tiếp theo nên làm gì?             → Gợi ý bước tiếp
```

### Ví dụ 3: Chuẩn bị launch ra thị trường mới

```
1. /child-safety Pika Robot — thị trường US  → COPPA compliance audit
2. /plan-launch Pika Robot cho thị trường US → GTM strategy
3. /strategy Mở rộng sang US                → Chiến lược sản phẩm
```

---

## Cấu trúc thư mục

```
pm-skills-main/
├── pm-orchestrator/            ← Bộ điều phối chính (/pm)
│   ├── skill-graph.yaml        ← Đồ thị phụ thuộc giữa 84 skills
│   ├── commands/pm.md          ← Lệnh /pm
│   └── skills/assess-project/  ← Đánh giá trạng thái project
│
├── pm-learning-design/         ← 🆕 Thiết kế trải nghiệm học
├── pm-child-safety/            ← 🆕 An toàn trẻ em & compliance
├── pm-engagement-design/       ← 🆕 Engagement & retention
│
├── pm-product-discovery/       ← Discovery & validation
├── pm-product-strategy/        ← Strategy & business model
├── pm-execution/               ← PRD, OKR, roadmap, sprint
├── pm-market-research/         ← Persona, segmentation, sizing
├── pm-data-analytics/          ← SQL, cohort, A/B test
├── pm-go-to-market/            ← GTM, growth, battlecard
├── pm-marketing-growth/        ← Positioning, North Star
├── pm-toolkit/                 ← Utilities (resume, NDA, grammar)
│
└── Project Context/            ← Data thực tế của Pika
    └── production-version/
        └── product-docs/       ← Feedback, research, insights, proposals
```

Mỗi plugin có cấu trúc giống nhau:
```
pm-[tên-plugin]/
├── .claude-plugin/plugin.json  ← Metadata
├── commands/                   ← Các lệnh /slash-command
│   └── [tên-lệnh].md
└── skills/                     ← Các skill
    └── [tên-skill]/
        └── SKILL.md
```

---

## Hướng dẫn đóng góp cho team Pika

Các bạn product trong team có thể đóng góp và mở rộng workspace này. Dưới đây là các hướng cụ thể:

### 1. Thêm Project Context (dễ nhất, ai cũng làm được)

Thư mục `Project Context/production-version/product-docs/` chứa data thực tế mà orchestrator dùng để inject context. Bạn có thể thêm:

- **User feedback mới** → `insight hub/user-feedback/`
- **Kết quả phỏng vấn** → `insight hub/proposals/`
- **Report feature** → `insight hub/feature-report/`
- **Insight & phân tích** → `insight hub/insight/`
- **Market research** → `insight hub/market-research/`

**Format:** Markdown (.md) hoặc CSV. Đặt tên file rõ ràng, có ngày tháng.

### 2. Tạo Skill mới

Khi bạn phát hiện một quy trình PM lặp đi lặp lại mà chưa có skill, hãy tạo một skill mới:

**Bước 1:** Tạo thư mục `pm-[plugin-phù-hợp]/skills/[tên-skill-mới]/SKILL.md`

**Bước 2:** Viết SKILL.md theo format:

```markdown
---
name: ten-skill-kebab-case
description: "Mô tả ngắn. Use when [khi nào dùng skill này]."
---

## Tên Skill Đầy Đủ

[1-2 đoạn giải thích skill này làm gì và tại sao quan trọng]

### Domain Context
[Framework, tác giả, lý thuyết nền tảng — trích dẫn nguồn cụ thể]

### Context
You are [vai trò] for **$ARGUMENTS**.

### Instructions
1. **Bước 1**: [hướng dẫn cụ thể]
2. **Bước 2**: [hướng dẫn cụ thể]
...

### Output Format
[Template markdown cho output]

### Further Reading
[Link đến sách, bài viết, nghiên cứu liên quan]
```

**Bước 3:** Thêm skill vào `pm-orchestrator/skill-graph.yaml`:

```yaml
ten-skill-moi:
  phase: [discover|strategy|design-learning|plan|validate|launch|grow|any]
  plugin: pm-[tên-plugin]
  produces: [loai-artifact-tao-ra]
  requires: [artifact-can-co-truoc]
  enhancedBy: [artifact-giup-tot-hon]
  effort: [quick|moderate|deep]
  description: "Mô tả 1 dòng"
  command: "/[ten-lenh]"
```

### 3. Tạo Command mới (workflow nhiều bước)

Command chain nhiều skill lại thành workflow. Tạo file `pm-[plugin]/commands/[tên-lệnh].md`:

```markdown
---
description: Mô tả ngắn
argument-hint: "<gợi ý argument>"
---

# /tên-lệnh -- Tiêu Đề

## Invocation
[Ví dụ cách gọi]

## Workflow
### Step 1: [Tên bước]
Apply skill `tên-skill`.
**Checkpoint:** [Hỏi user trước khi đi tiếp]

### Step 2: [Tên bước]
...
```

### 4. Các skill gợi ý team nên tạo thêm

Dựa trên context của Pika, đây là những skill chưa có mà team nên cân nhắc:

| Skill gợi ý | Plugin phù hợp | Lý do |
|---|---|---|
| `design-content-taxonomy` | pm-learning-design | Pika cần hệ thống phân loại nội dung (topic, level, format) |
| `plan-content-pipeline` | pm-learning-design | Quy trình sản xuất content: viết → review → record → publish |
| `design-onboarding-flow` | pm-engagement-design | Onboarding riêng cho EdTech (child + parent flow) |
| `analyze-learning-data` | pm-data-analytics | Phân tích data học tập: completion rate, mastery rate, time-to-mastery |
| `design-robot-interaction` | pm-learning-design (hoặc plugin mới) | Thiết kế tương tác voice/robot đặc thù cho Pika Robot |
| `localization-strategy` | pm-go-to-market | Chiến lược mở rộng ngôn ngữ/thị trường (VN → SEA → global) |
| `subscription-lifecycle` | pm-engagement-design | Phân tích vòng đời subscription: trial → paid → renewal → churn |
| `parent-interview-script` | pm-product-discovery | Script phỏng vấn đặc thù cho phụ huynh (khác với user interview thông thường) |

### 5. Cập nhật skill hiện có

Nếu bạn dùng một skill và thấy thiếu sót (ví dụ: framework không phù hợp cho trẻ em VN, output template cần thêm mục), hãy sửa trực tiếp file SKILL.md và tạo PR.

**Nguyên tắc khi sửa:**
- Giữ format hiện có (YAML frontmatter, ### sections)
- Trích dẫn nguồn nếu thêm framework mới
- Cập nhật `skill-graph.yaml` nếu thay đổi produces/requires

### 6. Quy trình đóng góp

```
1. Tạo branch mới: git checkout -b feat/ten-skill-moi
2. Thêm/sửa files
3. Chạy validate: python validate_plugins.py (nếu có)
4. Commit và push
5. Tạo Pull Request, mô tả rõ thay đổi
```

---

## Credit

- **PM Skills Marketplace gốc** — Paweł Huryn, [The Product Compass](https://www.productcompass.pm)
- **EdTech plugins** (pm-learning-design, pm-child-safety, pm-engagement-design) — Pika Product Team
- **Frameworks tham khảo chính:**
  - Teresa Torres — *Continuous Discovery Habits*
  - Wiggins & McTighe — *Understanding by Design*
  - Bloom, Anderson & Krathwohl — Bloom's Revised Taxonomy
  - Vygotsky — Zone of Proximal Development
  - Hattie — *Visible Learning*
  - Dweck — Growth Mindset
  - Deci & Ryan — Self-Determination Theory
  - Nir Eyal — *Hooked* (adapted ethically for children)
  - Kirkpatrick — Four Levels of Evaluation

## License

MIT — xem [LICENSE](LICENSE).
