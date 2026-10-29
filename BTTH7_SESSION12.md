# **Phần 1 – Đọc và định vị tệp tin**
1. Lệnh PowerShell in toàn bộ nội dung file `logs\server.log` ra màn hình: Get-Content logs\server.log
2. Lý do mở file 500MB bằng **Notepad** (double-click) có nguy cơ làm treo máy, trong khi đọc bằng **Terminal PowerShell** lại mượt mà: Notepad: Mở file bằng cách nạp toàn bộ 500 MB dữ liệu của file vào RAM cùng một lúc để dựng giao diện hiển thị văn bản; Terminal PowerShell: Đọc dữ liệu theo dạng luồng tức là đọc và đẩy từng dòng dữ liệu ra màn hình rồi giải phóng bộ nhớ liên tục => giúp tiết kiệm tối đa dung lượng RAM và đảm bảo hệ thống vận hành mượt mà.
3. **ệnh PowerShell duy nhất** tìm tất cả file đuôi `.log`: Get-ChildItem -Path . -Filter *.log -Recurse
# **Phần 2 – Lọc dữ liệu và Pipe**
4. ệnh PowerShell lọc ra các dòng chứa chữ `ERROR`: Select-String -Path logs\server.log -Pattern "ERROR"
5. 

| Câu hỏi | TLệnh PowerShell |
|-----|------|
| "File server.log đang nằm ở thư mục nào?"  | Get-ChildItem -Recurse -Filter server.log  |
| "Bên trong file này có dòng nào chứa lỗi 404 không?" | Select-String -Path .\logs\server.log -Pattern "404"
- Lệnh kết hợp **Pipe**: Get-Content logs\server.log | Select-String -Pattern "404"
6. **Lệnh PowerShell duy nhất** để: tìm đệ quy tất cả file `.log` trong `devops-lab`, rồi trong các file đó lọc ra những dòng **không chứa** chữ `INFO`: Get-ChildItem -Recurse -Filter *.log | Select-String -Pattern "INFO" -NotMatch
# **Phần 3 –** Toán tử chuyển hướng `>` và `>>`
7. Lệnh hoàn chỉnh: đọc `logs\server.log`, lọc các dòng chứa `404`, và **ghi đè** kết quả vào `reports\daily_report.txt`: Get-Content .\logs\server.log | Select-String -Pattern "404" > .\reports\daily_report.txt
8. 30 phút sau hệ thống phát sinh thêm một lỗi 404 mới.
- Lệnh **thêm dòng lỗi mới vào cuối** `reports\daily_report.txt` mà **không làm mất** báo cáo cũ: Get-Content .\logs\server.log | Select-String -Pattern "404" >> .\reports\daily_report.txt
- Nếu dùng nhầm toán tử > (ghi đè): Toàn bộ nội dung báo cáo cũ đã được ghi trước đó trong file reports\daily_report.txt sẽ bị xóa sạch hoàn toàn và thay thế bằng kết quả mới thu được.
# **Phần 4 – Shell Script và lệnh `echo`**
9. Viết lệnh dùng `Write-Output` (hoặc `echo`) để:
- In thông báo tiến trình: Write-Output "Dang loc log..."
- Lệnh ghi dòng tiêu đề `=== LOG REPORT ===` làm **dòng đầu tiên** của `reports\daily_report.txt`: Write-Output "=== LOG REPORT ===" > .\reports\daily_report.txt
10. Nội dung file `scripts\auto_report.ps1`:
# Script tu dong doc log server, loc ra cac dong loi 404 va xuat bao cao hang ngay vao reports\daily_report.txt
- Write-Output "Dang bat dau quy trinh trich xuat log loi 404..."
- Write-Output "=== LOG REPORT ===" > .\reports\daily_report.txt
- Get-Content .\logs\server.log | Select-String -Pattern "404" >> .\reports\daily_report.txt
# **Phần 5 – Viết, chạy và thẩm định Script AI**
11. **Quy trình 3 bước thực thi Script** cho file `scripts\auto_report.ps1`: 
- (a) Lệnh thực thi file script: .\scripts\auto_report.ps1
- (b) Lệnh kiểm tra nội dung file báo cáo đã được tạo: Get-Content .\reports\daily_report.txt
12. **3 Nguyên tắc Vàng thẩm định Script AI**:
- (a) Dòng lệnh nguy hiểm & Hậu quả:
   - Dòng lệnh nguy hiểm: Remove-Item -Recurse -Force C:\*
   - Hậu quả: Cờ -Recurse (xóa đệ quy) và -Force (xóa bắt buộc không hỏi) kết hợp với đường dẫn C:\* sẽ xóa toàn bộ hệ điều hành Windows, phần mềm và toàn bộ dữ liệu trên ổ C:, khiến máy tính ngay lập tức bị sụp đổ 
- Sửa lại đường dẫn: Remove-Item -Recurse -Force .\temp\*