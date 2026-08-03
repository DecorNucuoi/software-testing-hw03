# Context Brief — Thiết kế GUI Checklist cho hệ thống EMS

> Tài liệu này là **input đầy đủ và duy nhất** để tạo checklist GUI. Bạn không cần thông tin nào khác ngoài file này.

---

## 1. Nhiệm vụ

Sinh **đúng 14 mục checklist kiểm thử GUI**, phủ trải đều cả bốn *interface aspect* (IA-01 → IA-04) mô tả ở §4.

**Bối cảnh:** 14 mục này là phần đóng góp của một thành viên vào checklist chung của cả nhóm. Các thành viên khác cũng đóng góp phần của mình, sau đó gộp lại và khử trùng lặp thành checklist tổng hơn 40 mục. Vì vậy:

- 14 mục phải **trải rộng cả bốn IA**, không dồn vào một IA nào
- Ưu tiên các mục **có giá trị cao, bao quát**, áp dụng được cho nhiều loại màn hình — vì đây là phần tinh tuý đóng góp vào bộ chung
- Tránh mục quá vụn vặt hoặc quá hẹp, vì khi gộp sẽ bị loại

Checklist sau đó được áp dụng lặp lại lên nhiều màn hình khác nhau của EMS, mỗi mục đánh dấu **Passed / Failed / N/A** theo từng màn hình.

---

## 2. Ràng buộc quan trọng nhất

### 2.1. Viết TIÊU CHÍ, không viết PHÁT HIỆN

Đây là lỗi phổ biến nhất. Mỗi mục phải là một **câu hỏi kiểm tra được**, áp dụng được lên bất kỳ màn hình nào — KHÔNG phải kết luận về một màn hình cụ thể.

| ❌ Sai (là finding) | ✅ Đúng (là tiêu chí) |
| --- | --- |
| "Sửa lỗi id trùng ở ô chọn ngày" | "Mỗi input có `id` duy nhất và được liên kết với `<label for>`" |
| "Nút Publish nằm sai vị trí" | "Nhóm nút hành động chính/phụ đặt nhất quán ở cùng vị trí trên mọi form" |
| "Trang thiếu bản dịch tiếng Việt" | "Toàn bộ nhãn, thông báo lỗi và trạng thái đều được dịch khi đổi ngôn ngữ EN ↔ VI" |

### 2.2. Phải TỔNG QUÁT cho toàn hệ thống

Checklist dùng chung cho **cả bốn nhóm chức năng** ở §3. Không được viết bám vào một màn hình hay một nhóm cụ thể. Nếu một mục chỉ đúng cho đúng một màn hình duy nhất thì mục đó viết chưa đủ tổng quát.

### 2.3. Phải KIỂM CHỨNG ĐƯỢC

Mỗi mục phải trả lời được Pass hay Fail chỉ bằng cách nhìn/thao tác trên màn hình. Tránh mục mơ hồ kiểu "giao diện đẹp", "trải nghiệm tốt", "dễ dùng".

---

## 3. Hệ thống được kiểm thử (SUT)

**EMS — Event Management System**, ứng dụng web quản lý sự kiện học thuật của một khoa đại học. Gồm khu vực quản trị (admin) và khu vực công khai cho người dùng.

Bốn nhóm chức năng mà checklist phải phục vụ được:

| Nhóm | Phạm vi |
| --- | --- |
| **A — Quản trị sự kiện** | Dashboard KPI; danh sách Events có bộ lọc trạng thái; form Add/Edit Event (upload thumbnail 4:3 + banner 24:9, rich-text, validation ngày giờ); cấu hình đăng ký (công tắc student/lecturer/guest, waitlist, vai trò phụ); Draft / Publish / Preview / Delete; duyệt Participants & Reviews; Check-in |
| **B — Trải nghiệm người tham gia** | Trang chủ công khai có carousel sự kiện nổi bật; duyệt theo category, search/filter; trang chi tiết sự kiện; form đăng ký (chọn role, waitlist); My Registrations và vé barcode/QR; đánh giá sao 1–5 sau sự kiện |
| **C — Quản trị người dùng** | Danh sách Users (avatar + tên, role, member code, trạng thái active, audit); Assign Role; Block / Unblock; Reset Password; Export ra Excel; audit log |
| **D — Yêu cầu hỗ trợ** | Người dùng: tạo support request (category, nội dung, đính kèm ảnh), My Requests và chi tiết kèm phản hồi. Admin: danh sách Support Requests (tab Pending/Resolved, tìm theo member code hoặc category), chi tiết request có lightbox ảnh, internal note, phản hồi chính thức |

### 3.1. Inventory thành phần giao diện có trong EMS

Checklist cần phủ được các loại widget sau (đây là danh sách thật, đã khảo sát):

**Hiển thị dữ liệu:** bảng danh sách · phân trang · search box · bộ lọc theo trạng thái/role/category · thẻ card · carousel · KPI card · progress bar · badge trạng thái · barcode/QR · lightbox ảnh · audit log

**Nhập liệu:** form nhiều section · text input · textarea · number input · dropdown đơn chọn · dropdown đa chọn · checkbox · toggle switch · radio · date-time picker · rich-text editor (có thanh công cụ định dạng, chọn cỡ chữ) · upload ảnh theo tỉ lệ cố định (4:3 và 24:9) · upload file đính kèm · thang đánh giá sao 1–5

**Điều hướng:** sidebar · menu · tab · breadcrumb · nút back/return · deep link tới chi tiết

**Phản hồi:** toast · dialog xác nhận · thông báo lỗi cạnh trường · empty state · loading state · chấm thông báo (notification dot) · cập nhật real-time

**Hành động khác:** Export ra Excel · Preview · lưu nháp / phát hành

### 3.2. Đặc thù cần lưu ý của EMS

- **Song ngữ EN/VI**, có nút chuyển ngôn ngữ trên thanh điều hướng
- **Bốn nhóm quyền**: admin, sinh viên, giảng viên, khách — giao diện thay đổi theo quyền
- **Nhiều trường ngày giờ phụ thuộc lẫn nhau** trong cùng một form (thời gian bắt đầu/kết thúc sự kiện, mở/đóng check-in, mở/đóng đăng ký) — ràng buộc chéo giữa các trường
- **Trạng thái vòng đời**: Draft → Published, cùng các trạng thái đăng ký Registered / Pending / Confirmed / Approved / Waitlisted
- **Giới hạn sức chứa** theo từng vai trò, hiển thị dạng `đã đăng ký / tối đa`
- Ứng dụng chạy qua tunnel, dữ liệu có thể bị reset — trạng thái rỗng xuất hiện thường xuyên

---

## 4. Bốn Interface Aspect — chiều phủ bắt buộc

14 mục phải trải đều cả bốn nhóm dưới đây — đề nghị phân bổ **4 / 4 / 3 / 3**, và **không nhóm nào dưới 3 mục**.

| Mã | Tên | Phạm vi |
| --- | --- | --- |
| **IA-01** | **Chuẩn UI chung** | Layout, canh lề, typography, màu sắc, tính nhất quán, quốc tế hoá EN/VI, trạng thái empty / loading |
| **IA-02** | **Forms** | Nhãn trường, validation, vị trí hiển thị lỗi, xử lý trường bắt buộc, upload file/ảnh, rich-text editor |
| **IA-03** | **Navigation** | Menu, breadcrumb, tab, sidebar, kéo-thả sắp xếp, nút back/return, deep link |
| **IA-04** | **Feedback / State** | Toast, badge, dialog xác nhận, progress bar, màu sắc thể hiện trạng thái, cập nhật real-time |

---

## 5. Nền tảng lý thuyết bắt buộc

Checklist phải bắt nguồn từ các khung nguyên tắc được công nhận, và **mỗi mục phải ghi rõ nguồn gốc**:

- **Nielsen — 10 Usability Heuristics for User Interface Design**
- **Norman — 6 nguyên tắc thiết kế** (*The Design of Everyday Things*): visibility, feedback, constraints, mapping, consistency, affordance
- **Shneiderman — 8 Golden Rules of Interface Design**
- **ISTQB Foundation Level Syllabus** — thuật ngữ và khái niệm kiểm thử
- **WCAG 2.1** — cho các mục về khả năng tiếp cận

---

## 6. Định dạng đầu ra

Trả về một bảng Markdown với đúng các cột sau:

| ID | IA | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- | --- |

- **ID**: đánh số theo nhóm — `GUI-01-001`, `GUI-02-001`, …
- **Mục kiểm tra**: một câu khẳng định, có thể trả lời Pass/Fail
- **Cách kiểm chứng**: thao tác cụ thể để xác định Pass hay Fail
- **Nguồn**: ví dụ `Nielsen #4`, `Norman – Consistency`, `Shneiderman #2`, `WCAG 1.4.3`
- **Ưu tiên**: Cao / Trung bình / Thấp

### Ví dụ mẫu (bám đúng format này)

| ID | IA | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- | --- |
| GUI-01-001 | IA-01 | Tiêu đề trang khớp với mục đang được chọn trên menu điều hướng | Mở lần lượt từng mục menu, so tiêu đề trang với nhãn menu | Nielsen #1 | Cao |
| GUI-02-001 | IA-02 | Mọi trường bắt buộc được đánh dấu nhất quán bằng một quy ước duy nhất và quy ước đó được giải thích | Rà toàn bộ trường trên form, đối chiếu ký hiệu dùng cho trường bắt buộc | Nielsen #4 | Cao |
| GUI-04-001 | IA-04 | Mọi hành động phá huỷ dữ liệu đều có dialog xác nhận nêu rõ đối tượng bị tác động | Bấm xoá/chặn/reset, đọc nội dung dialog xem có nêu tên đối tượng cụ thể | Shneiderman #6 | Cao |

---

## 7. Quy trình đề nghị — chạy làm ba lượt riêng biệt

Không gộp thành một prompt duy nhất. Ba lượt tách rời cho kết quả tốt hơn và cho phép theo dõi được lượt đầu còn thiếu gì. **Sau cả ba lượt, tổng vẫn phải là 14 mục** — lượt 2 và lượt 3 là thay thế và tinh chỉnh, không phải cộng dồn.

**Lượt 1 — Sinh theo khung lý thuyết.**
Duyệt lần lượt Nielsen 10 heuristic, Norman 6 nguyên tắc, Shneiderman 8 quy tắc. Chọn ra 14 mục kiểm chứng được, giá trị cao nhất, trải đều IA-01…IA-04.

**Lượt 2 — Đối chiếu inventory widget.**
Rà lại danh sách widget ở §3.1, xem 14 mục hiện tại bỏ sót loại widget quan trọng nào. Nếu có, **thay thế** mục yếu nhất bằng mục phủ widget đó — giữ nguyên tổng 14.

**Lượt 3 — Phản biện tìm lỗ hổng.**
Tự đặt câu hỏi: 14 mục hiện tại còn thiếu gì về các nhóm dưới đây?

- Khả năng tiếp cận (accessibility): nhãn cho trợ năng, thứ tự tiêu đề, độ tương phản màu
- Điều hướng bằng bàn phím: thứ tự tab, vòng focus trong dialog, phím Esc, viền focus nhìn thấy được
- Quốc tế hoá EN/VI: dịch sót, định dạng ngày giờ, tràn chữ khi dịch dài hơn, thuộc tính `lang`
- Responsive: bảng trên màn hình hẹp, vùng chạm đủ lớn, dialog trên điện thoại
- Dark mode và bố cục phải-sang-trái (RTL)
- Xử lý lỗi hệ thống: mất mạng, hết phiên đăng nhập, tải thất bại
- Trạng thái rỗng và trạng thái đang tải

Nếu phát hiện lỗ hổng, **thay thế** mục yếu nhất chứ không thêm mục mới — tổng vẫn là 14.

---

## 8. Kiểm tra trước khi kết thúc

- [ ] Tổng số mục **đúng 14**
- [ ] Cả bốn IA đều có mặt, **không IA nào dưới 3 mục**
- [ ] Không mục nào là *finding* — tất cả đều là *tiêu chí*
- [ ] Không mục nào chỉ áp dụng được cho đúng một màn hình
- [ ] Mỗi mục có nguồn tham khảo cụ thể
- [ ] Mỗi mục có cách kiểm chứng rõ ràng, trả lời được Pass/Fail
- [ ] Các mục đủ bao quát để có giá trị khi gộp vào checklist chung của nhóm
