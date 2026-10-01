## 1. Mô tả

Sửa lỗi chương trình quản lý hàng đợi xe sạc và tính tổng sản lượng điện, doanh thu của trạm sạc

## 2. Các lỗi và cách khắc phục

- **Lỗi 1:** Sử dụng `pop()` lấy xe cuối hàng đợi, không đúng nguyên tắc FIFO.
  **Sửa:** Dùng `shift()` để lấy xe đầu tiên
- **Lỗi 2:** Sử dụng điều kiện `i <= completedSessionsKwh.length` khiến vòng lặp truy cập phần tử không tồn tại, dẫn đến kết quả `NaN`.
  **Sửa:** Dùng `i < completedSessionsKwh.length`

## 3. Kiểm thử

| Trường hợp | Dữ liệu                    | Kết quả mong đợi         |
| ---------- | -------------------------- | ------------------------ |
| TC01       | Hàng đợi có 3 xe           | Lấy xe `29A-112.33`      |
| TC02       | `[45.2, 30.5, 62.8, 28.0]` | Tổng: `166.5 kWh`        |
| TC03       | `166.5 × 4500`             | Doanh thu: `749.250 VNĐ` |
| TC04       | Hàng đợi rỗng              | Thông báo không có xe    |

## 4. Kết luận

Chương trình sau khi sửa đã lấy xe đúng thứ tự FIFO, tính chính xác tổng sản lượng điện và doanh thu
