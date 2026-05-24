# nguyễn lam sơn_K225480106076
## Bài tập 4 môn Phát triển ứng dụng với mã nguồn mở
# Khai thác N8N để tự động đăng bài lên WordPress
# bước 1: tạo folder và truy cập
mkdir btapvenha4
cd btapvenha4
tạo file cấu hình:
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c4441dd4-e59c-4228-aa41-db42fac99df1" />
# Bước 2: Khởi chạy hệ thống
sudo docker-compose up -d
## <img width="1104" height="575" alt="image" src="https://github.com/user-attachments/assets/7f813059-08dd-43b8-810a-cbb214c7e902" />
Kiểm tra trạng thái các Services đang chạy
sudo docker compose ps
## <img width="1095" height="284" alt="image" src="https://github.com/user-attachments/assets/9123abf6-d867-40d3-a47b-9da9435dd98d" />
# Bước 3: Cấu hình Cloudflare Tunnel để Public ra Internet
## <img width="1260" height="480" alt="image" src="https://github.com/user-attachments/assets/224c2b90-469c-467f-9deb-14815b2e9e85" />
# Bước 4: Cài đặt WordPress và đăng bài thủ công
1. Kiểm tra DB ban đầu: Truy cập https://pma.nlamson1301.id.vn
## <img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/a356f225-c116-436d-80ae-0c4351c48462" />
2. Cài đặt WP: Truy cập https://wp.nlamson1301.id.vn để tiến hành cài đặt WordPress. Ở phần tạo tài khoản quản trị cho trang web
## <img width="1919" height="1029" alt="image" src="https://github.com/user-attachments/assets/1d4bf01e-39c5-430e-b605-19387792026a" />
3. Kiểm tra lại DB: Cài xong WordPress, quay lại tab phpMyAdmin
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b95d3196-0800-4f5b-8510-f530868bb920" />
Đăng bài thủ công: Đăng nhập vào WordPress (wp.nlamson1301.id.vn/wp-admin) và tạo mới 2 bài viết: <br>
Bài 1: Giới thiệu thông tin cá nhân, sở thích của bạn (có thể thêm ảnh/video tùy ý). <br>
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e42a7606-5e3a-4524-852f-c1b6d8c28574" />
Bài 2: Giới thiệu các kiến thức bạn đã học được ở môn Phát triển ứng dụng với mã nguồn mở.  <br>
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cd776305-36a1-49eb-bfb8-7acc73022382" />
## <img width="1579" height="961" alt="image" src="https://github.com/user-attachments/assets/2ee740eb-e1ec-4d58-989c-1c6cb89b21d5" />
# Bước 5: Kích hoạt N8N
khi vào đăng ký tài khoản ( lưu ý nhập đúng mk maill để lấy mã key )
# Tạo Workflow tự động hóa.
Bước 1: Tạo Node 1 - Telegram Trigger <br>
Trong danh sách hiện ra, chọn On new message (hoặc OnMessage <br> 
## <img width="221" height="54" alt="image" src="https://github.com/user-attachments/assets/de2e95b9-61ec-48fc-9f7b-2c572bbe929b" />
bước 2: Cấu hình Credential (mã kết nối)
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5f89ba9d-7db4-47fa-aad0-24d78ae48d30" />
Lấy Access Token từ Telegram <br>
Mở ứng dụng Telegram trên điện thoại hoặc máy tính của bạn lên. <br>

Trên thanh tìm kiếm, gõ chính xác: @BotFather (chọn tài khoản có dấu tích xanh chính chủ nhé). <br>
Bấm Start rồi gõ lệnh: /newbot và ấn gửi. <br>
@BotFather sẽ bảo bạn đặt tên cho Bot (Tên hiển thị) -> Bạn gõ tên bất kỳ (Ví dụ: LamSon AI Bot) rồi gửi. <br>

Tiếp theo, @BotFather yêu cầu tạo Username (tên định danh) cho Bot -> Bạn nhập tên viết liền không dấu, phải kết thúc bằng chữ bot nguyenlamson_ai_bot <br>
Sau khi tạo xong, @BotFather sẽ gửi cho bạn một đoạn tin nhắn dài, trong đó có một chuỗi ký tự loằng ngoằng nửa số nửa chữ (Ví dụ dạng: 739485028:AAH_GxF...). Đó chính là Access Token. Bạn hãy chạm hoặc click vào chuỗi đó để Copy. <br>
bước 3: Mồi dữ liệu và Test thử <br>

Trên Telegram, bạn tìm đúng cái tên Username con bot bạn vừa tạo ( @nguyenlamson_ai_bot ), bấm Start (hoặc /start). <br?
Nhắn cho con bot của bạn một tin nhắn bất kỳ, ví dụ gõ: "Bài test số 1" rồi ấn gửi. <br>
Quay lại giao diện n8n, nhìn sang cột bên phải (chỗ vùng màu xám có chữ No trigger output ấy), bấm vào nút màu cam Test this trigger (hoặc Listen for test event) <br>
# kết quả trả về 
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5b85bc25-fbbf-4fa2-89da-a6fbb612334a" />
