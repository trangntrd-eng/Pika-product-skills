# PROBLEM BREAKDOWN"""
(image1)
(image2)
## North star metrics: **Retention D7/D30**
- Ưu tiên trong tháng 3, 4, 5 là nhanh chóng cải thiện **retention D7**
- **Giả định**: Trải nghiệm học và Retention của những user có bố mẹ hỗ trợ và tham gia sâu vào việc học là tốt hơn
- **Areas to improve:
  **Bố mẹ chưa dễ dàng nắm được hết cách sử dụng robot
  Orchestration hiện tại hạn chế sự tham gia của bố mẹ
  **→ Initiatives**:
  **P1 - Activation**: đảm bảo bố mẹ hiểu rõ cách sử dụng robot, những gì họ có thể làm với robot
  **P2 - Build hook ux loop cho phụ huynh**: habit forming cho cả phụ huynh thông qua việc build loop ux có phản hồi và reward đầy đủ cho các action của phụ huynh
(image3)
## **P1 - Activation**
## **1.1. Định nghĩa Activation với bố mẹ**
## **Phụ huynh hiểu toàn bộ giá trị mà robot mang lại**
**Activation** không chỉ là việc người dùng mở app, mà là một hành trình tâm lý và hành vi gồm 3 giai đoạn chính:

  - **Nhận biế**t: Người dùng bắt đầu biết đến các giá trị sử dụng của Pika
  - **Dùng thử**: Trải nghiệm thực tế các tính năng
  - **Hình thành thói quen**: Quay lại sử dụng tính năng thêm các lần tiếp theo

**Cốt lõi của Activation**: Quan trọng nhất là giúp người dùng nhận biết được đẩy đủ các JTBD mà họ có thể làm với Pika, giảm rào cản khiến phụ huynh không tiếp cận được các tính năng của robot. Quan trọng thứ 2 là đảm bảo các hành vi của người dùng engage được phản hồi / reward đầy đủ trên app.
## **Pika tự hành vừa dạy học vừa làm bạn với con**
## **Pika giúp con hình thành thói quen**
## **Pika hỗ trợ dạy theo yêu cầu của bố mẹ**
## Tính năng: Todo list, Learn & Talk
- **Hiểu
  **Giới thiệu về cách hoạt động của Pika trong onboarding 
  kênh app
  kênh robot
- **Biết cách**
- **Nhận được đầy đủ feedback
  **Qua report
  Notification liên quan đến report
## Tính năng: đặt nhắc nhở (báo thức)
- **Hiểu
  **Giá trị này gán vào các tính năng: giao bài trong lộ trình + tự tạo bài học từng vựng
  Giới thiệu khi bố mẹ nhận feedback trên report lần đầu tiên (vd: bố mẹ có thể giao thêm bài...)
- **Biết cách
  **
- **Nhận được đầy đủ feedback
  **Qua report
  Notification liên quan đến report
- **Hiểu
  **Phụ huynh có thể sử dụng Pika để giúp con hình thành thói quen tốt
  vd: đi ngủ sớm
- **Biết cách
  **Hướng dẫn tạo thử một thói quen tốt
- **Nhận được đầy đủ feedback
  **VD: con bỏ qua hoặc tắt báo thức → cần feedback lại cho bố mẹ
## Tính năng: nội dung lồng ghép trong free talk
- **Hiểu
  **
- **Biết cách
  **
- **Nhận được đầy đủ feedback
  **
## **1.2. Các initiatives để tối ưu activation với bố mẹ**
- **Hiểu** luồng hoạt động của robot (ux view của orchestration) tới level rationale (vì sao lại thế?)
- **Nhận biết **được các tính năng có thể sử dụng để engage vào luồng hoạt động mặc định:
  Giao bài & tạo bài
  Giao các hoạt động giải trí (hát / kể chuyện)
  Nhắc việc
- **Nhận được đầy đủ feedback** cho các hành động engage của mình
  Lv.1: Xác nhận thành công và nhìn thấy robot phản hồi
  Lv2: Xem lại đc kết quả trên app (optional - tuỳ tính năng)
## **L0 - Redesign / Refactor app**
## **L2 - Cẩm nang sử dụng robot**
**Goal: **Đảm bảo các tính năng được sắp xếp một cách rõ ràng, tạo một “bảng điều khiển” phù hợp nhất với mental model của phụ huynh để invite họ engage vào quá trình học của con
  - Anh Hải design đảm bảo độ systematic của các mảnh to, trong từng mảnh to thì module hoá phù hợp từng tính năng
  - Cần UX research để đưa ra các design decision ở ngọn → surface value tới phụ huynh tốt nhất
**Goal: **Cung cấp cẩm nang sử dụng robot in-app phục vụ việc sử dụng robot của bố mẹ (khác với HDSD)
  - Cung cấp hướng dẫn dựa trên Use Case (Tình huống sử dụng) thay vì liệt kê tính năng
  - Tập trung vào Point of Delivery (PoD): Giúp họ biết, dùng thử và duy trì
  - Trả lời câu hỏi: "Pika có thể giúp con làm gì và bằng cách nào?" để làm nổi bật giá trị sản phẩm
→
bán giá trị sử dụng robot rõ ràng hơn tới cho phụ huynh
- **Tham gia cộng đồng phụ huynh trên fb**
## **L1 - Redesign luồng onboarding**
## **L2 - Các tính năng hỗ trợ học tiếng Anh / Parenting**
**Goal: **Đảm bảo người dùng được activate, thông qua 3 việc sau:
  - Dẫn dắt (Guide): Thay vì để người dùng tự bơi, cần dẫn dắt để họ biết họ có thể duy trì việc học của con như thế nào ngay sau khi kết nối.
  - Rút ngắn Time-to-Aha: Giúp phụ huynh khám phá các tình huống sử dụng (use cases) thực tế (Ví dụ: phụ huynh hẹn giờ để robot nhắc trẻ đi ngủ)
  - Hỗ trợ ra quyết định: Design các điểm chạm giúp phụ huynh nhận ra giá trị cốt lõi nhanh nhất.
### **Goal: **Khiến bố mẹ cảm thấy robot Pika đang giúp mình dạy con tiếng Anh nói riêng và dạy con nói chung
(image4)
## **P2 - Build hook model UX loop**
**Vòng lặp trải nghiệm khép kín cho bố mẹ, áp dụng cho tất cả tính năng

(1) Bố mẹ engage vào quá trình học (giao bài, tạo bài, tạo nhắc nhở,...)
(2) Bố mẹ nhìn thấy con sử dụng, nhìn thấy những phản hồi tương ứng trên robot
(3) Bố mẹ nhận được chứng minh giá trị của giải pháp ở 2 lv:
  - lv1: chứng minh tức thì (VD: Hôm nay Pika nhắc con đi ngủ, con đã chào Pika để đi ngủ luôn)
  - lv2: chứng minh qua thời gian dài - trajectory (VD: Trong một tháng vừa qua, con đã đi ngủ đúng giờ hơn)
## **L1 - Refactor home dashboard**
## **L1 - Cho phép bố mẹ treo thưởng cho các**
### **Goal: **Tối ưu trải nghiệm xem report của phụ huynh (tức thì) + Bổ sung các phần report theo tuần và tháng
**Goal: **Thêm cơ chế cho phép bố mẹ treo thưởng thực tế cho các thành tựu con đạt được cùng Pika
→ mở rộng các cơ chế gamification → impact lớn hơn tới con
## **L1 - Build hệ thống badge**
## **L1 - Tạo ra những engagement có ý nghĩa giữa bố mẹ và con**
**Goal: **Celebrate skills / character development milestones của con
→ có thêm hình thức instant gratification cho con
→ bố mẹ nhìn thấy sự phát triển về mặt skills, xây dựng đức tính tốt của con (vd: badge kiên nhẫn - đạt được khi cùng Pika đi hết 10 cuộc trò chuyện)
**Goal: **Nếu tôi check app thường xuyên thì tôi sẽ có những engagement thú vị với con dựa theo insight Pika cung cấp
→ vd: khi con học kiến thức mới thì bố mẹ challenge con
"""