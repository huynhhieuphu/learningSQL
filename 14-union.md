UNION -> dùng để trả kết quả hợp thành từ 2 hoặc nhiều SELECT lại.
https://www.w3schools.com/sql/sql_union.asp

- Mỗi lệnh SELECT trong UNIQUE đều có số cột bằng nhau
- Các cột cũng có kiểu dữ liệu giống
- Các cột trong mỗi câu lệnh SELECT phải sắp thứ tự

==========================================
=== SELECT column_name(s) FROM table1  ===
=== UNION                              ===
=== SELECT column_name(s) FROM table2; ===
==========================================

==========================================
=== SELECT column_name(s) FROM table1  ===
=== UNION ALL                          ===
=== SELECT column_name(s) FROM table2; ===
==========================================