# Phân tích sự khác biệt cấu hình log giữa Dev và Prod

- **Môi trường Dev**
    - Mục đích: Giúp lập trình viên dễ dàng theo dõi luồng xử lý khi phát triển và debug.
    - Cấu hình: In log ra console, bật mức DEBUG để thấy chi tiết nhất.
    - Đặc điểm: Không cần lưu lâu dài, ưu tiên hiển thị trực tiếp.

- **Môi trường Prod**
    - Mục đích: Lưu giữ log để phân tích sự cố, giám sát hệ thống, tránh mất dữ liệu khi server restart.
    - Cấu hình: Ghi log ra file `app.log`, sử dụng RollingFileAppender để tự động cắt/nén khi vượt dung lượng.
    - Đặc điểm: Giới hạn dung lượng (10MB mỗi file), giữ tối đa 30 ngày, mức INFO để tránh “ngập rác”.
