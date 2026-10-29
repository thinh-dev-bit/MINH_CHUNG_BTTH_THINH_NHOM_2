# **Phần 1 – CLI vs GUI và cấu trúc câu lệnh**
1. Câu lệnh PowerShell:
- **Command**: ls
- **Options/Flags**:  -Force
- **Argument**: 1. C:\Windows\Logs
2. Lý do nhóm **bắt buộc phải dùng Terminal (PowerShell/SSH)** thay vì giao diện đồ họa để làm việc với máy chủ vì Terminal giúp tiết kiệm tài nguyên và tối ưu hiệu năng hơn giao diện đồ họa 
# **Phần 2 – Điều hướng hệ thống file**
3. Lệnh **Relative Path** : cd .\quan-ly-sinh-vien
4.  **Absolute Path** đầy đủ: C:\Users\student\Desktop\quan-ly-sinh-vien\src\main.py
5. **Lệnh PowerShell duy nhất** (không dùng cd trước) để xem toàn bộ nội dung — **kể cả file ẩn** — của thư mục data\: ls ..\data -Force
# **Phần 3 – Thao tác file và thư mục**
6. Lệnh PowerShell tạo cùng lúc 2 thư mục con `src` và `data` bên trong `quan-ly-sinh-vien`: mkdir quan-ly-sv\src, quan-ly-sv\data
7. Lệnh PowerShell tạo 3 file rỗng `main.py`, `utils.py` và `README.md` trong **cùng một dòng lệnh**: New-Item -ItemType File quan-ly-sinh-vien\src\main.py, quan-ly-sinh-vien\src\utils.py, quan-ly-sinh-vien\README.md
8. 
- Lệnh PowerShell để **đổi tên lại cho đúng**: mv quan-ly-sv quan-ly-sinh-vien
- Lệnh để **sao lưu toàn bộ** thư mục project (đã đổi tên) thành bản backup `backup-quan-ly-sinh-vien`: cp quan-ly-sinh-vien backup-quan-ly-sinh-vien -Recurse
# **Phần 4 – Xử lý lỗi Terminal**
9.  **Log lỗi số 2** (mục 3d), chẩn đoán: đây có khả năng là lỗi gõ sai tên thư mục: nhầm src thành scr
- Kiểm tra bằng phím Tab: Gõ cd s rồi nhấn Tab. Nếu thư mục tồn tại, PowerShell tự điền thành cd .\src
10. **Log lỗi số 3** (mục 3e), chẩn đoán nguyên nhân: Lỗi Access is denied do chính sách bảo mật thực thi script của Windows PowerShell mặc định đang ở trạng thái Restricted (chặn chạy các file .ps1 chưa được cấp phép).
- Cách khắc phục: Mở PowerShell dưới quyền Quản trị viên (Run as Administrator).
11. **Log lỗi số 1** (mục 3c), chẩn đoán: Thư mục old-version chứa các file/thư mục con bên trong, do lệnh rm mặc định không tự động xóa đệ quy để tránh người dùng vô tình xóa nhầm dữ liệu quan trọng nên PowerShell đưa ra bảng hỏi xác nhận.
- Lệnh PowerShell đúng: rm old-version -Recurse -Force
12. **Log lỗi số 4** (mục 3f):

| Trái | Giữa | 
|:-----:|:----:|
| (a) Dòng chứa thông điệp lỗi trực tiếp nhất  |  FileNotFoundError: [Errno 2] No such file or directory: 'data/input.csv'   | 
| (b) Từ khóa lỗi (Error Keyword)  | FileNotFoundError / No such file or directory   | 
| (c) Điều cần kiểm tra tiếp để sửa lỗi | Vị trí đang đứng là ...\quan-ly-sinh-vien\src, trong khi đường dẫn data/input.csv trong code (main.py) là đường dẫn tương đối, được tính từ thư mục hiện tại. Từ src thì không có src\data\input.csv; file thật nằm ở ..\data\input.csv.| 

