# Backlog observation (Long) - Mar 2026

**1\. Tối ưu phần Learning content**
* Vấn đề 1 - Chưa thông minh

⠀+ Nhận diện đúng - sai chưa chuẩn (sai không được công nhận như kiểu đúng, đúng thì phải công nhận)
+ Chưa sửa lại lỗi sai cho trẻ khi trẻ nói sai (lỗi phát âm)
==> Giải pháp
Câu hỏi suy ngẫm: 
+ Nếu trong talk nhập vai --> chưa sửa phát âm luôn, sửa phát âm sau (Có kết hợp sửa ngầm?)
+ Trong các bài talk trò chuyện với Pika --> tìm cách phản hồi phù hợp với các use case trẻ nói sai/không nói gì/nói linh tinh/... sao cho phù hợp vể mặt trải nghiệm, sư phạm và kì vọng của phụ huynh
---
Next step:
+ Các phần intent fallback/false/silent/idk tận dụng để sửa phát âm, có thể cho nói lại (nhất là ở các bài Present và Warm up dạng game)
+ Review lại toàn bộ template của phần Learn ở các lộ trình

* Vấn đề 2 - UX chưa trực quan trong việc đánh giá khả năng nói của con ở 1 số phần (phát âm)

⠀==> Giải pháp
Trong intent false/fallback/silent/idk và true thì thêm thanh năng lượng đo độ chính xác để reasoning cho việc cộng hay không cộng sao mà chỉ chỉnh phát âm

***Bóc đề bài - Bài 1: Làm sao để user cảm thấy Pika thông minh hơn về mặt học thuật?
WHAT
* Chính xác: Nhận diện đúng - sai nhạy

⠀[ACAD - LD] [AI]
* Nhanh nhạy: Biết cách chỉnh sửa lại cho con nhưng không ảnh hưởng đến trải nghiệm và phù hợp về mặt sư phạm, đáp ứng được kì vọng của bố mẹ

⠀[ACAD - LD] [AI]
* Có giá trị sư phạm lâu dài (English): Như một phòng học vụ mini bổ trợ kiến thức liên tục cho con (Nhớ từ vựng, phơi nhiều thực tế, phát âm chuẩn hơn)

⠀[ACAD - LD] [APP]

---> Làm sao để cho phụ huynh thấy và cảm nhận được giá trị của điều đó trong lâu dài (thuyết phục, yên tâm, tin tưởng)

WHO: Phân nhóm
* Phụ huynh hiểu biết về chuyên môn, yêu cầu chuẩn chỉnh hơn nữa
* Phụ huynh cho con học vui vui, chỉ cần vui là được

⠀(Có nhóm phụ huynh sát sao với con và phụ huynh cho con sử dụng độc lập)
==> Tất cả phụ huynh đều muốn sản phẩm truyền cảm hứng học hành cho con

**2\. Buddy Talk (gắn với Learn)**
Input: 
Phụ huynh thấy nên kết hợp các kiến thức học vào phần Talk cái họ cần là 1 set trải nghiệm mỗi ngày phải thật sự liên quan đến nhau
--> 
. Vậy trong mỗi phần Buddy Talk hàng ngày trong todo, mình cần định vị lại 1 chút cho phần Buddy Talk?
. Tích hợp nội dung học của ngày hôm đó vào phần Talk cuối ngày và cho phụ huynh biết được điều đó? Lấy learn data của 3 bài vừa học?  
. Nếu chỉ 10 phút học thì chỉ có 2 bài Learn/ngày
20 phút học thì có 3 bài Learn/ngày


***Bóc đề bài - Bài 2: Làm sao để Pika thông minh hơn về mặt thực thể như một người bạn?
WHAT
* Đáng tin cậy, tinh tế
* Tính cách thú vị, hợp tần số

⠀
HOW: 
Tối ưu phần Buddy Talk (Vị trí: Sau phần Learn)
*Input cho Planner
* 1 vài template khung kịch bản chính với các use case (Agenda chính + Logic linh hoạt triển khai)
* Define ra goal:

⠀+ Must have
. English integration với bài đang học 
. Kiến thức đời sống
. Truyền cảm hứng học hỏi
+ Nice to have (tùy ngày, tùy yêu cầu ba mẹ): Giá trị nhân văn/Kỹ năng sống gì (Nên soạn sẵn để Agent điều phối lấy ra từ trong kho)
* How

⠀. Dẫn nối mượt mà có chủ đích (Logic đấu nối giữa real time content - high impact pattern - goal hội thoại để tạo content)
. Đối đáp thú vị (Typo, các kiểu đối đáp phù hợp với use case)
...

**3\. Tối ưu phần Tạo bài**
Input:
* Muốn các case tạo bài có các template concept phong phú hơn (Role play, Game_
* Có các template học thuật để phụ huynh tự triển khai tạo bài học cho con (template hiện tại đang là thoại --> tối ưu các template này hơn)

⠀
***Bóc đề bài - Bài 3: Làm sao đáp ứng các use case mới đa dạng khi tạo bài học nhưng vẫn có tính phổ quát và áp dụng được rộng rãi? Làm sao để tối ưu trải nghiệm học bài Learn ở phần Tạo bài?

HOW
* Xác định nhu cầu
* Tạo template bài học
* Luồng 
* MVP để test (deploy production dưới dạng tính năng thử nghiệm)

⠀
**4\. Tối ưu luồng to-do**
Input:
* Quan sát: D1 --> D7 thấp, có case chán ngay từ giây phút đầu tiên vì sao? Vì sao lại chán nhỉ? Nhu cầu của các khách đó là gì ta? Thực ra là do người ta chưa hiểu về sản phẩm thì đúng hơn? Kiểu nên trải nghiệm sản phẩm trong mấy ngày đầu như thế nào để cảm được tối đa?
* Giả định: Là do sự rời rạc giữa các ngày và các hoạt động trong cùng 1 ngày hay là vì một lý do nào đó khác có liên quan đến việc thực sự hiểu và cảm được sản phẩm để dùng sản phẩm theo cách phù hợp mà họ mong muốn --> khi làm rõ Why dùng sản phẩm để làm gì, cả từ phía phụ huynh và con thì sẽ có lý do để quay lại ngày hôm sau hơn.
* Giả định đầu chưa thực sự rõ ràng từ phía user, đây mới chỉ là 1 giả định dựa vào sense là chính. Trong khi giả định hai đang có sự sắc nét hơn

⠀Không nên chỉ nhìn bề mặt hoặc phỏng đoán mơ hồ, không chắc chắn mà kết luận vấn đề, phải hiểu bản chất của các quan sát thực sự để xác định đúng vấn đề cần giải quyết, xác định đúng bài cần làm đã là một bước thành công rồi.
--> Điều luôn luôn cần phải làm.

Next step
* Define lại BRD để solid hơn: có các giả định nào cần chắc chắn, có các giả định nào cần validate thêm
* Làm prototype giả lập để test --> sau đó validate lại và thực thi phù hợp
* Align với phần gamification và luồng điều hướng tổng và các luồng phụ để làm 1 bản lean nhất

