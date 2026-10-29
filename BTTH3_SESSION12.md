# Phần 1 — Kiến trúc Hệ điều hành :
1. Theo mục 3a, Máy của bạn đang cùng lúc chạy Word, Chrome, VS Code và phần mềm nộp bài
- Chức năng cốt lõi: Đây là hoạt động của chức năng Quản lý Tiến trình (Process Management) và Quản lý Bộ nhớ (Memory Management) của Hệ điều hành.
- Lý do không bị xung đột (conflict):
  - HĐH áp dụng cơ chế đa nhiệm (multitasking) để chia nhỏ thời gian xử lý của CPU (CPU scheduling) cho từng tiến trình.
2. Khi double-click vào file báo cáo để mở, hành động đó thực chất được xử lý qua lớp Shell trước:
- Vai trò của Shell: Shell là giao diện tương tác giữa người dùng và HĐH. Shell tiếp nhận thao tác click chuột, dịch yêu cầu của người dùng thành câu lệnh / lời gọi hệ thống.
- Lý do không tương tác trực tiếp với Kernel: Kernel là nhân hệ điều hành, làm việc trực tiếp ở mức phần cứng low-level và quản lý tài nguyên khắt khe => Nếu cho phép người dùng tương tác trực tiếp mà không qua Shell kiểm duyệt, chỉ một thao tác sai sót nhỏ cũng có thể làm sụp đổ toàn bộ hệ thống.
# Phần 2 — Cây thư mục & Ổ đĩa :
1. Dựa vào cây thư mục ở mục 3b: 
- D:\ là **Root Directory**
- Thư mục Hinh anh là **Parent Directory** trực tiếp của file anh 1.jpg
- File anh 1.jpg đóng vai trò là "lá" (Leaf)
2. **2 lý do kỹ thuật** đây là lựa chọn nguy hiểm và đề xuất nơi lưu đúng:
- Gây chậm máy / đầy ổ C:
- Nguy cơ mất dữ liệu khi cài lại Window
# Phần 3 — Đường dẫn Path :
1. **Absolute Path** đầy đủ: D:\Nam1\HocKy1\MonHoc\CongNgheThongTin\BaiTapLon\Session02\BaoCaoCuoiKy\Chuong1\Hinh anh\anh 1.jpg
2. **Relative Path**: 
./assets/logo.png
- Lý do dùng **Relative Path**: vì khi dùng đường dẫn tương đối sẽ giúp bất kì máy tính nào cũng có thể truy cập được qua đường dẫn đó mà không bị lỗi.
# Phần 4 — Quy tắc Đặt tên chuẩn :
- Tên chuẩn: bao-cao-bai-tap-lon-it101-ban-cuoi-v2.docx
# Phần 5 — Tổ chức & Dọn dẹp Ổ đĩa
- Đường dẫn ở mục 3b đang lồng 9 cấp thư mục
- Quy tắc đã vi phạm: Quy tắc 3 Cấp Thư mục
- Đường dẫn thư mục đúng: D:\01_HocTap\IT101_CongNgheThongTin\BaiTapLon\anh-1.jpg
# Phần 6 — Đuôi file & File ẩn
- Bản chất cạm bẫy: Đây là hình thức tấn công giả mạo đuôi file. Khi Windows đang ở chế độ mặc định ẩn đuôi file mở rộng, kẻ tấn công sẽ đặt tên file là de-thi-dap-an.pdf.exe. Máy tính chỉ hiển thị phần tên de-thi-dap-an.pdf khiến người dùng lầm tưởng đây là file tài liệu PDF an toàn, nhưng thực chất nó là một file thực thi mã độc (.exe).
- Các thao tác cụ thể nào trong Windows File Explorer giúp bạn phát hiện ra sự thật này trước khi nhấp đôi chuột mở file:
  - Mở cửa sổ File Explorer (phím tắt Windows + E).
  - Chọn tab View trên thanh menu trên cùng.
  - Chọn mục Show => Đánh dấu tích vào File name extensions.