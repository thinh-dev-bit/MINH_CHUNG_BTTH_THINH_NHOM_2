# **Phần 1 – Lĩnh vực CNTT và đơn vị lưu trữ**
1. Ngân sách chỉ đủ tuyển 1 người nên chọn ứng viên B
- Vì Cyber Arena là trung tâm cho thuê máy chơi game và livestream, nên điều quan trọng nhất là máy chạy ổn định và mạng không bị gián đoạn do đó hiện tại cần một người vận hành hệ thống phần cứng, lắp ráp máy tính, xử lý sự cố mạng ổn định cho khách chơi game và livestream. Việc tự viết phần mềm đặt lịch chưa thực sự cấp thiết vì có thể dùng các giải pháp quản lý phòng máy có sẵn trên thị trường.
2. Sắp xếp các đơn vị sau theo thứ tự **tăng dần**: Byte > KB > MB > GB > TB
# **Phần 2 – Mô hình IPO và lĩnh vực CNTT**
1. **Hệ thống quay lại** và **xem lại trận đấu** hoạt động theo ***mô hình IPO**

| Thành phần |Trong hệ thống quay/xem lại trận đấu |
|-----|------|
|Input | Tín hiệu hình ảnh/âm thanh từ màn hình chơi game và camera/micro   |
|Process | CPU/GPU mã hóa (encode) và xử lý dữ liệu video thô thành file MP4 |
|Output|Video phát trực tiếp trên màn hình livestream (YouTube) hoặc phát lại cho đội tuyển xem|
|Storage|Ổ cứng SSD/HDD lưu trữ các file video trận đấu (khoảng 500 MB/file)|
2. Hoạt động của **Cyber Arena** (livestream, quay video, xem lại phân tích) gắn với lĩnh vực CNTT: 
- Mạng máy tính: Đảm bảo đường truyền internet ổn định để truyền tải dòng video livestream lên nền tảng YouTube.
- Quản trị hệ thống / Phần cứng: Quản lý, tối ưu hóa hiệu năng của CPU, RAM và ổ cứng để máy vừa chơi game vừa ghi hình mượt mà.
# **Phần 3 – Tính toán dung lượng và tốc độ mạng**
1. **Tính dung lượng lưu trữ:**
- 20 trận × 500 MB =10000 MB
- Đổi kết quả sang GB: 10000 MB = 9.77 GB
- Ổ SSD 512 GB chứa đủ video của 1 tháng. Sau 1 tháng đầu tiên vận hành ổ còn trống 512 - 9.77 = 502,23 GB
2. **Tính tốc độ mạng:**
- Mạng 100 Mbps tương đương tối đa 12.5 MB/s
- Với tốc độ đó, tải lên (upload) 1 đoạn video 200 MB mất tối thiểu 16 giây
- Lý do thực tế thường lâu hơn con số tính được vì 100 Mbps là tốc độ tối đa lý thuyết; thực tế đường truyền bị chia sẻ với nhiều máy khác trong trung tâm, nhiễu, hoặc máy chủ YouTube nhận chậm nên tốc độ thực thấp hơn.
# **Phần 4 – Phần cứng và mô hình DIKW**
1. Máy bị giật khi vừa **chơi game** vừa **quay video livestream** => Lựa chọn nâng cấp: CPU vì việc vừa chơi game vừa quay/livestream đòi hỏi máy tính phải xử lý đồng thời hai tác vụ rất nặng là tính toán logic game và mã hóa video (encoding). 16 GB RAM hiện tại đã đủ dung lượng cho game Liên Minh Huyền Thoại và phần mềm quay hình, trong khi CPU quá tải sẽ gây ra tình trạng nghẽn cổ chai dẫn đến giật lag.
2. Áp mô hình **DIKW**

| Tầng  |Nội dung trong tình huống | Vì sao thuộc tầng này? |
|-----|-----|-----|
| Data | Các đoạn video | Là dữ liệu thô, rời rạc, chưa được xử lý hay giải thích |
| Information | Tuyển thủ hay chết ở khoảng thời gian phút 15–20. | Dữ liệu đã được tổng hợp, sắp xếp thành thông tin có ý nghĩa |
| Knowledge | Nguyên nhân là do thiếu tầm nhìn bản đồ | Hiểu được mối quan hệ nguyên nhân – kết quả từ thông tin đã thu thập |
| Wisdom | Yêu cầu tuyển thủ mua thêm mắt (Ward) cho các trận đấu sau | Đưa ra quyết định/hành động chiến lược đúng đắn để giải quyết vấn đề |
