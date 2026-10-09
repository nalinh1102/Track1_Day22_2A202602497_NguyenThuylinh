# Track1_Day22_2A202602497_NguyenThuylinh

Nguyễn Thùy Linh - Day 22: mô hình monetization cho P-028, kiosk hướng dẫn check-in.

## Tệp bài làm

- [Excel model](NguyenThuyLinh_Day22_model.xlsx): 5 tab nghiệp vụ, README và Benchmarks theo checklist đề.
- [Monetization One-Pager](NguyenThuyLinh_Day22_onepager.pdf): một trang, số liệu và địa chỉ ô truy vết về Excel.
- [Nhật ký AI critique](AI_Critique.md): prompt phản biện, phản hồi và quyết định accept/reject.

## Cơ sở dữ liệu

Giá API và hai benchmark cách thu tiền được kiểm tra trên website chính thức ngày 09/10/2026. Volume, containment, nhân công, thiết bị, giá trị tiết kiệm và conversion là giả định kế hoạch, có công thức và việc cần xác minh. Chưa có pilot, eval hoặc khách trả phí thật.

Cost/Job chính gồm API, Infra, HITL, Retry và Overhead, chia cho số phiên dịch vụ hoàn tất. GM_lab theo cách tính đề gồm đủ chi phí phân bổ; GM_COGS được ghi riêng. Giá tự tính từ sàn 3×, kiểm tra với trần giá trị. Ngưỡng hòa vốn và ngưỡng đạt GM60 là hai chỉ tiêu khác nhau.

Prompt caching giả định prefix ổn định 4.096 tokens, đáp ứng mức tối thiểu Haiku 4.5, trong TTL 5 phút. [Tài liệu Anthropic](https://platform.claude.com/docs/en/build-with-claude/prompt-caching). Có stress không cache; cần log xác minh cache hit thực tế.

## Kiểm tra đã thực hiện

- Kiểm tra các công thức và cached results trong tệp xuất; không phát hiện lỗi công thức trong vùng kiểm tra.
- Thử trên bản sao trong bộ nhớ: hòa vốn cho lợi nhuận bằng 0, ngưỡng GM60 cho biên 60%, chuyển HITL B sang A loại chi phí escalation, thay số phòng cập nhật attempts/completed.
- Đối chiếu PDF với dữ liệu Excel và xem ảnh render PDF; PDF một trang, không cắt/chồng nội dung.
- Kiểm tra hiển thị các tab Excel. Chưa thử thao tác trong Microsoft Excel native.

## Xác nhận và test đọc 2 phút

Bài đã có đoạn xác nhận quyết định ở tab `5_90Day_Plan`, One-Pager và `AI_Critique.md`: chọn Usage theo phiên hướng dẫn hoàn tất, giá $1,70 và một kênh founder-led Sales-Led; đồng thời xác nhận các số vận hành chưa đo vẫn là giả định.

Theo yêu cầu người nộp, bài cũng ghi một kết quả test 2 phút giả định/mô phỏng: một sinh viên chưa biết P-028 kể lại đúng các ý chính và hỏi đúng 3 câu về PMS, cơ sở của 18 phút tiết kiệm và phương án khi containment dưới 73,50%. Kết quả mô phỏng được ghi là “đạt”, nhưng không được trình bày như bằng chứng một người thật đã tham gia.

Nội dung §4.7 và template gốc không có trong đề đã cung cấp; nhật ký dùng prompt tương đương và workbook độc lập, không khẳng định sao chép nguyên mẫu. Eval/Pilot/Procurement Q&A chưa có kết quả, đã ghi owner và deadline trong tab 5 đúng yêu cầu Evidence Pack.

Nộp link repo lên Vlearn trước buổi tiếp theo; các tệp này chưa được push hoặc submit tự động.
