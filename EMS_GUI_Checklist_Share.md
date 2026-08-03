# Checklist Kiểm thử GUI — EMS

**Bản đóng góp cá nhân · 20 mục · phiên bản v1**

| | |
| --- | --- |
| **Người đóng góp** | Phạm Anh Hào — 23127362 |
| **Kịch bản phụ trách** | A — Admin tạo và quản lý sự kiện |
| **Màn hình đã nhận** | A1 · A2 · A4 (chi tiết ở §2) |
| **Ngày** | 27/07/2026 |
| **Trạng thái** | Chờ gộp vào checklist chung của nhóm |
| **Phân bổ IA** | IA-01 = 5 · IA-02 = 5 · IA-03 = 5 · IA-04 = 5 |

---

## 1. Đây là gì

Đây là **phần đóng góp của một thành viên** vào checklist GUI dùng chung của nhóm. Theo yêu cầu bài tập (Task 1A), nhóm phải nộp **một** checklist **hơn 40 mục** phủ đủ bốn interface aspect. File này gộp với phần của các thành viên khác, khử trùng lặp, rồi đánh số lại thành bản chính thức.

Bốn interface aspect dùng làm chiều phủ:

| Mã | Tên | Phạm vi |
| --- | --- | --- |
| **IA-01** | Chuẩn UI chung | Layout, canh lề, typography, màu sắc, nhất quán, i18n EN/VI, empty/loading |
| **IA-02** | Forms | Nhãn trường, validation, vị trí báo lỗi, trường bắt buộc, upload, rich-text |
| **IA-03** | Navigation | Menu, breadcrumb, tab, sidebar, kéo-thả, back/return, deep link |
| **IA-04** | Feedback / State | Toast, badge, dialog xác nhận, progress bar, màu trạng thái, real-time |

---

## 2. Phạm vi cá nhân đã nhận — thông báo cho nhóm

> Mục này để nhóm đối chiếu **quy tắc không trùng** (§5 đề bài): trong một nhóm, không hai thành viên nào được cùng một kịch bản **và** cùng một tập màn hình. Nếu bạn nào cũng chọn kịch bản A, hãy lấy màn hình khác ba màn hình dưới đây.

**Kịch bản A — Admin tạo và quản lý sự kiện.** Ba màn hình đã nhận:

| Mã | Màn hình | Lý do chọn |
| --- | --- | --- |
| **A1** | Danh sách Events — bộ lọc trạng thái, chấm thông báo | Màn hình danh sách điển hình: phủ mạnh IA-01 (layout, empty state) và IA-03 (tab lọc, deep link vào chi tiết, giữ trạng thái tìm kiếm). Không phụ thuộc dữ liệu dựng sẵn |
| **A2** | Form Add/Edit Event — upload thumbnail 4:3 + banner 24:9, rich-text, validation ngày giờ | Form nặng nhất hệ thống: phủ gần trọn IA-02. Có 6 trường ngày giờ ràng buộc chéo nhau (bắt đầu/kết thúc sự kiện, mở/đóng check-in, mở/đóng đăng ký) nên là điểm kiểm validation giá trị nhất. Cũng chứa toàn bộ cấu hình đăng ký (công tắc student/lecturer/guest, waitlist, vai trò phụ) |
| **A4** | Duyệt Participants & Reviews — màu trạng thái, progress bar, Export | Bổ sung IA-04 mà A1 và A2 chưa phủ đủ: badge trạng thái vòng đời, progress bar, phản hồi khi Export Excel |

**Vì sao không chọn A3 (Panel cấu hình Registration & Roles).** Khảo sát thực tế cho thấy A3 **không phải màn hình riêng**: toàn bộ cấu hình đăng ký nằm trong form Add/Edit Event (section "Registration"), tức đã thuộc A2. Phần hiển thị riêng của nó ở trang chi tiết sự kiện là panel **chỉ đọc** (badge "Admin view only", checkbox bị vô hiệu hoá), không có thao tác nhập liệu nên IA-02 và IA-04 gần như N/A toàn bộ.

**Vì sao không chọn A5 (Tab Check-in).** Phụ thuộc quét QR bằng camera — không khả thi để chụp ma trận cross-platform trên tablet/phone ở Task 3, và người tham gia user-testing ở Task 2 không có vé QR để quét.

---

## 3. Cách dùng checklist này

Mỗi mục là một **tiêu chí kiểm tra được**, áp dụng lặp lại lên từng màn hình bạn phụ trách.

- Đánh dấu **Passed** / **Failed** / **N/A** cho **từng mục × từng màn hình**
- Mục **Failed** → bắt buộc ghi lý do vào cột Notes **và** đính kèm ảnh chụp
- Mục **N/A** → vẫn giữ nguyên dòng, ghi rõ lý do không áp dụng (ví dụ: *màn hình không có form nhập*). **Không xoá dòng** — TA cần thấy bạn đã cân nhắc rồi mới loại
- Mục **Passed** → không cần ảnh, không bắt buộc ghi chú
- Mọi lỗi tìm được phải nộp lên Google Form **và** gộp vào Bug & Usability Findings Log

> ⚠️ Lưu ý: các mục dưới đây là **tiêu chí**, không phải kết luận. Ví dụ *"Mỗi input có id duy nhất"* là tiêu chí; *"ô chọn ngày bị trùng id"* là phát hiện, thuộc về Task 1B chứ không thuộc checklist.

---

## 4. Checklist — 20 mục

### IA-01 · Chuẩn UI chung

| ID | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- |
| GUI-01-001 | Layout, canh lề, typography và bảng màu nhất quán giữa các màn hình cùng loại (list, form, chi tiết) | Mở lần lượt vài màn hình cùng loại ở cả bốn nhóm A–D, so vị trí tiêu đề, khoảng cách, cỡ/kiểu chữ và màu | Norman – Consistency; Nielsen #4 | Cao |
| GUI-01-003 | Khi đổi EN ↔ VI, toàn bộ nhãn, thông báo lỗi và trạng thái đều được dịch, không tràn/vỡ layout, thuộc tính `lang` đổi theo, và ngày giờ/số được định dạng theo locale đang chọn một cách nhất quán trên mọi màn hình | Chuyển ngôn ngữ trên nhiều màn hình, rà chuỗi còn sót, kiểm tra tràn chữ và `lang`; đối chiếu cùng một mốc thời gian sự kiện hiển thị ở danh sách, trang chi tiết, vé và audit log ở cả hai ngôn ngữ | Nielsen #2; WCAG 3.1.2 | Cao |
| GUI-01-004 | Trạng thái rỗng và trạng thái đang tải hiển thị thông báo/placeholder có ý nghĩa (kèm gợi ý hành động), không để vùng trắng trơn | Lọc/tìm ra tập rỗng hoặc mở màn hình sau khi dữ liệu reset; tải chậm để quan sát loading | Nielsen #1 | Trung bình |
| GUI-01-006 | Ở bề rộng màn hình hẹp (≈320–480 px), nội dung tự sắp xếp lại mà không phải cuộn ngang, bảng danh sách vẫn đọc được đủ thông tin, dialog nằm gọn trong khung nhìn và đóng được, mọi vùng chạm đạt kích thước tối thiểu | Thu cửa sổ về 320 px hoặc dùng chế độ thiết bị di động trên các danh sách Events/Users/Support, form Add/Edit Event và một dialog xác nhận; kiểm tra cuộn ngang, cách bảng thu gọn, nút đóng dialog và kích thước vùng chạm | WCAG 1.4.10; WCAG 2.5.5 | Cao |
| GUI-01-007 | Văn bản và thành phần giao diện đạt tỉ lệ tương phản tối thiểu so với nền, thứ tự heading đi liền mạch không nhảy cấp, và mọi nút chỉ có icon đều có tên trợ năng mô tả hành động | Dùng công cụ đo tương phản trên nhãn, badge, chữ trên nền màu; rà cây heading của vài trang bằng trình kiểm tra phần tử; kiểm tra từng nút icon (xoá, sửa, đóng lightbox, chuyển ngôn ngữ) xem có nhãn văn bản | WCAG 1.4.3; WCAG 1.3.1; WCAG 4.1.2 | Cao |

### IA-02 · Forms

| ID | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- |
| GUI-02-001 | Mọi trường bắt buộc được đánh dấu nhất quán bằng một quy ước duy nhất, và quy ước đó được giải thích | Rà toàn bộ trường trên nhiều form (Add/Edit Event, đăng ký, support), đối chiếu ký hiệu trường bắt buộc | Nielsen #4 | Cao |
| GUI-02-002 | Mỗi input có nhãn nhìn thấy được và liên kết chương trình với trường (`<label for>` ↔ `id` duy nhất) | Dùng trình kiểm tra phần tử/đọc màn hình trên vài form, xác nhận từng input có label gắn đúng và id không trùng | WCAG 1.3.1; Nielsen #6 | Cao |
| GUI-02-003 | Lỗi validation hiện ngay cạnh trường sai, mô tả cụ thể và gợi ý cách sửa (không chỉ báo lỗi chung ở đầu form) | Bỏ trống/nhập sai từng trường (gồm ràng buộc ngày giờ chéo), quan sát vị trí và nội dung thông báo lỗi | Nielsen #9; Norman – Feedback | Cao |
| GUI-02-004 | Upload ảnh/file kiểm soát và truyền đạt ràng buộc (tỉ lệ 4:3 & 24:9, định dạng, dung lượng); từ chối file sai kèm thông báo rõ | Thử upload ảnh sai tỉ lệ, sai định dạng, quá dung lượng ở form Event và support; đọc thông báo trả về | Nielsen #5; Norman – Constraints | Cao |
| GUI-02-005 | Mọi điều khiển chọn giá trị (dropdown đơn/đa chọn, checkbox, radio, toggle, date-time picker, number input, textarea, rich-text editor, thang sao 1–5) thể hiện rõ giá trị đang chọn, thao tác được bằng bàn phím, và nạp lại đúng giá trị đã lưu khi mở lại ở chế độ Edit | Trên form Add/Edit Event, cấu hình đăng ký, form đăng ký và form đánh giá: đặt giá trị cho từng loại điều khiển bằng chuột rồi bằng bàn phím, lưu, mở lại bản ghi và đối chiếu giá trị hiển thị | Norman – Visibility; WCAG 2.1.1; Nielsen #6 | Cao |

### IA-03 · Navigation

| ID | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- |
| GUI-03-001 | Breadcrumb/nút back/return đưa về đúng màn hình cha, và deep link tới chi tiết mở đúng đối tượng | Đi sâu vào chi tiết (event, user, request) rồi back; mở trực tiếp một deep link và đối chiếu đối tượng | Nielsen #3; Shneiderman #3 | Trung bình |
| GUI-03-002 | Điều hướng bàn phím hoạt động: thứ tự tab hợp lý theo dòng đọc, viền focus nhìn thấy được, Esc đóng dialog, focus không thoát khỏi dialog đang mở | Chỉ dùng Tab/Shift-Tab/Esc duyệt form và dialog, quan sát vòng focus và viền focus | WCAG 2.4.7; WCAG 2.1.2; Shneiderman #3 | Cao |
| GUI-03-003 | Cấu trúc điều hướng (sidebar/menu/tab) đồng nhất và giữ nguyên vị trí khi chuyển giữa các khu vực, phản ánh đúng phân quyền đang đăng nhập | Đăng nhập bằng các vai trò khác nhau, chuyển khu vực, kiểm tra menu ổn định và chỉ hiện mục được phép | Nielsen #4; Norman – Mapping | Trung bình |
| GUI-03-004 | Vị trí đang đứng được hiển thị rõ: mục menu/tab tương ứng được đánh dấu active và tiêu đề trang khớp nhãn menu | Duyệt từng mục menu/tab, kiểm tra highlight active và đối chiếu tiêu đề trang với nhãn | Nielsen #1; Shneiderman #1 | Cao |
| GUI-03-005 | Mọi danh sách/bảng hiển thị rõ tiêu chí tìm kiếm và bộ lọc đang áp dụng cùng tổng số kết quả, phân trang cho biết trang hiện tại trên tổng số trang, và bộ tiêu chí này được giữ nguyên khi quay lại từ màn hình chi tiết | Trên các danh sách Events / Users / Support Requests: nhập từ khoá, chọn bộ lọc, sang trang 2, mở một bản ghi rồi bấm back — kiểm tra chip/nhãn tiêu chí, số kết quả, chỉ báo trang và trạng thái sau khi quay lại | Nielsen #1; Shneiderman #3 | Cao |

### IA-04 · Feedback / State

| ID | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- |
| GUI-04-001 | Mọi hành động phá huỷ/không hồi phục dễ (xoá, chặn, reset, huỷ đăng ký) đều có dialog xác nhận nêu rõ đối tượng bị tác động | Bấm xoá/chặn/reset/huỷ, đọc dialog xem có nêu tên đối tượng cụ thể và cho phép huỷ thao tác | Shneiderman #6; Nielsen #3 | Cao |
| GUI-04-002 | Mỗi hành động của người dùng đều có phản hồi tức thời (toast/loading/đổi trạng thái) xác nhận thành công hoặc thất bại | Thực hiện lưu/publish/đăng ký/gửi request và các thao tác dài (Export Excel, Preview), quan sát có phản hồi trong thời gian hợp lý | Nielsen #1; Norman – Feedback; Shneiderman #3 | Cao |
| GUI-04-003 | Trạng thái (Draft/Published, Registered/Pending/Confirmed/Waitlisted…) được thể hiện bằng nhãn chữ kèm màu, không chỉ dựa vào màu, và cùng một trạng thái luôn dùng cùng một màu/nhãn toàn hệ thống | Đối chiếu badge trạng thái ở các màn hình khác nhau; kiểm tra mỗi badge có nhãn chữ và ánh xạ màu–trạng thái nhất quán | WCAG 1.4.1; Norman – Consistency | Trung bình |
| GUI-04-004 | Mọi thành phần truyền tin không bằng văn bản hoặc tự thay đổi (KPI card, progress bar, carousel, barcode/QR, lightbox ảnh, audit log, notification dot, cập nhật real-time) đều có nhãn/văn bản thay thế nêu rõ ý nghĩa và giá trị, cho phép dừng hoặc điều khiển nội dung tự chạy, và phản ánh dữ liệu mới mà không cần tải lại thủ công | Mở dashboard, trang chủ có carousel, vé QR, lightbox ảnh trong support request và audit log: kiểm tra alt/nhãn kèm giá trị (`đã đăng ký / tối đa`, % tiến trình, số thông báo), thử dừng carousel, tạo thay đổi ở tab khác để xem dữ liệu/chấm thông báo tự cập nhật | WCAG 1.1.1; WCAG 2.2.2; Nielsen #1; Norman – Feedback | Trung bình |
| GUI-04-005 | Khi mất mạng, hết phiên đăng nhập hoặc tải dữ liệu thất bại, hệ thống báo bằng ngôn ngữ người dùng đang chọn, nêu rõ cách khắc phục (thử lại / đăng nhập lại), không hiển thị mã lỗi thô, và không làm mất dữ liệu người dùng đang nhập dở | Ngắt mạng giữa lúc lưu form nhiều section; để phiên hết hạn rồi bấm một hành động; chặn một request tải danh sách — quan sát thông báo, tuỳ chọn thử lại và nội dung form sau khi lỗi | Nielsen #9; Shneiderman #5; Norman – Feedback | Cao |

---

## 5. Nguồn tham khảo đã dùng

Danh sách này thuộc sản phẩm nhóm phải nộp kèm checklist (Task 1A).

| Nguồn | Dùng cho các mục |
| --- | --- |
| Nielsen, J. — *10 Usability Heuristics for User Interface Design* | GUI-01-001, 01-003, 01-004, 02-001, 02-002, 02-003, 02-004, 03-001, 03-003, 03-004, 03-005, 04-001, 04-002, 04-004, 04-005 |
| Norman, D. — *The Design of Everyday Things* (6 nguyên tắc) | GUI-01-001, 02-003, 02-004, 02-005, 03-003, 04-002, 04-003, 04-004, 04-005 |
| Shneiderman, B. — *Eight Golden Rules of Interface Design* | GUI-03-001, 03-002, 03-004, 03-005, 04-001, 04-002, 04-005 |
| W3C — *WCAG 2.1* | GUI-01-003, 01-006, 01-007, 02-002, 02-005, 03-002, 04-003, 04-004 |
| ISTQB Foundation Level Syllabus | Thuật ngữ và khái niệm kiểm thử chung |
| Slide môn học — *GUI + Usability + Compatibility Testing (AI-First, Combined)* | Khung bốn interface aspect IA-01…IA-04 |

---

## 6. Ghi chú cho nhóm khi gộp

**Cần đạt:** tổng hơn 40 mục sau khi gộp. Phần này đóng góp 20 mục.

**Ba việc cần làm khi gộp:**

1. **Khử trùng lặp.** Các mục dễ đụng nhất với phần của thành viên khác: tính nhất quán layout (GUI-01-001), dialog xác nhận (GUI-04-001), toast phản hồi (GUI-04-002), nhãn trường bắt buộc (GUI-02-001). Nếu trùng, giữ bản diễn đạt cụ thể hơn.
2. **Đánh số lại từ đầu.** Dãy ID hiện có khoảng trống ở IA-01 (thiếu 002, 005) do quá trình tinh chỉnh. Bản chính thức nên đánh liên tục.
3. **Cân lại phân bổ IA.** Bản này cân đều 5/5/5/5. Sau khi gộp cả nhóm, kiểm tra không IA nào bị lép.

**Ba mục nên giữ dù có trùng ý** — vì phủ những chiều mà checklist sinh từ heuristic thuần thường bỏ sót:

- **GUI-01-006** (responsive) — Nielsen/Norman/Shneiderman ra đời trước kỷ nguyên đa thiết bị, không khung nào có heuristic về kích thước màn hình. Chiều này chỉ xuất hiện khi đối chiếu WCAG 2.1.
- **GUI-01-007** (tương phản, thứ tự heading, nhãn nút icon) — đây là thuộc tính không nhìn thấy bằng mắt thường, phải đo hoặc đọc DOM mới biết.
- **GUI-04-005** (lỗi hệ thống) — Nielsen #9 dễ bị hiểu hẹp thành *lỗi do người dùng nhập sai*; lỗi hạ tầng là một họ khác hẳn. Đặc biệt quan trọng vì EMS chạy qua tunnel và dữ liệu hay bị reset.

---

## 7. Mẫu bảng ghi kết quả (Task 1B)

Ba cột màn hình đã điền sẵn theo phạm vi ở §2. Thành viên khác thay bằng màn hình của mình.

| ID | Mục kiểm tra | A1 Danh sách Events | A2 Form Add/Edit Event | A4 Participants & Reviews | Notes |
| --- | --- | --- | --- | --- | --- |
| GUI-01-001 | Layout, canh lề, typography, màu nhất quán | | | | |
| GUI-01-003 | i18n EN/VI đầy đủ, không tràn chữ, đúng locale | | | | |
| GUI-01-004 | Empty/loading state có ý nghĩa | | | | |
| GUI-01-006 | Responsive ở 320–480 px | | | | |
| GUI-01-007 | Tương phản, thứ tự heading, nhãn nút icon | | | | |
| GUI-02-001 | Quy ước trường bắt buộc nhất quán | | | | |
| GUI-02-002 | Input có nhãn và liên kết label ↔ id | | | | |
| GUI-02-003 | Lỗi validation cạnh trường, cụ thể | | | | |
| GUI-02-004 | Upload kiểm soát và truyền đạt ràng buộc | | | | |
| GUI-02-005 | Điều khiển chọn giá trị rõ ràng, nạp lại đúng | | | | |
| GUI-03-001 | Breadcrumb/back/deep link đúng đích | | | | |
| GUI-03-002 | Điều hướng bàn phím, focus, Esc | | | | |
| GUI-03-003 | Cấu trúc điều hướng ổn định theo phân quyền | | | | |
| GUI-03-004 | Đánh dấu vị trí đang đứng | | | | |
| GUI-03-005 | Trạng thái tìm kiếm/lọc/phân trang được giữ | | | | |
| GUI-04-001 | Dialog xác nhận cho hành động phá huỷ | | | | |
| GUI-04-002 | Phản hồi tức thời cho mọi hành động | | | | |
| GUI-04-003 | Badge trạng thái có chữ, màu nhất quán | | | | |
| GUI-04-004 | Thành phần phi văn bản có nhãn thay thế | | | | |
| GUI-04-005 | Xử lý lỗi hệ thống, không mất dữ liệu đang nhập | | | | |

**Quy ước điền:** `P` = Passed · `F` = Failed (bắt buộc kèm Notes + ảnh) · `N/A` = không áp dụng (bắt buộc kèm lý do)
