# Nguyễn Lam Sơn_K225480106076
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
## XÂY DỰNG FLOW TRÊN N8N (CHI TIẾT 4 NODE)
khi vào đăng ký tài khoản ( lưu ý nhập đúng mk maill để lấy mã key )
## <img width="1887" height="1024" alt="image" src="https://github.com/user-attachments/assets/65a6c277-ef66-4efd-a6c5-09b9501cd199" />
active vào n8n
## <img width="1919" height="1026" alt="image" src="https://github.com/user-attachments/assets/bfe45598-83c2-4d60-9655-2713f112613e" />
# Node 1: Telegram Trigger (Nhận tin nhắn)
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
# Node 2: Google Gemini (Xử lý nội dung)
cấu hình google genmini 
Bấm dấu + nối tiếp sau Telegram Trigger -> Tìm chọn Google Gemini (hoặc chọn node Advanced AI -> Chain rồi kéo model Gemini vào tùy phiên bản, hoặc node Google Gemini / Message a model).

Tại mục Credential, dán cái Google AI Studio API Key đã tạo vào
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/312e8f3e-f3f4-40c6-a7c2-ba675e58967b" />
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b0747658-352c-443b-be75-13dc0fc10c7e" />
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c3a768b0-e7f8-4450-92f8-508c0d845cc1" />
Tại ô Prompt / Text:

Đầu tiên, bạn kéo thả nội dung tin nhắn chat từ Telegram vào để có chuỗi: {{ $json.message.text }}. 

Ngay sau dấu ngoặc nhọn đó, bạn gõ thêm chính xác cụm từ yêu cầu định dạng HTML+CSS của đề bài vào:  Plaintext{{ $json.message.text }}. Kết quả sinh ra ở định dạng HTML+CSS để tôi dùng HTML+CSS này tạo bài viết cho wordpress.

Bật chế độ định dạng JSON
nhìn xuống phía dưới cấu hình node, tìm dòng chữ Output Content as JSON. 

Gạt công tắc sang màu xanh (TURN ON) để ép con AI bắt buộc phải trả về dữ liệu đóng gói dạng chuỗi JSON cấu trúc. 

Cấu hình System Message (Mẹo giải quyết yêu cầu mở rộng của đề bài): Đề bài có câu hỏi: "Có thể thử nghiệm thêm thuộc tính System message... => đưa ra cái nào đáng dùng?". Để node JavaScript tiếp theo không bị lỗi, bạn cần dùng System Message để ép Gemini trả về đúng tên trường dữ liệu.

Bấm vào nút Add Option ở cuối node Gemini -> Chọn System message.  Nhập nội dung này vào ô System message:Plaintext Bạn là trợ lý viết bài blog. Hãy trả về một chuỗi JSON chuẩn có cấu trúc chính xác gồm 2 key là "post_title" và "post_content". Trong đó "post_content" phải chứa toàn bộ nội dung bài viết đã được định dạng bằng các thẻ HTML và CSS.
# bấm execu step để ra out put
## <img width="1919" height="982" alt="image" src="https://github.com/user-attachments/assets/410f9316-6589-49c3-a599-21cb46ae4ede" />
# Node 3: cấu hình code in JavaScrip
## // 1. Lấy dữ liệu text từ Node Gemini trả về
let rawText = $input.first().json.content.parts[0].text;

// 2. Dọn dẹp các ký tự rác (nếu AI có lỡ chèn thêm ```json hoặc ```html)
rawText = rawText.replace(/```json/g, "").replace(/```html/g, "").replace(/```/g, "").trim();

// 3. Chuyển chữ thành dữ liệu JSON chuẩn
let data = JSON.parse(rawText);

// 4. Đề phòng trường hợp AI trả về một danh sách (Array), ta lấy bài đầu tiên
if (Array.isArray(data)) {
    data = data[0];
}

// 5. Xuất dữ liệu ra cho WordPress
return {
    title: data.title,
    content: data.html_content || data.content
};

## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/378ad7a8-1d52-4152-a76b-8b220adb9e8f" />
kết quẩ tra về 
## <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fa4454df-5905-4fff-90b1-d1a9840fe28b" />
# Node 4: WordPress => Create a Post
cấu hình: Credential
## <img width="1339" height="729" alt="image" src="https://github.com/user-attachments/assets/719ee7e0-d405-4092-b2b7-6b674884895e" />
mục Username: tk wordPess của mình 
passwword: truy cập trang chủ wordpess
vào mục tài khoạn chọn người dùng ( Admin )
## <img width="1917" height="1024" alt="image" src="https://github.com/user-attachments/assets/2b439189-7d64-49a8-9b83-37745d94e104" />
thêm mật khẩu ứng dụg mới :n8n <br>
sau khi thêm có 1 dải chuỗi 24 số đó là passwword copy r dán vào node đang cấu hình <br>
Thêm Url: https://btvn3wordpress.nlamson1301.id.vn <br>
## <img width="1025" height="346" alt="image" src="https://github.com/user-attachments/assets/0c6139c6-48ee-4a4d-91b3-9b069a9ab72d" />
sau đó cấu hình bên ngoài kéo các tile và conten vào 
## <img width="537" height="832" alt="image" src="https://github.com/user-attachments/assets/8537eba4-42f0-4791-8fc5-bf10509b022d" />
# Kết quả trả về
## <img width="1863" height="867" alt="image" src="https://github.com/user-attachments/assets/1243f54c-3bfe-49d4-9e76-5f7f87d4ef6b" />
# kết quả:
## <img width="1919" height="1029" alt="image" src="https://github.com/user-attachments/assets/97adaaa5-05de-4328-bd98-b4465ee22210" />
## <img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/b38f1860-22c6-4149-a874-bb7a8d64c76d" />
## <img width="1317" height="321" alt="image" src="https://github.com/user-attachments/assets/169995d8-1fd1-41bb-b8e5-4d0c6cec20af" />






