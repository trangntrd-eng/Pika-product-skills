# Pika Robot User Journey - SSOT

---

## GIAI ĐOẠN 1: KHỞI ĐỘNG & THIẾT LẬP (Onboarding Phase)

**Mục tiêu:** Robot sẵn sàng cho tương tác, đã kết nối với hệ thống backend và người dùng. Người dùng hoàn thành các hoạt động trong ngày đầu tiên.

### I. PHỤ HUYNH MỞ HỘP → THIẾT LẬP BAN ĐẦU

#### Bước 1.1: Khởi Động Robot Lần Đầu

- **Người dùng (Phụ huynh/Trẻ):** Cắm nguồn và nhấn nút NGUỒN 1 lần.
- **Robot:** Robot khởi động, phát âm thanh, chạy servo và mood tương ứng với trạng thái khởi động.
- **Robot:** Robot phát âm thanh điều hướng phụ huynh tải app Robot Pika

#### Bước 1.2: Tải & Tạo Tài Khoản App Robot Pika

- **Người dùng (Phụ huynh):** Scan QR trong HDSD hoặc tìm trên cửa hàng ứng dụng
- **Người dùng (Phụ huynh):** Tải app Robot Pika
- **Người dùng (Phụ huynh):** Đăng ký tài khoản Robot Pika

#### Bước 1.3: Thiết Lập Profile & Hướng Dẫn Kết Nối

- **Người dùng (Phụ huynh):** Nhập tên con
- **Người dùng (Phụ huynh):** Chọn đã có robot hay chưa
- **Người dùng (Phụ huynh):** Chọn trình độ tương ứng với lộ trình → chế độ ngôn ngữ mong muốn
- **App:** Hướng dẫn người dùng kiểm tra robot đã bật hay chưa
- **Người dùng (Phụ huynh):** Xác nhận robot đã bật nguồn thành công

#### Bước 1.4: Kết Nối Bluetooth (BT Pairing)

- **App:** Kiểm tra nếu thiết bị của user đã bật bluetooth.
- **App:** Kiểm tra nếu thiết bị của user đã bật trạng thái Dịch vụ Vị trí (Location Services).
- **Người dùng (Phụ huynh):** Thao tác bật Bluetooth và Location Service nếu cần. Quay lại app để tiếp tục Kết nối Bluetooth.
- **App:** Tự động chuyển qua bước quét robot
- **App:** Hiển thị danh sách robot đã quét được
- **Người dùng (Phụ huynh):** Chọn robot tương ứng cần kết nối Bluetooth
- **App:** Thông báo kết nối Bluetooth thành công
- **Robot:** Thông báo kết nối Bluetooth thành công

#### Bước 1.5: Kết Nối & Xác Thực Mạng (WiFi Setup)

- **App:** Hiển thị màn kết nối Wifi. Tự động kết nối với Wifi mà điện thoại đang kết nối
- **Người dùng (Phụ huynh):** Chọn Wifi từ danh sách Drop-down
- **Người dùng (Phụ huynh):** Nhập mật khẩu Wifi
- **App:** Thông báo kết nối Wifi thành công
- **Robot:** Thông báo kết nối Wifi thành công

#### Bước 1.6: Cấu Hình Profile Chi Tiết

- **App:** Mời phụ huynh thiết lập profile chi tiết
- **Người dùng (Phụ huynh):** Bắt đầu thiết lập profile
- **Người dùng (Phụ huynh):** Nhập ngày sinh nhật → giới tính → tỉnh thành → thông tin về sở thích của trẻ
- **Hệ thống:** Lưu các dữ liệu của trẻ vào bộ nhớ tĩnh

---

## GIAI ĐOẠN 2: TRẺ TƯƠNG TÁC HÀNG NGÀY (Daily Interaction Loop)

> **Lưu ý:** Các bước trong giai đoạn này có thể bị ngắt bởi **Hệ Thống 7: MQTT Handler**, hệ thống có độ ưu tiên cao nhất và sẽ tạm dừng các trạng thái khác để xử lý các lệnh đến (với một số ngoại lệ được quy định).

**Mục tiêu:** Robot tải To-Do List, thức dậy, thực thi các hoạt động theo từng loại (Workflow, Agent), xử lý In-Session Routing cho Agent activities, và đồng bộ dữ liệu.

### Bước 2.1: Đánh Thức Robot

- **Người dùng (Trẻ/Phụ huynh):** Gọi "Hey, Pika" hoặc ấn nút NGUỒN / HOME
- **Robot:** Nhận diện Wakeword hoặc thao tác của người dùng từ trạng thái ngủ
- **Robot:** Phát audio + biểu cảm + servo mô phỏng trạng thái thức dậy

### Bước 2.2: Kiểm Tra Trạng thái Ghép nối

- **Robot:** Kiểm tra trạng thái kết nối wifi. Phát audio + gif để user hiểu trạng thái đang kết nối mạng
- **Robot:** Thông báo kết nối thành công
- **Hệ thống:** Kiểm tra trạng thái ghép nối của robot với user profile

### Bước 2.3: Tải Danh Sách Hoạt Động Trong Ngày

- **Hệ thống:** Tải danh sách các hoạt động đề xuất trong ngày (To-do-List)
  - Số lượng và thứ tự các hoạt động: dựa trên giai đoạn tình bạn (Context Handling)
  - Độ khó của hoạt động học: dựa theo lộ trình
- **Hệ thống:** Đưa các thông tin trong cấu hình profile và các thông tin liên quan từ bộ nhớ tĩnh / động vào trong các hoạt động Agent (Prompt Generator)
- **Hệ thống:** Xác định phiên sử dụng của user trong ngày.
  - **Phiên đầu tiên trong ngày:** Hoạt động đầu tiên là chào hỏi (Greeting)
  - **Phiên tiếp theo:** Hoạt động đầu tiên là hoạt động tiếp theo chưa hoàn thành trong To-Do List (Học / Trò chuyện / Chơi game)
  - **Nếu To-Do List trống:** Chuyển sang hoạt động Trò chuyện chung (General Talk)

### Bước 2.4: Chu Trình Tương Tác Theo Các Dạng Hoạt Động

#### A. DẠNG WORKFLOW (Thường sử dụng cho các hoạt động học có cấu trúc)

- **Hệ thống:** Nhận tín hiệu bắt đầu hội thoại và yêu cầu kết nối socket tới server BE
- **Hệ thống:** Tải trước một số tài nguyên cần thiết để bắt đầu hoạt động đầu tiên
- **Robot:** Hiển thị màn loading (nếu cần tải tài nguyên)

**Vòng lặp lặp lại cho tới khi hội thoại kết thúc:**

1. **Robot:** Nói/hỏi trẻ, câu hỏi có thể được cấu hình chi tiết về hình ảnh/biểu cảm/servo/âm thanh
2. **Người dùng (Trẻ):** Trả lời bằng âm thanh hoặc bấm nút (nếu hoạt động yêu cầu)
3. **Robot:** Thể hiện trạng thái nghe (mặt nghe/hình ảnh trẻ cần nhìn để trả lời + đèn nghe)
4. **Hệ thống:** Tải dần các tài nguyên tiếp theo cho hoạt động + Record và stream audio về BE → BE gửi lên server STT
5. **Người dùng (Trẻ):** Trả lời xong
6. **Hệ thống:** Nhận diện user trả lời xong → Hệ thống ngưng thu âm
7. **Robot:** Thể hiện trạng thái suy nghĩ (mặt suy nghĩ + đèn suy nghĩ)
8. **Hệ thống:** Đánh giá ý định (intent) của người dùng + Lựa chọn câu trả lời chính phù hợp (đã được cấu hình chi tiết về hình ảnh/biểu cảm/servo/âm thanh) + Lựa chọn câu trả lời đệm phù hợp (fast response)
9. **Robot:** Phát câu trả lời đệm → câu trả lời chính
10. **Hệ thống:** Đánh giá nếu cuộc hội thoại đã kết thúc → Ngắt socket + Lưu lịch sử hội thoại

#### B. DẠNG AGENT (Thường sử dụng cho các hoạt động với kịch bản trả lời không cố định)

- **Hệ thống:** Nhận tín hiệu bắt đầu hội thoại và yêu cầu kết nối socket tới server BE
- **Hệ thống:** Tải trước một số tài nguyên cần thiết để bắt đầu hoạt động đầu tiên
- **Robot:** Hiển thị màn loading (nếu cần tải tài nguyên)

**Vòng lặp lặp lại cho tới khi hội thoại kết thúc:**

1. **Robot:** Nói/hỏi trẻ. Trong một lượt nói của robot có thể thay đổi biểu cảm nhiều lần. Nếu có hình ảnh cần phát sẽ ưu tiên phát hình ảnh.
2. **Hệ thống:** Trả biểu cảm và audio cho từng khúc trong toàn bộ câu trả lời.
3. **Người dùng (Trẻ):** Trả lời bằng voice
4. **Robot:** Thể hiện trạng thái nghe (mặt nghe/hình ảnh trẻ cần nhìn để trả lời + đèn nghe)
5. **Người dùng (Trẻ):** Trả lời xong
6. **Robot:** Thể hiện trạng thái suy nghĩ (mặt suy nghĩ + đèn suy nghĩ)
7. **Hệ thống:** LLM dựa vào system prompt để trả ra câu trả lời chính phù hợp → Lựa chọn câu trả lời đệm phù hợp (fast response) → Đánh giá nếu cuộc hội thoại đã kết thúc
8. **Robot:** Phát câu trả lời đệm → câu trả lời chính
9. **Hệ thống:** Đánh giá nếu cuộc hội thoại đã kết thúc → Ngắt socket + Lưu lịch sử hội thoại

### Bước 2.5: Điều Hướng Ngay Trong Phiên (Chỉ Cho Các Hoạt Động Dạng Agent)

- **Người dùng (Trẻ):** Trả lời bằng voice
- **Hệ thống:** Liên tục theo dõi câu trả lời của trẻ & phân loại yêu cầu tức thời thành các nhóm cụ thể:
  - **Game Request** ("Chơi trò chơi", "Chơi game nào đó")
  - **Song Request** ("Hát bài gì", "Nghe bài hát")
  - **Backstory Inquiry** ("Pika từ đâu?", "Pika thích gì?")
  - **Off-Topic Question** ("Hôm nay thời tiết như thế nào?", "Mình có thể làm gì?")
  - **Emotional Expression** ("Tớ buồn", "Tớ vui quá", "Tớ sợ")
- **Hệ thống:** Dựa trên ý định được nhận diện, hệ thống đi tới hoạt động chuyên biệt tương ứng:
  - Game Request → **Game Agent**
  - Song Request → **Story/Music Agent**
  - Backstory Inquiry → **Backstory Agent**
  - Off-Topic Question → **AMA Agent** (Ask Me Anything)
  - Emotional Expression → **Emotion Agent**
- **Robot:** Phát câu trả lời đệm → câu trả lời chính tương ứng với hoạt động chuyên biệt
- **Hệ thống:** Đánh giá nếu cuộc hội thoại đã kết thúc → Quay trở lại cuộc hội thoại trước đó

### Bước 2.6: Điều Hướng Cuối Phiên

- **Hệ thống:** Kiểm tra To-Do List để xác định hoạt động tiếp theo
  - **Nếu còn hoạt động chưa hoàn thành trong To-Do List (trừ hoạt động Kết thúc):** Robot bắt đầu hoạt động tiếp theo
  - **Nếu chỉ còn hoạt động Kết thúc:** Robot chủ động rủ user kết thúc → Robot về trạng thái ngủ
  - **Nếu tất cả hoạt động đã hoàn thành:** Robot chuyển sang chế độ trò chuyện tự do (GENERAL_TALK mode)

### Bước 2.7: Điều Hướng Bằng Các Nút Chức Năng

#### NÚT NGUỒN

**Cho robot đi ngủ:**
- **Người dùng (Trẻ):** Nhấn 1 lần
- **Hệ thống:** Kết thúc tất cả hoạt động, chuyển sang trạng thái ngủ
- **Robot:** Phát âm thanh đi ngủ.

**Tắt nguồn robot:**
- **Người dùng (Trẻ):** Giữ nguồn
- **Hệ thống:** Tắt nguồn.

#### NÚT HOME

**Thoát ra khỏi hoạt động hiện tại:**
- **Người dùng (Trẻ):** Ấn nút Home 1 lần
- **Robot:** Hỏi trẻ nếu muốn chọn hoạt động khác thì ấn nút Home lần nữa

**Về màn Menu:**
- **Người dùng (Trẻ):** Ấn lần tiếp theo
- **Robot:** Ngắt hoạt động hiện tại, đưa robot về màn hình Menu.

#### MÀN MENU

**Điều hướng:**
- **Người dùng (Trẻ):** Ấn button phải, trái để chuyển giữa các mục
- **Người dùng (Trẻ):** Ấn button giữa để chọn vào mục

**Chế độ Learn:**
- **Người dùng (Trẻ):** Lựa chọn chế độ Learn
- **Hệ thống:** Lấy bài học tiếp theo từ lộ trình
- **Robot:** Phát bài học tiếp theo

**Chế độ Talk:**
- **Người dùng (Trẻ):** Lựa chọn chế độ Talk
- **Hệ thống:** Vào hoạt động General Talk
- **Robot:** Phát hoạt động General Talk

**Settings Menu:**

*Cài đặt âm thanh/độ sáng:*
- **Người dùng (Trẻ):** Lựa chọn một trong các cài đặt âm thanh/độ sáng
- **Người dùng (Trẻ):** Ấn nút phải/trái để tăng/giảm âm thanh/độ sáng

*Cài đặt Reset:*
- **Người dùng (Trẻ):** Lựa chọn Reset Wifi
- **Robot:** Hiện màn hình xác nhận
- **Người dùng (Trẻ):** Xác nhận
- **Hệ thống:** Reset wifi

- **Người dùng (Trẻ):** Lựa chọn Factory Reset
- **Robot:** Hiện màn hình xác nhận
- **Người dùng (Trẻ):** Xác nhận
- **Hệ thống:** Factory Reset

*Xem thông tin Robot:*
- **Robot:** Hiện thông số robot (robot_id, Wifi)
- **Người dùng (Trẻ):** Xác nhận

### Bước 2.8: Điều Hướng Bằng App Phụ Huynh

#### Giao bài học

- **Người dùng (Phụ huynh):** Chọn bài học trên lộ trình → Ấn giao bài học
- **Hệ thống:** Nhận diện yêu cầu → Ngưng hoạt động hiện tại → Khởi tạo bài học phụ huynh giao
- **App:** Xác nhận bài học được giao thành công
- **Robot:** Phát âm thanh báo hiệu có bài học được giao
- **Robot:** Hiển thị màn loading (nếu cần tải tài nguyên) → Bắt đầu học

#### Đặt báo thức

- **Người dùng (Phụ huynh):** Đặt báo thức (thời gian, tên hoạt động, ngày báo thức)
- **Hệ thống:** Lưu yêu cầu theo robot_id
- **Hệ thống:** Nhận diện tới giờ báo thức, đẩy trigger báo thức xuống robot
- **Robot:** Nếu robot đã kết nối thành công và không ở trạng thái tắt nguồn → Phát báo thức → Bảo trẻ bấm nút để tắt báo thức
- **Người dùng (Trẻ):** Bấm nút tắt báo thức
- **Hệ thống:** Nhận diện báo thức đã gửi thành công
- **Hệ thống:** Khởi tạo hoạt động tiếp theo trong danh sách To-do List
- **Robot:** Bắt đầu phát hoạt động

#### Chuyển đổi ngôn ngữ/lộ trình

- **Người dùng (Phụ huynh):** Chọn ngôn ngữ hoặc lộ trình mới trên app
- **App:** Gửi yêu cầu thay đổi đến hệ thống
- **Hệ thống:** Nhận yêu cầu, cập nhật profile của trẻ trong bộ nhớ tĩnh
- **Hệ thống:** Gửi tín hiệu (trigger) xuống robot qua MQTT để thông báo có sự thay đổi
- **App:** Xác nhận thay đổi thành công trên giao diện của phụ huynh + thời gian delay để áp dụng thay đổi.
- **Robot:** Nhận tín hiệu, có thể có các hành vi sau tùy thuộc vào trạng thái hiện tại:
  - **Nếu đang ở trạng thái ngủ:** Robot không có hành động ngay lập tức. Thay đổi sẽ được áp dụng trong phiên tương tác tiếp theo khi robot thức dậy và tải To-Do List mới.
  - **Nếu đang trong một hoạt động:** Robot tải lại To-Do List mới + hoàn thành nốt hoạt động hiện tại (nếu có), sau đó thông báo cho trẻ về sự thay đổi và bắt đầu vào phiên tiếp theo tương ứng thiết lập ngôn ngữ / lộ trình mới.

---

## TÍNH NĂNG PHỤ

- Cập nhật Firmware
- Cập nhật thẻ SSD

---

## CÁC HỆ THỐNG CHẠY SONG SONG

### HỆ THỐNG 1: XỬ LÝ LỖI & CHẾ ĐỘ OFFLINE (Error Handling & Offline Mode)

**Mục tiêu:** Đảm bảo robot vẫn có thể cung cấp trải nghiệm tương tác cơ bản (kể chuyện, hát) khi gặp sự cố kết nối nghiêm trọng, giúp duy trì sự tương tác và giảm thiểu sự gián đoạn cho trẻ.

#### Bước 1: Phát Hiện Lỗi & Kích Hoạt Chế Độ Offline

- **Hệ thống (BE/AI):** Gặp lỗi nghiêm trọng trong quá trình tương tác online (ví dụ: timeout > 10s, mất kết nối socket, lỗi LLM).
- **Hệ thống (BE):** Gửi lệnh cho robot chuyển sang chế độ offline.
- **Robot:** Ngừng hoạt động online hiện tại, phát âm thanh và biểu cảm thông báo có sự cố nhỏ và chuyển sang hoạt động offline (ví dụ: "Ôi, hình như có chút trục trặc rồi. Để tớ kể cậu nghe chuyện này nhé!").

#### Bước 2: Thực Thi Hoạt Động Offline

- **Robot:** Tải và bắt đầu một hoạt động offline đã được lưu sẵn trong bộ nhớ (truyện kể hoặc bài hát).
- **Robot:** Phát nội dung đa phương tiện (âm thanh, hình ảnh, servo) theo kịch bản của hoạt động offline.
- **Người dùng (Trẻ):** Có thể tương tác cơ bản bằng các nút bấm:
  - Nhấn nút HOME 1 lần: Tạm dừng hoạt động.
  - Nhấn nút HOME 2 lần: Thoát về màn hình Menu chính.
  - Nhấn nút NGUỒN 1 lần: Chuyển robot về trạng thái ngủ.

#### Bước 3: Kết Thúc Hoạt Động & Khôi Phục Kết Nối

- **Hệ thống:** Hoạt động offline kết thúc (hoàn thành hoặc do người dùng ngắt).
- **Robot:** Tự động thử kết nối lại với BE (thử 3 lần, mỗi lần cách nhau 5 giây), hiển thị biểu cảm chờ đợi.

**Nếu kết nối thành công:**
- **Robot:** Phát âm thanh vui vẻ ("A, mạng đã trở lại rồi! Mình tiếp tục nhé!").
- **Hệ thống:** Đồng bộ lịch sử hoạt động offline lên BE. BE trả về hoạt động tiếp theo trong To-Do List.

**Nếu kết nối thất bại:**
- **Robot:** Thông báo mạng chưa ổn định và tự khởi chạy một hoạt động offline khác.
- **Robot:** Nếu hết hoạt động offline, chuyển sang chế độ trò chuyện chung (General Talk) với các chủ đề cơ bản đã lưu sẵn.
