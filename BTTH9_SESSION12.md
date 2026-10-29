Phần 1 – Khung sườn README

# SmartCampus


Ứng dụng di động giúp sinh viên PTIT **tra cứu lịch học**, xem *phòng trống* và nhận thông báo mới nhất từ nhà trường.


![Logo SmartCampus](https://clblaptrinh.ptit.edu.vn/images/smartcampus-logo.png)


Dự án thuộc [CLB Lập trình PTIT](https://clblaptrinh.ptit.edu.vn).


## Tính năng đã hoàn thành


- Tra cứu lịch học theo mã sinh viên

- Nhập mã sinh viên để xem lịch học

- Xem danh sách phòng trống theo tòa nhà

- Lọc phòng trống theo từng tòa nhà


> **Cảnh báo:** Dự án đang trong giai đoạn phát triển, chưa dùng cho mục đích chính thức.


— Phần 2 – Phần kỹ thuật của README

## :rocket: Cài đặt nhanh


```bash

git clone https://github.com/clb-lap-trinh/smartcampus.git

npm install

npm start

```


## Tiến độ tính năng


- [x] Tra cứu lịch học theo mã sinh viên

- [x] Xem danh sách phòng trống theo tòa nhà

- [ ] Thông báo đẩy (push notification)

- [ ] Đăng nhập bằng tài khoản trường


## :package: Thư viện sử dụng


| Thư viện | Phiên bản | Mục đích |

|:---|:---:|:---|

| React Native | 0.74 | Xây giao diện đa nền tảng iOS/Android |

| Axios | 1.6 | Gọi API lấy dữ liệu lịch học |


## Lưu ý về ký tự đặc biệt


Muốn hiển thị dấu \* hoặc dấu \# nguyên văn, hãy gõ dấu gạch chéo ngược `\` ngay phía trước ký tự đó.

Phần 3 – Hỏi AI đúng cách và lưu tài liệu

Prompt theo Công thức 3 Phần: ## Tôi là ai / Bối cảnh - Tôi là sinh viên năm 1 PTIT, mới gia nhập nhóm dự án SmartCampus. - Tôi chưa có nền tảng lập trình và gặp thuật ngữ này trong tài liệu dự án.

## Chủ đề / Nội dung cần xử lý Giải thích thuật ngữ **API** (Application Programming Interface).

## Yêu cầu - Dùng ẩn dụ đời thường, so sánh với một tình huống quen thuộc. - Giải thích trong khoảng 100-150 từ. - Cho 1 ví dụ liên quan đến việc ứng dụng lấy lịch học từ máy chủ của trường. - Trình bày bằng Markdown có tiêu đề, chữ đậm và danh sách gạch đầu dòng.

## Không cần - Cấu trúc kỹ thuật chi tiết như HTTP, JSON, REST. - Ví dụ bằng ngôn ngữ lập trình.

Câu trả lời của AI: ### 🍽️ API Là Gì? **API** (Application Programming Interface, giao diện lập trình ứng dụng) giống như *người phục vụ trong nhà hàng*. Bạn (ứng dụng) không vào bếp (máy chủ) mà chỉ gọi món với người phục vụ. Người phục vụ mang yêu cầu vào bếp rồi bưng món ra cho bạn.


Ví dụ với ứng dụng SmartCampus: - **Bạn gọi món:** ứng dụng gửi mã sinh viên. - **Người phục vụ:** API chuyển yêu cầu đến máy chủ của trường. - **Món ăn:** lịch học được trả về và hiện trên màn hình điện thoại. > **Điểm mấu chốt:** API là cầu nối giúp hai phần mềm trao đổi dữ liệu mà không cần biết chi tiết bên trong của nhau.

Tóm tắt 3 câu: - API là cầu nối giúp một phần mềm gửi yêu cầu và nhận dữ liệu từ phần mềm khác, giống người phục vụ nhận món rồi mang từ bếp ra. Trong SmartCampus, ứng dụng gửi mã sinh viên qua API và nhận lại lịch học để hiển thị. Nhờ vậy ứng dụng không cần biết máy chủ của trường hoạt động bên trong ra sao.

Copy: - Soạn prompt chuẩn 3 phần (3.1). - Yêu cầu AI trả lời bằng Markdown (dòng cuối của mục ## Yêu cầu). - Copy câu trả lời, dán vào StackEdit, lưu thành api_giai_thich.md. - Tích lũy các file tương tự thành bộ từ điển công nghệ cá nhân Phần 4 – Bẫy cú pháp

1 Bảng thiếu dòng phân cách |---|---| ngay dưới dòng tiêu đề Parser không nhận là Table, cả khối hiện thành chữ thường kèm các dấu |

2 Task List thiếu dấu cách sau -: viết -[x], -[ ] Phải là - [x], - [ ]. Thiếu dấu cách thì không thành list item, không hiện checkbox

Đoạn đã sửa | Tính năng | Trạng thái | |:---|:---:| | Tra cứu lịch học | Xong | | Push notification | Đang làm |


- [x] Tra cứu lịch học

- [ ] Push notification