# Các ràng buộc

- **IDENTITY** : (cú pháp ms sql) tự động tăng, Không truyền giá trị sử động tăng (vẫn tăng giá trị đã xoá bảng ghi cũ). Bắt buộc dùng cho khoá chính và 1 bảng chỉ dùng 1 lần. (cú pháp ms sql)<br><br>

- **AUTO_INCREMENT** : (cú pháp mysql) tự động tăng, Không truyền giá trị sử động tăng (vẫn tăng giá trị đã xoá bảng ghi cũ). Bắt buộc dùng cho khoá chính và 1 bảng chỉ dùng 1 lần.<br><br>

- **UNIQUE** : Dùng cho 1 (hoặc nhiều) cột KHÔNG cho phép được trùng hoặc lặp lại, được phép null.<br><br>

- **NOT NULL** : KHÔNG được phép null.<br><br>

- **UNSIGNED** : số KHÔNG được phép âm<br><br>

- **DEFAULT** : thiết lập giá trị mặc định, khi insert mà không có giá trị sẽ lấy giá trị mặc định.<br><br>

- **CHECK** : Kiểm tra điều kiện -> TRUE -> thì được phép thêm hoặc cập nhật.<br><br>
