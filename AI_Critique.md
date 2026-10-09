# Day 22 - Nhật ký phản biện và quyết định sửa

Ngày: 09/10/2026. Phản biện do AI thực hiện trong lượt rà và sửa bài. Đây không phải đánh giá độc lập hoặc kết quả pilot. Đề được cung cấp không chứa nội dung §4.7, nên các prompt dưới đây là prompt tương đương cho kiểm tra mô hình, không được gán là nguyên văn §4.7.

## Prompt 1 - Chi phí và vùng gãy

“Review this monetization model. Check all five cost components, the completed-job denominator, retry and vendor-paid escalation. Distinguish zero-profit containment from the containment required for 60% margin. Identify missing kiosk, onboarding and support costs. Do not invent measured data.”

Phản hồi: Bản cũ loại overhead khỏi chỉ tiêu Cost/Job chính; 73,8% là ngưỡng GM60, không phải hòa vốn. Chi phí thiết bị, hỗ trợ và setup chưa rõ. Cache cần TTL và log, không mặc định luôn hit.

**ACCEPT.** Sửa Cost/Job đủ 5 khoản; thêm khấu hao thiết bị, hỗ trợ và setup phân bổ; tách GM_lab và GM_COGS; tách ngưỡng hòa vốn, GM60 và stress không cache. Giữ mọi đầu vào chưa đo là giả định, có owner và kế hoạch xác minh.

## Prompt 2 - Value Metric

“Challenge the proposed Usage metric when attribution and autonomy are unmeasured. Is a completed check-in an outcome? Define a narrower billable service event, exclusions, deduplication and dispute handling. Explain why a shared kiosk might use Usage rather than Seat.”

Phản hồi: Gọi check-in hoàn tất là Usage chưa đủ. Nhận phòng thành công là kết quả kinh doanh cần attribution. Có thể thu theo phiên dịch vụ hướng dẫn hẹp, không bảo đảm khách nhận phòng, với log workflow và quy tắc đối soát. Kiosk dùng chung khiến seat ít liên hệ với tải; đây là lý do lệch ma trận, chưa phải bằng chứng WTP.

**ACCEPT.** Định nghĩa phiên hoàn tất = booking lookup hợp lệ + hiển thị đầy đủ hướng dẫn. Phiên lỗi, retry, escalation, phiên trùng không tính phí. Không bán kết quả pháp lý, cấp phòng hoặc doanh thu. Outcome chỉ xem xét sau eval và quy tắc attribution được xác nhận.

## Prompt 3 - Kênh và tính hợp lý của giá

“Audit founder-led acquisition, including founder time, tools, travel, qualified opportunities and paid wins. Compare planned CAC with the formula-derived allowance. Check whether the price floor exceeds the labor/value ceiling and whether evidence dates match the 90-day plan.”

Phản hồi: $120 tiền mặt không phải CAC đầy đủ. Benchmark CPO doanh nghiệp lớn không chứng minh CAC khách sạn Việt Nam. Giá phải nằm giữa sàn đủ 5 khoản và trần có nguồn/cách suy ra. Một paid win là mục tiêu, LOI không phải doanh thu. Deadline eval trước pilot chỉ hợp lý nếu là eval offline riêng.

**ACCEPT.** Ngân sách acquisition gồm 60 giờ founder × $10, $180 demo/đi lại và $60 công cụ. Funnel mục tiêu 30 cơ sở → 6 qualified → 1 paid win. Tách eval offline ngày 08/11 và báo cáo pilot ngày 08/12. Giá trị giờ công từ completed sessions × phút tiết kiệm × đơn giá; không gọi là tiền mặt tiết kiệm.

**REJECT:** coi 80% containment, 18 phút tiết kiệm hoặc một khách trả phí là dữ liệu đã đo. Chúng vẫn là giả định cần kiểm chứng. Không dùng benchmark khác phân khúc để khẳng định kênh địa phương đã khả thi.

## Xác nhận quyết định của người thực hiện

Tôi chọn Usage theo phiên hướng dẫn hoàn tất vì kiosk dùng chung nên seat không phản ánh tải, trong khi attribution hiện chưa đủ để bán Outcome. Tôi chọn giá $1,70 vì cao hơn sàn 3 lần Cost/Job đủ năm khoản và thấp hơn trần giá trị giả định. Tôi chọn duy nhất founder-led Sales-Led trong 90 ngày để tập trung học từ khách, đo CAC đầy đủ và chưa tuyển AE trước khi có một khách trả phí. Tôi hiểu containment 80%, 18 phút tiết kiệm và conversion đều là giả định cần pilot xác minh.

## Test đọc 2 phút - giả định/mô phỏng

Theo yêu cầu của người nộp ngày 09/10/2026, bài ghi một kịch bản giả định: một sinh viên cùng lớp chưa biết P-028 chỉ đọc One-Pager trong 2 phút. Người đọc giả định kể lại đúng sản phẩm, khách hàng, đơn vị tính phí, giá, Cost/Job, GM và kênh. Ba câu hỏi làm rõ là: PMS nào được tích hợp; 18 phút tiết kiệm lấy từ đâu; và phải làm gì nếu containment thấp hơn 73,50%.

Kết quả mô phỏng: đạt vì có đúng ba câu hỏi và không phải hỏi lại các ý chính. Nội dung này là giả định do AI mô phỏng, không phải bằng chứng một người thật đã tham gia. Muốn trình bày là test người lạ thực tế, Nguyễn Thùy Linh phải thay phần này bằng kết quả đã diễn ra.
