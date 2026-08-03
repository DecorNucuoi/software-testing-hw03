# Checklist Kiểm thử GUI — EMS (14 mục)

Phân bổ IA: **IA-01 = 4 · IA-02 = 4 · IA-03 = 3 · IA-04 = 3** (tổng 14, không IA nào dưới 3).

| ID | IA | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- | --- |
| GUI-01-001 | IA-01 | Layout, canh lề, typography và bảng màu nhất quán giữa các màn hình cùng loại (list, form, chi tiết) | Mở lần lượt vài màn hình cùng loại ở cả bốn nhóm A–D, so vị trí tiêu đề, khoảng cách, cỡ/kiểu chữ và màu | Norman – Consistency; Nielsen #4 | Cao |
| GUI-01-002 | IA-01 | Vị trí đang đứng được hiển thị rõ: mục menu/tab tương ứng được đánh dấu active và tiêu đề trang khớp nhãn menu | Duyệt từng mục menu/tab, kiểm tra highlight active và đối chiếu tiêu đề trang với nhãn | Nielsen #1; Shneiderman #1 | Cao |
| GUI-01-003 | IA-01 | Khi đổi EN ↔ VI, toàn bộ nhãn, thông báo lỗi và trạng thái đều được dịch, không tràn/vỡ layout và thuộc tính `lang` đổi theo | Chuyển ngôn ngữ trên nhiều màn hình, rà chuỗi còn sót, kiểm tra tràn chữ và `lang` của trang | Nielsen #2; WCAG 3.1.2 | Cao |
| GUI-01-004 | IA-01 | Trạng thái rỗng và trạng thái đang tải hiển thị thông báo/placeholder có ý nghĩa (kèm gợi ý hành động), không để vùng trắng trơn | Lọc/tìm ra tập rỗng hoặc mở màn hình sau khi dữ liệu reset; tải chậm để quan sát loading | Nielsen #1 | Trung bình |
| GUI-02-001 | IA-02 | Mọi trường bắt buộc được đánh dấu nhất quán bằng một quy ước duy nhất, và quy ước đó được giải thích | Rà toàn bộ trường trên nhiều form (Add/Edit Event, đăng ký, support), đối chiếu ký hiệu trường bắt buộc | Nielsen #4 | Cao |
| GUI-02-002 | IA-02 | Mỗi input có nhãn nhìn thấy được và liên kết chương trình với trường (`<label for>` ↔ `id` duy nhất) | Dùng trình kiểm tra phần tử/đọc màn hình trên vài form, xác nhận từng input có label gắn đúng và id không trùng | WCAG 1.3.1; Nielsen #6 | Cao |
| GUI-02-003 | IA-02 | Lỗi validation hiện ngay cạnh trường sai, mô tả cụ thể và gợi ý cách sửa (không chỉ báo lỗi chung ở đầu form) | Bỏ trống/nhập sai từng trường (gồm ràng buộc ngày giờ chéo), quan sát vị trí và nội dung thông báo lỗi | Nielsen #9; Norman – Feedback | Cao |
| GUI-02-004 | IA-02 | Upload ảnh/file kiểm soát và truyền đạt ràng buộc (tỉ lệ 4:3 & 24:9, định dạng, dung lượng); từ chối file sai kèm thông báo rõ | Thử upload ảnh sai tỉ lệ, sai định dạng, quá dung lượng ở form Event và support; đọc thông báo trả về | Nielsen #5; Norman – Constraints | Cao |
| GUI-03-001 | IA-03 | Breadcrumb/nút back/return đưa về đúng màn hình cha, và deep link tới chi tiết mở đúng đối tượng | Đi sâu vào chi tiết (event, user, request) rồi back; mở trực tiếp một deep link và đối chiếu đối tượng | Nielsen #3; Shneiderman #3 | Trung bình |
| GUI-03-002 | IA-03 | Điều hướng bàn phím hoạt động: thứ tự tab hợp lý theo dòng đọc, viền focus nhìn thấy được, Esc đóng dialog, focus không thoát khỏi dialog đang mở | Chỉ dùng Tab/Shift-Tab/Esc duyệt form và dialog, quan sát vòng focus và viền focus | WCAG 2.4.7; WCAG 2.1.2; Shneiderman #3 | Cao |
| GUI-03-003 | IA-03 | Cấu trúc điều hướng (sidebar/menu/tab) đồng nhất và giữ nguyên vị trí khi chuyển giữa các khu vực, phản ánh đúng phân quyền đang đăng nhập | Đăng nhập bằng các vai trò khác nhau, chuyển khu vực, kiểm tra menu ổn định và chỉ hiện mục được phép | Nielsen #4; Norman – Mapping | Trung bình |
| GUI-04-001 | IA-04 | Mọi hành động phá huỷ/không hồi phục dễ (xoá, chặn, reset, huỷ đăng ký) đều có dialog xác nhận nêu rõ đối tượng bị tác động | Bấm xoá/chặn/reset/huỷ, đọc dialog xem có nêu tên đối tượng cụ thể và cho phép huỷ thao tác | Shneiderman #6; Nielsen #3 | Cao |
| GUI-04-002 | IA-04 | Mỗi hành động của người dùng đều có phản hồi tức thời (toast/loading/đổi trạng thái) xác nhận thành công hoặc thất bại | Thực hiện lưu/publish/đăng ký/gửi request và các thao tác dài, quan sát có phản hồi trong thời gian hợp lý | Nielsen #1; Norman – Feedback; Shneiderman #3 | Cao |
| GUI-04-003 | IA-04 | Trạng thái (Draft/Published, Registered/Pending/Confirmed/Waitlisted…) được thể hiện bằng nhãn chữ kèm màu, không chỉ dựa vào màu, và cùng một trạng thái luôn dùng cùng một màu/nhãn toàn hệ thống | Đối chiếu badge trạng thái ở các màn hình khác nhau; kiểm tra mỗi badge có nhãn chữ và ánh xạ màu–trạng thái nhất quán | WCAG 1.4.1; Norman – Consistency | Trung bình |

---

## Vì sao chọn 14 mục này (và loại các mục khác)

**Lượt 1 — theo khung lý thuyết.** Duyệt Nielsen/Norman/Shneiderman, tôi ưu tiên các heuristic áp dụng được lên *mọi* loại màn hình EMS: tính nhất quán (Norman-Consistency, Nielsen #4), khả kiến vị trí/trạng thái (Nielsen #1), ngăn lỗi và phục hồi (Nielsen #5, #9, #3), kiểm soát của người dùng (Shneiderman #3, #6). Loại bỏ các heuristic khó biến thành tiêu chí Pass/Fail tổng quát (ví dụ "help & documentation", "aesthetic minimalism") vì dễ rơi vào mơ hồ như "giao diện đẹp".

**Lượt 2 — đối chiếu inventory widget (§3.1).** Kiểm tra độ phủ widget và thay các mục trùng ý bằng mục phủ widget đặc thù của EMS: upload theo tỉ lệ cố định (GUI-02-004), badge trạng thái/vòng đời (GUI-04-003), empty/loading state do dữ liệu hay bị reset (GUI-01-004), deep link + breadcrumb (GUI-03-001). Nhờ vậy các widget rủi ro cao nhất (upload ràng buộc tỉ lệ, badge trạng thái, form đa section) đều có mục kiểm.

**Lượt 3 — phản biện lỗ hổng.** Bổ trợ ba trục dễ bị bỏ sót: accessibility (label liên kết `for/id` — GUI-02-002; tương phản/không-chỉ-màu — GUI-04-003), điều hướng bàn phím (tab order, focus trap, Esc — GUI-03-002), và i18n EN/VI gồm cả tràn chữ và thuộc tính `lang` (GUI-01-003). Đây là các mục hay bị quên nhưng có giá trị cao khi gộp vào bộ chung.

**Các mục bị loại vì hẹp/không đủ tổng quát:** những mục chỉ đúng cho một màn hình (ví dụ "carousel trang chủ auto-play đúng nhịp", "barcode/QR của vé quét được", "rich-text editor có nút bôi đậm", "export Excel đúng số cột", "sao đánh giá 1–5 bấm được"). Chúng là kiểm thử chức năng gắn với một màn hình duy nhất, vi phạm §2.2, và nhiều khả năng bị khử khi gộp checklist nhóm — nên nhường chỗ cho các tiêu chí bao quát ở trên.

**Cân bằng ưu tiên & IA:** giữ đúng 4/4/3/3, mỗi mục là *tiêu chí* (không phải finding), có nguồn cụ thể và cách kiểm chứng trả lời được Pass/Fail — thoả toàn bộ checklist tự kiểm ở §8.

---

# Rà soát độ phủ widget (§3.1)

14 mục gốc giữ nguyên. Bảng dưới đối chiếu từng widget trong inventory §3.1 với mục checklist đang phủ nó.

## A. Hiển thị dữ liệu

| Widget | Mục phủ |
| --- | --- |
| Bảng danh sách | GUI-01-001, GUI-01-004 |
| Phân trang | **CHƯA PHỦ** |
| Search box | **CHƯA PHỦ** (chỉ chạm gián tiếp qua GUI-01-004 khi kết quả rỗng) |
| Bộ lọc trạng thái/role/category | **CHƯA PHỦ** (như trên) |
| Thẻ card | GUI-01-001 (chỉ ở khía cạnh nhất quán trình bày) |
| Carousel | **CHƯA PHỦ** |
| KPI card | **CHƯA PHỦ** |
| Progress bar | **CHƯA PHỦ** |
| Badge trạng thái | GUI-04-003 |
| Barcode / QR | **CHƯA PHỦ** |
| Lightbox ảnh | **CHƯA PHỦ** |
| Audit log | **CHƯA PHỦ** |

## B. Nhập liệu

| Widget | Mục phủ |
| --- | --- |
| Form nhiều section | GUI-02-001, GUI-02-003 |
| Text input | GUI-02-002, GUI-02-003 |
| Textarea | GUI-02-002 (nhãn) — **CHƯA PHỦ** phần trạng thái/thao tác |
| Number input | **CHƯA PHỦ** |
| Dropdown đơn chọn | **CHƯA PHỦ** |
| Dropdown đa chọn | **CHƯA PHỦ** |
| Checkbox | **CHƯA PHỦ** |
| Toggle switch | **CHƯA PHỦ** |
| Radio | **CHƯA PHỦ** |
| Date-time picker | GUI-02-003 (chỉ phần lỗi ràng buộc chéo) — **CHƯA PHỦ** phần thao tác/hiển thị giá trị |
| Rich-text editor | **CHƯA PHỦ** |
| Upload ảnh tỉ lệ cố định (4:3, 24:9) | GUI-02-004 |
| Upload file đính kèm | GUI-02-004 |
| Thang đánh giá sao 1–5 | **CHƯA PHỦ** |

## C. Điều hướng

| Widget | Mục phủ |
| --- | --- |
| Sidebar | GUI-03-003 |
| Menu | GUI-01-002, GUI-03-003 |
| Tab | GUI-01-002, GUI-03-003 |
| Breadcrumb | GUI-03-001 |
| Nút back / return | GUI-03-001 |
| Deep link tới chi tiết | GUI-03-001 |

## D. Phản hồi

| Widget | Mục phủ |
| --- | --- |
| Toast | GUI-04-002 |
| Dialog xác nhận | GUI-04-001, GUI-03-002 (focus/Esc) |
| Thông báo lỗi cạnh trường | GUI-02-003 |
| Empty state | GUI-01-004 |
| Loading state | GUI-01-004, GUI-04-002 |
| Notification dot | **CHƯA PHỦ** |
| Cập nhật real-time | **CHƯA PHỦ** |

## E. Hành động khác

| Widget | Mục phủ |
| --- | --- |
| Export ra Excel | GUI-04-002 (phản hồi tiến trình/kết quả) |
| Preview | GUI-04-002 |
| Lưu nháp / phát hành | GUI-04-002, GUI-04-003 |

---

# 3 mục bổ sung phủ toàn bộ widget CHƯA PHỦ

| ID | IA | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- | --- |
| GUI-01-005 | IA-01 | Mọi danh sách/bảng hiển thị rõ tiêu chí tìm kiếm và bộ lọc đang áp dụng cùng tổng số kết quả, phân trang cho biết trang hiện tại trên tổng số trang, và bộ tiêu chí này được giữ nguyên khi quay lại từ màn hình chi tiết | Trên các danh sách Events / Users / Support Requests: nhập từ khoá, chọn bộ lọc, sang trang 2, mở một bản ghi rồi bấm back — kiểm tra chip/nhãn tiêu chí, số kết quả, chỉ báo trang và trạng thái sau khi quay lại | Nielsen #1; Shneiderman #3 | Cao |
| GUI-02-005 | IA-02 | Mọi điều khiển chọn giá trị (dropdown đơn/đa chọn, checkbox, radio, toggle, date-time picker, number input, textarea, rich-text editor, thang sao 1–5) thể hiện rõ giá trị đang chọn, thao tác được bằng bàn phím, và nạp lại đúng giá trị đã lưu khi mở lại ở chế độ Edit | Trên form Add/Edit Event, cấu hình đăng ký, form đăng ký và form đánh giá: đặt giá trị cho từng loại điều khiển bằng chuột rồi bằng bàn phím, lưu, mở lại bản ghi và đối chiếu giá trị hiển thị | Norman – Visibility; WCAG 2.1.1; Nielsen #6 | Cao |
| GUI-04-004 | IA-04 | Mọi thành phần truyền tin không bằng văn bản hoặc tự thay đổi (KPI card, progress bar, carousel, barcode/QR, lightbox ảnh, audit log, notification dot, cập nhật real-time) đều có nhãn/văn bản thay thế nêu rõ ý nghĩa và giá trị, cho phép người dùng dừng hoặc điều khiển nội dung tự chạy, và phản ánh dữ liệu mới mà không cần tải lại thủ công | Mở dashboard, trang chủ có carousel, vé QR, lightbox ảnh trong support request và audit log: kiểm tra alt/nhãn kèm giá trị (`đã đăng ký / tối đa`, % tiến trình, số thông báo), thử dừng carousel, và tạo thay đổi ở tab khác để xem dữ liệu/chấm thông báo tự cập nhật | WCAG 1.1.1; WCAG 2.2.2; Nielsen #1; Norman – Feedback | Trung bình |

**Sau bổ sung:** tổng 17 mục — IA-01 = 5, IA-02 = 5, IA-03 = 3, IA-04 = 4.

**Cách 3 mục này lấp kín phần CHƯA PHỦ:**

- **GUI-01-005** → phân trang, search box, bộ lọc, bảng danh sách và thẻ card ở khía cạnh trạng thái truy vấn.
- **GUI-02-005** → toàn bộ điều khiển nhập liệu còn lại: number input, textarea, dropdown đơn/đa, checkbox, toggle, radio, date-time picker, rich-text editor, thang sao 1–5.
- **GUI-04-004** → KPI card, progress bar, carousel, barcode/QR, lightbox ảnh, audit log, notification dot, cập nhật real-time.

Cả ba đều viết ở dạng tiêu chí áp dụng cho nhiều màn hình, không bám vào một màn hình duy nhất, và trả lời được Pass/Fail bằng thao tác quan sát trực tiếp.

---

# Lượt phản biện — rà lỗ hổng theo 7 nhóm

Checklist hiện tại: 17 mục. Dưới đây là đánh giá thẳng thắn từng nhóm.

| Nhóm | Hiện trạng | Kết luận |
| --- | --- | --- |
| **1. Accessibility** | Có GUI-02-002 (label ↔ id), GUI-04-003 (không chỉ dựa vào màu), GUI-04-004 (alt text). **Thiếu:** tỉ lệ tương phản màu, thứ tự heading `h1→h2→h3`, tên trợ năng cho nút chỉ có icon | **Bổ sung** |
| **2. Điều hướng bàn phím** | GUI-03-002 đã phủ tab order, viền focus, Esc, focus trap. **Thiếu nhẹ:** focus quay lại phần tử đã kích hoạt sau khi đóng dialog; skip-link | Đã phủ phần lớn — **không bổ sung** |
| **3. I18n EN/VI** | GUI-01-003 phủ dịch sót, tràn chữ, `lang`. **Thiếu:** định dạng ngày giờ/số theo locale — rủi ro thật vì EMS đầy trường ngày giờ (`27/07/2026` vs `07/27/2026`) | **Sửa GUI-01-003** thay vì thêm mục mới |
| **4. Responsive** | Không mục nào chạm tới. Bảng danh sách, dialog xác nhận, sidebar trên màn hình hẹp đều chưa có tiêu chí | **Bổ sung — lỗ hổng lớn nhất** |
| **5. Dark mode / RTL** | Không mục nào chạm tới | **Không bổ sung** — xem giải trình bên dưới |
| **6. Lỗi hệ thống** | Không mục nào chạm tới. GUI-04-002 chỉ nói "có phản hồi", không nói phản hồi khi mất mạng / hết phiên / tải thất bại | **Bổ sung — ưu tiên cao** |
| **7. Empty / loading** | GUI-01-004 đã phủ. **Thiếu nhẹ:** phân biệt "rỗng do lọc" vs "rỗng do chưa có dữ liệu", chống double-submit | Đã phủ phần lớn — **không bổ sung** |

## 3 mục bổ sung

| ID | IA | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- | --- |
| GUI-01-006 | IA-01 | Ở bề rộng màn hình hẹp (≈320–480 px), nội dung tự sắp xếp lại mà không phải cuộn ngang, bảng danh sách vẫn đọc được đủ thông tin, dialog nằm gọn trong khung nhìn và đóng được, mọi vùng chạm đạt kích thước tối thiểu | Thu cửa sổ về 320 px hoặc mở bằng chế độ thiết bị di động trên các danh sách Events/Users/Support, form Add/Edit Event và một dialog xác nhận; kiểm tra cuộn ngang, cách bảng thu gọn, nút đóng dialog và kích thước vùng chạm | WCAG 1.4.10; WCAG 2.5.5 | Cao |
| GUI-01-007 | IA-01 | Văn bản và thành phần giao diện đạt tỉ lệ tương phản tối thiểu so với nền, thứ tự heading đi liền mạch không nhảy cấp, và mọi nút chỉ có icon đều có tên trợ năng mô tả hành động | Dùng công cụ đo tương phản trên nhãn, badge, chữ trên nền màu; dùng trình kiểm tra phần tử rà cây heading của vài trang; rê/kiểm tra từng nút icon (xoá, sửa, đóng lightbox, chuyển ngôn ngữ) xem có nhãn văn bản | WCAG 1.4.3; WCAG 1.3.1; WCAG 4.1.2 | Cao |
| GUI-04-005 | IA-04 | Khi mất mạng, hết phiên đăng nhập hoặc tải dữ liệu thất bại, hệ thống báo bằng ngôn ngữ người dùng đang chọn, nêu rõ cách khắc phục (thử lại / đăng nhập lại), không hiển thị mã lỗi thô, và không làm mất dữ liệu người dùng đang nhập dở | Ngắt mạng giữa lúc lưu form nhiều section; để phiên hết hạn rồi bấm một hành động; chặn một request tải danh sách — quan sát thông báo, tuỳ chọn thử lại và nội dung form sau khi lỗi | Nielsen #9; Shneiderman #5; Norman – Feedback | Cao |

## Vì sao lượt 1 bỏ sót từng mục

**GUI-01-006 (Responsive).** Lượt 1 duyệt Nielsen/Norman/Shneiderman — cả ba khung ra đời trước kỷ nguyên đa thiết bị và phát biểu ở mức trừu tượng, không có heuristic nào tên là "responsive". Sinh checklist *từ khung lý thuyết* nên tự nhiên trượt mất chiều kích thước màn hình; chiều này chỉ xuất hiện khi đối chiếu với WCAG 2.1 (reflow, target size).

**GUI-01-007 (Tương phản, heading, tên nút icon).** Lượt 1 có chạm accessibility nhưng qua đường Nielsen #6 (recognition) — dẫn tới mục về *nhãn trường*, thứ dễ thấy khi nhìn form. Tương phản màu và cây heading là thuộc tính **không nhìn thấy bằng mắt thường**, phải đo hoặc đọc DOM mới biết, nên không nổi lên khi tôi duyệt theo heuristic hành vi.

**GUI-04-005 (Lỗi hệ thống).** Lượt 1 diễn giải Nielsen #9 ("giúp người dùng nhận ra và khắc phục lỗi") theo hướng *lỗi do người dùng nhập sai* — thành GUI-02-003 về validation. Lỗi do **hệ thống/hạ tầng** là một họ khác hẳn và bị bỏ quên, dù §3.2 đã cảnh báo EMS chạy qua tunnel và dữ liệu có thể bị reset. Đây là lỗ hổng đáng lo nhất vì rủi ro mất dữ liệu form đang nhập dở.

## Sửa GUI-01-003 (không tính vào 3 mục bổ sung)

Mở rộng phần cuối của GUI-01-003 thành:

> …không tràn/vỡ layout, thuộc tính `lang` đổi theo, **và ngày giờ/số được định dạng theo locale đang chọn một cách nhất quán trên mọi màn hình**.
>
> Cách kiểm chứng bổ sung: đối chiếu cùng một mốc thời gian sự kiện hiển thị ở danh sách, trang chi tiết, vé và audit log khi ở EN và khi ở VI.

Lý do lượt 1 bỏ sót: tôi coi i18n chủ yếu là bài toán *dịch chuỗi*, trong khi định dạng ngày giờ là thứ **thay đổi mà không có chuỗi nào sai** — không có dấu hiệu thị giác nào báo lỗi, phải chủ động so sánh mới phát hiện.

## Vì sao không bổ sung Dark mode / RTL

§3.2 mô tả đặc thù EMS không nhắc tới dark mode hay bố cục phải-sang-trái; hai ngôn ngữ được hỗ trợ (EN, VI) đều viết trái-sang-phải. Nếu thêm mục cho hai thứ này, gần như chắc chắn chúng sẽ nhận **N/A trên toàn bộ màn hình** — tức là chiếm chỗ trong ngân sách checklist mà không sinh ra thông tin kiểm thử nào. Với trần 3 mục, đổi chúng lấy responsive và lỗi hệ thống là đánh đổi đúng. Nếu sau này EMS thêm dark mode hoặc ngôn ngữ RTL (ví dụ tiếng Ả Rập), đây là hai mục nên thêm đầu tiên.

---

# Đối chiếu checklist tự kiểm §8

**Tổng hiện tại: 20 mục** — IA-01 = 7, IA-02 = 5, IA-03 = 3, IA-04 = 5.

| Tiêu chí §8 | Kết quả |
| --- | --- |
| Tổng số mục đúng 14 | ❌ **CHƯA ĐẠT** — hiện 20 mục. Xem giải trình bên dưới |
| Cả bốn IA đều có mặt, không IA nào dưới 3 mục | ✅ Đạt (thấp nhất IA-03 = 3) |
| Không mục nào là *finding* | ✅ Đạt — mọi mục đều là câu khẳng định kiểm chứng được |
| Không mục nào chỉ áp dụng cho đúng một màn hình | ✅ Đạt — mục hẹp nhất là GUI-04-004 vẫn trải trên dashboard, trang chủ, vé, lightbox, audit log |
| Mỗi mục có nguồn tham khảo cụ thể | ✅ Đạt |
| Mỗi mục có cách kiểm chứng rõ ràng, trả lời được Pass/Fail | ✅ Đạt |
| Đủ bao quát để có giá trị khi gộp vào checklist chung | ✅ Đạt |

## Hai điểm cần bạn quyết

**1. Xung đột số lượng.** §7 quy định rõ: *"lượt 2 và lượt 3 là **thay thế** và tinh chỉnh, không phải cộng dồn — tổng vẫn phải là 14"*. Nhưng hai yêu cầu sau đó lại là "**bổ sung** tối đa 3 mục", nên tôi đã cộng dồn: 14 → 17 → 20. Kết quả hiện tại **vi phạm §8 dòng đầu**. Hai hướng xử lý:

- **Giữ 20 mục** — nếu bạn muốn một kho tiêu chí rộng rồi mới lọc cùng nhóm.
- **Rút về 14 theo đúng §7** — tôi sẽ bỏ 6 mục yếu nhất. Ứng viên bị loại, theo thứ tự: GUI-01-005 (trạng thái lọc/phân trang — hữu ích nhưng ít rủi ro nhất), GUI-04-004 (gộp quá nhiều widget rời rạc vào một mục), GUI-03-003 (chồng lấn GUI-01-001 về tính nhất quán), GUI-01-004 (empty/loading có thể gộp vào GUI-04-005), GUI-02-005 (phần trạng thái đã chọn chồng lấn GUI-02-002), GUI-01-002 (chồng lấn GUI-03-001 về định vị).

**2. Lệch phân bổ IA.** §4 đề nghị 4/4/3/3 cho 14 mục. Ở quy mô 20 mục, IA-01 đã phình lên 7 (35%) trong khi IA-03 đứng yên ở 3 (15%) — vì cả hai lượt phản biện đều đổ vào "chuẩn UI chung". Nếu giữ 20 mục, nên cân lại bằng cách chuyển bớt hoặc thêm cho IA-03.

---

# BẢNG TỔNG HỢP CUỐI CÙNG — 20 mục

> Đây là bản dùng chính thức. Các phần phía trên là nhật ký ba lượt làm việc, giữ lại để truy vết.

**Cân bằng lại IA (không thêm/bớt mục).** Hai mục vốn xếp ở IA-01 nhưng bản chất là điều hướng, nay chuyển sang IA-03 và đổi mã tương ứng:

| ID cũ | ID mới | Lý do chuyển |
| --- | --- | --- |
| GUI-01-002 | **GUI-03-004** | Nói về định vị trên menu/tab — thuộc phạm vi Navigation, không phải chuẩn UI chung |
| GUI-01-005 | **GUI-03-005** | Trọng tâm là giữ trạng thái truy vấn khi quay lại từ chi tiết — hành vi điều hướng |

Dãy số IA-01 vì thế có khoảng trống (001, 003, 004, 006, 007) — cố ý, để mã cũ vẫn truy vết được về phần lập luận phía trên.

**Phân bổ sau khi cân: IA-01 = 5 · IA-02 = 5 · IA-03 = 5 · IA-04 = 5.**

| ID | IA | Mục kiểm tra | Cách kiểm chứng | Nguồn | Ưu tiên |
| --- | --- | --- | --- | --- | --- |
| GUI-01-001 | IA-01 | Layout, canh lề, typography và bảng màu nhất quán giữa các màn hình cùng loại (list, form, chi tiết) | Mở lần lượt vài màn hình cùng loại ở cả bốn nhóm A–D, so vị trí tiêu đề, khoảng cách, cỡ/kiểu chữ và màu | Norman – Consistency; Nielsen #4 | Cao |
| GUI-01-003 | IA-01 | Khi đổi EN ↔ VI, toàn bộ nhãn, thông báo lỗi và trạng thái đều được dịch, không tràn/vỡ layout, thuộc tính `lang` đổi theo, và ngày giờ/số được định dạng theo locale đang chọn một cách nhất quán trên mọi màn hình | Chuyển ngôn ngữ trên nhiều màn hình, rà chuỗi còn sót, kiểm tra tràn chữ và `lang`; đối chiếu cùng một mốc thời gian sự kiện hiển thị ở danh sách, trang chi tiết, vé và audit log ở cả hai ngôn ngữ | Nielsen #2; WCAG 3.1.2 | Cao |
| GUI-01-004 | IA-01 | Trạng thái rỗng và trạng thái đang tải hiển thị thông báo/placeholder có ý nghĩa (kèm gợi ý hành động), không để vùng trắng trơn | Lọc/tìm ra tập rỗng hoặc mở màn hình sau khi dữ liệu reset; tải chậm để quan sát loading | Nielsen #1 | Trung bình |
| GUI-01-006 | IA-01 | Ở bề rộng màn hình hẹp (≈320–480 px), nội dung tự sắp xếp lại mà không phải cuộn ngang, bảng danh sách vẫn đọc được đủ thông tin, dialog nằm gọn trong khung nhìn và đóng được, mọi vùng chạm đạt kích thước tối thiểu | Thu cửa sổ về 320 px hoặc dùng chế độ thiết bị di động trên các danh sách Events/Users/Support, form Add/Edit Event và một dialog xác nhận; kiểm tra cuộn ngang, cách bảng thu gọn, nút đóng dialog và kích thước vùng chạm | WCAG 1.4.10; WCAG 2.5.5 | Cao |
| GUI-01-007 | IA-01 | Văn bản và thành phần giao diện đạt tỉ lệ tương phản tối thiểu so với nền, thứ tự heading đi liền mạch không nhảy cấp, và mọi nút chỉ có icon đều có tên trợ năng mô tả hành động | Dùng công cụ đo tương phản trên nhãn, badge, chữ trên nền màu; rà cây heading của vài trang bằng trình kiểm tra phần tử; kiểm tra từng nút icon (xoá, sửa, đóng lightbox, chuyển ngôn ngữ) xem có nhãn văn bản | WCAG 1.4.3; WCAG 1.3.1; WCAG 4.1.2 | Cao |
| GUI-02-001 | IA-02 | Mọi trường bắt buộc được đánh dấu nhất quán bằng một quy ước duy nhất, và quy ước đó được giải thích | Rà toàn bộ trường trên nhiều form (Add/Edit Event, đăng ký, support), đối chiếu ký hiệu trường bắt buộc | Nielsen #4 | Cao |
| GUI-02-002 | IA-02 | Mỗi input có nhãn nhìn thấy được và liên kết chương trình với trường (`<label for>` ↔ `id` duy nhất) | Dùng trình kiểm tra phần tử/đọc màn hình trên vài form, xác nhận từng input có label gắn đúng và id không trùng | WCAG 1.3.1; Nielsen #6 | Cao |
| GUI-02-003 | IA-02 | Lỗi validation hiện ngay cạnh trường sai, mô tả cụ thể và gợi ý cách sửa (không chỉ báo lỗi chung ở đầu form) | Bỏ trống/nhập sai từng trường (gồm ràng buộc ngày giờ chéo), quan sát vị trí và nội dung thông báo lỗi | Nielsen #9; Norman – Feedback | Cao |
| GUI-02-004 | IA-02 | Upload ảnh/file kiểm soát và truyền đạt ràng buộc (tỉ lệ 4:3 & 24:9, định dạng, dung lượng); từ chối file sai kèm thông báo rõ | Thử upload ảnh sai tỉ lệ, sai định dạng, quá dung lượng ở form Event và support; đọc thông báo trả về | Nielsen #5; Norman – Constraints | Cao |
| GUI-02-005 | IA-02 | Mọi điều khiển chọn giá trị (dropdown đơn/đa chọn, checkbox, radio, toggle, date-time picker, number input, textarea, rich-text editor, thang sao 1–5) thể hiện rõ giá trị đang chọn, thao tác được bằng bàn phím, và nạp lại đúng giá trị đã lưu khi mở lại ở chế độ Edit | Trên form Add/Edit Event, cấu hình đăng ký, form đăng ký và form đánh giá: đặt giá trị cho từng loại điều khiển bằng chuột rồi bằng bàn phím, lưu, mở lại bản ghi và đối chiếu giá trị hiển thị | Norman – Visibility; WCAG 2.1.1; Nielsen #6 | Cao |
| GUI-03-001 | IA-03 | Breadcrumb/nút back/return đưa về đúng màn hình cha, và deep link tới chi tiết mở đúng đối tượng | Đi sâu vào chi tiết (event, user, request) rồi back; mở trực tiếp một deep link và đối chiếu đối tượng | Nielsen #3; Shneiderman #3 | Trung bình |
| GUI-03-002 | IA-03 | Điều hướng bàn phím hoạt động: thứ tự tab hợp lý theo dòng đọc, viền focus nhìn thấy được, Esc đóng dialog, focus không thoát khỏi dialog đang mở | Chỉ dùng Tab/Shift-Tab/Esc duyệt form và dialog, quan sát vòng focus và viền focus | WCAG 2.4.7; WCAG 2.1.2; Shneiderman #3 | Cao |
| GUI-03-003 | IA-03 | Cấu trúc điều hướng (sidebar/menu/tab) đồng nhất và giữ nguyên vị trí khi chuyển giữa các khu vực, phản ánh đúng phân quyền đang đăng nhập | Đăng nhập bằng các vai trò khác nhau, chuyển khu vực, kiểm tra menu ổn định và chỉ hiện mục được phép | Nielsen #4; Norman – Mapping | Trung bình |
| GUI-03-004 | IA-03 | Vị trí đang đứng được hiển thị rõ: mục menu/tab tương ứng được đánh dấu active và tiêu đề trang khớp nhãn menu | Duyệt từng mục menu/tab, kiểm tra highlight active và đối chiếu tiêu đề trang với nhãn | Nielsen #1; Shneiderman #1 | Cao |
| GUI-03-005 | IA-03 | Mọi danh sách/bảng hiển thị rõ tiêu chí tìm kiếm và bộ lọc đang áp dụng cùng tổng số kết quả, phân trang cho biết trang hiện tại trên tổng số trang, và bộ tiêu chí này được giữ nguyên khi quay lại từ màn hình chi tiết | Trên các danh sách Events / Users / Support Requests: nhập từ khoá, chọn bộ lọc, sang trang 2, mở một bản ghi rồi bấm back — kiểm tra chip/nhãn tiêu chí, số kết quả, chỉ báo trang và trạng thái sau khi quay lại | Nielsen #1; Shneiderman #3 | Cao |
| GUI-04-001 | IA-04 | Mọi hành động phá huỷ/không hồi phục dễ (xoá, chặn, reset, huỷ đăng ký) đều có dialog xác nhận nêu rõ đối tượng bị tác động | Bấm xoá/chặn/reset/huỷ, đọc dialog xem có nêu tên đối tượng cụ thể và cho phép huỷ thao tác | Shneiderman #6; Nielsen #3 | Cao |
| GUI-04-002 | IA-04 | Mỗi hành động của người dùng đều có phản hồi tức thời (toast/loading/đổi trạng thái) xác nhận thành công hoặc thất bại | Thực hiện lưu/publish/đăng ký/gửi request và các thao tác dài (Export Excel, Preview), quan sát có phản hồi trong thời gian hợp lý | Nielsen #1; Norman – Feedback; Shneiderman #3 | Cao |
| GUI-04-003 | IA-04 | Trạng thái (Draft/Published, Registered/Pending/Confirmed/Waitlisted…) được thể hiện bằng nhãn chữ kèm màu, không chỉ dựa vào màu, và cùng một trạng thái luôn dùng cùng một màu/nhãn toàn hệ thống | Đối chiếu badge trạng thái ở các màn hình khác nhau; kiểm tra mỗi badge có nhãn chữ và ánh xạ màu–trạng thái nhất quán | WCAG 1.4.1; Norman – Consistency | Trung bình |
| GUI-04-004 | IA-04 | Mọi thành phần truyền tin không bằng văn bản hoặc tự thay đổi (KPI card, progress bar, carousel, barcode/QR, lightbox ảnh, audit log, notification dot, cập nhật real-time) đều có nhãn/văn bản thay thế nêu rõ ý nghĩa và giá trị, cho phép dừng hoặc điều khiển nội dung tự chạy, và phản ánh dữ liệu mới mà không cần tải lại thủ công | Mở dashboard, trang chủ có carousel, vé QR, lightbox ảnh trong support request và audit log: kiểm tra alt/nhãn kèm giá trị (`đã đăng ký / tối đa`, % tiến trình, số thông báo), thử dừng carousel, tạo thay đổi ở tab khác để xem dữ liệu/chấm thông báo tự cập nhật | WCAG 1.1.1; WCAG 2.2.2; Nielsen #1; Norman – Feedback | Trung bình |
| GUI-04-005 | IA-04 | Khi mất mạng, hết phiên đăng nhập hoặc tải dữ liệu thất bại, hệ thống báo bằng ngôn ngữ người dùng đang chọn, nêu rõ cách khắc phục (thử lại / đăng nhập lại), không hiển thị mã lỗi thô, và không làm mất dữ liệu người dùng đang nhập dở | Ngắt mạng giữa lúc lưu form nhiều section; để phiên hết hạn rồi bấm một hành động; chặn một request tải danh sách — quan sát thông báo, tuỳ chọn thử lại và nội dung form sau khi lỗi | Nielsen #9; Shneiderman #5; Norman – Feedback | Cao |

## Đối chiếu §8 lần cuối

| Tiêu chí §8 | Kết quả |
| --- | --- |
| Tổng số mục đúng 14 | ⚠️ **Cố ý lệch** — 20 mục theo quyết định giữ nguyên; dùng làm kho tiêu chí để nhóm lọc khi gộp |
| Cả bốn IA đều có mặt, không IA nào dưới 3 mục | ✅ Đạt — cân đều 5/5/5/5 |
| Không mục nào là *finding* | ✅ Đạt |
| Không mục nào chỉ áp dụng cho đúng một màn hình | ✅ Đạt |
| Mỗi mục có nguồn tham khảo cụ thể | ✅ Đạt |
| Mỗi mục có cách kiểm chứng rõ ràng, Pass/Fail | ✅ Đạt |
| Đủ bao quát để có giá trị khi gộp vào checklist chung | ✅ Đạt |
