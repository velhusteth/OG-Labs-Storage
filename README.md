# 🤖 0G Storage Auto Bot

### ✨ Tính năng chính

- 🔑 **Hỗ trợ đa ví**: Chạy tác vụ trên nhiều private key tuần tự
- 🌐 **Tích hợp proxy**: Sử dụng proxy xoay vòng để tránh giới hạn tốc độ
- 🔄 **Xoay vòng User-Agent**: Tự động thay đổi user agent cho mỗi request
- 📊 **Thống kê chi tiết**: Theo dõi các hoạt động thành công và thất bại
- 📝 **Lịch sử giao dịch**: Lưu tất cả chi tiết giao dịch để tham khảo sau này
- ⚡ **Xử lý lỗi thông minh**: Tự động xử lý lỗi rate limit và retry

## 🚀 Cài đặt

### Yêu cầu hệ thống

- Node.js 18+ 
- NPM hoặc Yarn
- Kết nối internet ổn định

### Bước cài đặt

```bash
# Clone repository
git clone https://github.com/vikitoshi/0g-Storage-Auto-Bot.git

# Di chuyển vào thư mục
cd 0g-Storage-Auto-Bot

# Cài đặt dependencies
npm install
```

## ⚙️ Cấu hình

### 1. Cấu hình Private Keys

Tạo file `.env` trong thư mục gốc với private keys của bạn:

```env
# Cho một ví
PRIVATE_KEY=your_private_key_here

# HOẶC cho nhiều ví
PRIVATE_KEY_1=your_first_private_key
PRIVATE_KEY_2=your_second_private_key
PRIVATE_KEY_3=your_third_private_key
```

### 2. Cấu hình Proxy (Tùy chọn)

Tạo file `proxies.txt` với một proxy trên mỗi dòng:

```txt
http://username:password@ip:port
http://ip:port
socks5://username:password@ip:port
```

## 🎯 Cách sử dụng

### Chạy bot

```bash
node index.js
```

Khi được nhắc, nhập số lượng file bạn muốn tải lên cho mỗi ví.

### Ví dụ sử dụng

```bash
$ node index.js

--------------------------------------------
 0G Storage Scan Auto Bot - Airdrop Insiders
--------------------------------------------

[✅] Loaded 2 private key(s)
[⚠] No proxies found in proxies.txt
[⟳] Checking network status...
[✅] Connected to network: chainId 16601
[⟳] Checking network sync...
[✅] Network synced at block 2586143

Available wallets:
[1] 0xCA2f0C5aEf4Df89a90DCb52561B5c7BbFF01A817
[2] 0x1234567890abcdef1234567890abcdef12345678

How many files to upload per wallet? 10
[✓] Starting 20 uploads (10 per wallet)
```

## 🔧 Cách hoạt động

### Quy trình hoạt động

1. **Khởi tạo**: Bot tải private keys và proxies
2. **Kiểm tra mạng**: Xác minh kết nối với Galileo Testnet
3. **Xử lý từng ví**:
   - Tải ảnh ngẫu nhiên từ internet
   - Tính toán hash và chuẩn bị dữ liệu
   - Tải lên file segments lên 0G indexer
   - Gửi giao dịch blockchain để đăng ký upload
   - Chờ xác nhận trước khi tiếp tục upload tiếp theo
4. **Lưu kết quả**: Lưu tất cả thông tin vào thư mục `results`

### Cơ chế xử lý lỗi

- **Rate Limiting**: Tự động phát hiện và xử lý lỗi giới hạn tốc độ
- **Retry Logic**: Thử lại tối đa 3 lần với thời gian chờ tăng dần
- **Balance Check**: Kiểm tra số dư trước khi thực hiện giao dịch
- **Network Sync**: Đảm bảo mạng đã đồng bộ trước khi bắt đầu

## 🛠️ Xử lý sự cố

### Lỗi thường gặp

| Lỗi | Nguyên nhân | Giải pháp |
|-----|-------------|-----------|
| **Gas Errors** | Thiếu token testnet | Đảm bảo ví có đủ 0G testnet tokens |
| **Network Issues** | Kết nối mạng không ổn định | Kiểm tra kết nối internet hoặc dùng proxy |
| **RPC Errors** | RPC testnet quá tải | Thử lại sau hoặc tăng thời gian chờ |
| **Rate Limit** | Gửi request quá nhanh | Bot tự động xử lý, hoặc dùng proxy |

### Tối ưu hiệu suất

- Sử dụng proxy để tránh rate limiting
- Không chạy quá nhiều instance cùng lúc
- Đảm bảo kết nối mạng ổn định

## 📊 Thống kê

Bot auto:

- Số lượng upload thành công/thất bại
- Hash của từng file đã upload
- Link explorer cho mỗi giao dịch
- Thời gian thực hiện
- Chi phí gas sử dụng


### Liên hệ

- **Telegram**: [@Velhust](https://t.me/velhust0x)
- **Twitter**: [0xVelhust](https://x.com/0xVelhust)

---

<div align="center">

**⭐ Nếu dự án này hữu ích, hãy cho chúng tôi một ngôi sao! ⭐**

</div>

