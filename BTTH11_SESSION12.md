# **Phần 1 – Hoàn thiện SRS bằng Heading Styles và Auto TOC**
## Mở rộng khung tiêu đề vaf gán đúng cấp Heading:
1. Giới thiệu dự án (Heading 1)
- 1.1. Mục tiêu (Heading 2)
- 1.2. Đối tượng sử dụng (Heading 2)
2. Chức năng hệ thống (Heading 1)
- 2.1. Quản lý mượn sách (Heading 2)
   -  2.1.1. Luồng mượn sách qua thẻ sinh viên (Heading 3)
- 2.2. Quản lý trả sách (Heading 2)
3. Yêu cầu bảo mật (Heading 1)
## Mội dung mô tả:
- 2 câu mô tả chức năng hệ thống:
  - Hệ thống cho phép nhân viên thư viện tìm kiếm thông tin sách, ghi nhận thông tin mượn/trả và tự động tính toán ngày quá hạn. Ngoài ra, sinh viên có thể đăng nhập portal để tra cứu danh mục sách và đăng ký mượn trực tuyến.
-  2 câu mô tả **Yêu cầu phi chức năng**:
  - Mọi thông tin mật khẩu của người dùng phải được mã hóa chuẩn bcrypt trước khi lưu trữ vào cơ sở dữ liệu. Hệ thống phải đảm bảo phân quyền chặt chẽ, chỉ có tài khoản Thủ thư mới có quyền thực hiện các thao tác thêm, sửa, xóa dữ liệu mượn trả sách
## Chèn **Auto TOC** ở đầu tài liệu
- Đặt con trỏ soạn thảo ở trang đầu tiên của tài liệu.
- Vào thẻ References => chọn Table of Contents => chọn mẫu Automatic Table 1 (hoặc Automatic Table 2) để tự động sinh mục lục từ các thẻ Heading.
- Chèn một đoạn văn bản hoặc bấm Ctrl + Enter (Page Break) để đẩy mục 3. Yêu cầu bảo mật sang trang tiếp theo.
- Nhấp chuột phải vào bảng mục lục => chọn Update Field => tích chọn Update entire table => bấm OK. Mục lục sẽ tự động cập nhật lại đúng số trang mới mà không cần sửa tay.
# **Phần 2 – Chuẩn hóa dữ liệu và AutoFilter**
1. 3 lỗi vi phạm 5 Quy tắc Vàng:

| Lỗi | Vị trí | Quy tắc bị vi phạm |
|----|-----|------|
|Merge các ô A1:E1 thành một ô lớn chứa tiêu đề "DANH SÁCH MƯỢN SÁCH THÁNG 10"|Hàng 1|Không gộp ô (Merge Cells) trong hoặc trên vùng tiêu đề dữ liệu|
|Để trống hoàn toàn nguyên một hàng giữa các bản ghi|Hàng 5|Không chứa hàng trống trong vùng dữ liệu|
|Chèn dòng tính tổng nằm xen kẽ giữa các hàng dữ liệu|Hàng 6|Không chèn dòng tổng cộng/tóm tắt nằm bên trong vùng dữ liệu|
2. Bảng đã sửa đúng chuẩn:

|MSSV|Họ Tên|Mã Sách|Ngày Mượn|Tình Trạng|
|----|----|----|----|----|
|SV001|Nguyễn Văn An|S001|01/10/2026|Đang mượn|
|SV002|Trần Thị Bình|S002|03/10/2026|Quá hạn|
|SV003|Lê Văn Cường|S003|10/10/2026|Đã trả|
|SV004|Phạm Thu Hà|S099|12/10/2026|Đang mượn|
3. 
- 1 Record (Bản ghi / Hàng): Là toàn bộ thông tin của 1 lượt mượn sách. Ví dụ: Dòng 2 chứa Record: SV001 | Nguyễn Văn An | S001 | 01/10/2026 | Đang mượn.
- 1 Field (Trường / Cột): Là một thuộc tính dữ liệu cụ thể của đối tượng. Ví dụ: Cột Mã Sách chứa tập hợp mã các cuốn sách được mượn.
4. Thao tác bật **AutoFilter** (`Ctrl+Shift+L`) và lọc ra danh sách sinh viên có Tình trạng = "Quá hạn": 
- Đặt con trỏ chuột vào bất kỳ ô nào bên trong bảng dữ liệu đã sửa.
- Nhấn tổ hợp phím tắt Ctrl + Shift + L (hoặc vào Data => bấm chọn nút Filter). Các mũi tên xổ xuống sẽ xuất hiện tại hàng Tiêu đề (Hàng 1).
- Nhấp vào nút mũi tên xổ xuống ở tiêu đề cột Tình Trạng.
- Bỏ tích (Select All), đánh dấu tích duy nhất vào ô Quá hạn =. bấm OK. Excel sẽ ẩn các dòng khác và chỉ hiển thị sinh viên SV002 - Trần Thị Bình.
# **Phần 3 – Nối dữ liệu bằng VLOOKUP**
- Công thức VLOOKUP tra cứu Tên Sách
  - Giả sử bảng DanhMucSach ở sheet DanhMucSach nằm trong vùng A2:C4 (Cột A: Mã Sách, Cột B: Tên Sách, Cột C: Thể Loai):
  - Tại ô F2 (cột Tên Sách) của bảng Phiếu mượn, nhập công thức: =VLOOKUP(C2, DanhMucSach!$A$2:$C$4, 2, FALSE)
- Lỗi trả về: #N/A (Not Available).
  - Nguyên nhân: Mã sách S099 không tồn tại trong danh mục tra cứu ở sheet DanhMucSach (cột Lookup_value không tìm thấy giá trị trùng khớp chính xác trong cột đầu tiên của Table_array).
- Công thức có bọc thêm `IFERROR` để dòng đó hiển thị **"Không tìm thấy sách"** thay vì lỗi: =IFERROR(VLOOKUP(C2, DanhMucSach!$A$2:$C$4, 2, FALSE), "Không tìm thấy sách")
# **Phần 4 – Slide báo cáo tiến độ**
1. 
- Assertion Title (Tiêu đề kết luận): Tỷ lệ trả sách đúng hạn đạt 75%, ghi nhận 25% phiếu mượn rơi vào trạng thái quá hạn cần xử lý.
- 1 con số hoặc kết luận nổi bật đặt ở **Content Area**:
  - Con số nổi bật (Big Number): 25% (Quá hạn)
  - Biểu đồ lựa chọn: Biểu đồ Tròn / Vành khuyên (Donut Chart).
- Chọn biểu đồ **Donut / Flowchart** để minh họa số sách mượn theo tình trạng:
  - Lý do chọn Biểu đồ Donut: Biểu đồ Donut thể hiện trực quan tỷ lệ phần trăm các thành phần so với tổng thể (100% tổng số phiếu mượn = Đang mượn + Đã trả + Quá hạn), giúp người xem ngay lập tức thấy được tỷ trọng các trạng thái mượn trả sách trong tháng 10.
- Quy tắc Rule 10/20/30:
  - Rule 10/20/30: 10 Slide – 20 Phút trình bày – Cỡ chữ tối thiểu 30pt.
- Tỷ lệ slide này:
  - Đây là 1 slide trong tổng số 10 slide của toàn bộ bài báo cáo đồ án.
  - Thời lượng trình bày dự kiến cho slide này là 2 phút (trên tổng số 20 phút trình bày toàn bài).