# Demo Lỗ Hổng Reentrancy (Tấn công Tái nhập)

Dự án này được xây dựng để minh họa lỗ hổng bảo mật **Reentrancy** trong Smart Contract và cách khai thác nó. Dự án bao gồm Smart Contract (Solidity) và giao diện Web (Frontend) để tương tác.

## 📂 Cấu trúc dự án
- `contracts/VulnerableAuction.sol`: Contract chứa lỗ hổng (Nạn nhân).
- `contracts/Attack.sol`: Contract tấn công (Hacker).
- `index.html` & `app.js`: Giao diện web để demo tấn công.

## 🛠️ Yêu cầu cài đặt
- [Node.js](https://nodejs.org/)
- Ví MetaMask (đã cài trên trình duyệt)

## 🚀 Hướng dẫn chạy Demo

Để chạy dự án này, bạn cần mở **3 cửa sổ Terminal** (hoặc 3 tab terminal) riêng biệt:

### Bước 1: Khởi chạy mạng Local Blockchain
Tại Terminal 1, chạy lệnh:
npx hardhat node

### Bước 2: Deploy Smart Contract
Tại Terminal 2, chạy lệnh:
npx hardhat run scripts/deploy.js --network localhost

Lưu ý: Copy địa chỉ contract vừa deploy (hiện trên màn hình) nếu cần dán vào file js hoặc giao diện.

### Bước 3: Chạy giao diện Web
Tại Terminal 3, chạy lệnh để tạo server ảo:
npx http-server

Sau đó truy cập trình duyệt tại địa chỉ: http://127.0.0.1:8080

## 🧪 Kịch bản Demo

1. **Chuẩn bị:** Mở web, kết nối ví MetaMask (mạng Localhost 8545).
2. **Nạn nhân:** Sử dụng ví A, gửi tiền vào Contract (Deposit).
3. **Tấn công:** Sử dụng ví B (Hacker), kích hoạt hàm `attack()` trên giao diện.
4. **Kết quả:** Quan sát số dư của Contract nạn nhân về 0 và ví Hacker tăng lên bất thường.
