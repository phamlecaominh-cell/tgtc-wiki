# Thế Giới Thống Chế Wiki

Wiki canon cho tiểu thuyết **Thế Giới Thống Chế**, xây dựng bằng HTML, CSS và JavaScript thuần.

## Cấu trúc

```text
tgtc-wiki/
├── index.html
├── data/
│   ├── wiki.json
│   └── chapters.json
├── README.md
└── .gitignore
```

- `data/wiki.json`: nguồn canon mặc định cho hồ sơ wiki.
- `data/chapters.json`: nguồn canon mặc định cho chương truyện.
- `tgtc_database_v1`: database chỉnh sửa cục bộ trong `localStorage`.

Nếu `tgtc_database_v1` hợp lệ, ứng dụng ưu tiên dữ liệu cục bộ. Nếu chưa có database cục bộ, ứng dụng tải seed canon từ thư mục `data/`. Nút Reset luôn tạo bản backup trong ô Export trước khi khôi phục seed canon.

## Chạy thử cục bộ

Không mở trực tiếp `index.html` bằng đường dẫn `file://`, vì trình duyệt có thể chặn việc tải JSON.

1. Mở thư mục dự án trong VS Code.
2. Chạy bằng Live Server.
3. Mở trang được Live Server cung cấp.
4. Kiểm tra các luồng: tải trang, import, refresh, delete, reset và export.

## Publish bằng GitHub Pages

1. Tạo repository GitHub mới.
2. Push toàn bộ file dự án lên nhánh chính.
3. Mở **Settings → Pages**.
4. Chọn triển khai từ nhánh chính và thư mục gốc `/root`.
5. Mở URL GitHub Pages và chạy lại checklist kiểm thử.

## Quy tắc dữ liệu

- Không đổi schema hoặc khóa `tgtc_database_v1` nếu chưa có kế hoạch migration.
- Import merge theo `id`; ID trùng trong cùng một batch sẽ bị từ chối.
- Không tạo ID mới cho một cá thể đã tồn tại.
- Backup trước import lớn, reset hoặc xóa dữ liệu.
- Chỉ cập nhật hai file trong `data/` sau khi dữ liệu đã được kiểm tra và xác nhận là canon.
