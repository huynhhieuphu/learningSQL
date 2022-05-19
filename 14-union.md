# UNION

> dùng để trả về kết quả hợp thành từ 2 hoặc nhiều SELECT lại.<br>

[SQL UNION Operator](https://www.w3schools.com/sql/sql_union.asp)<br>

- Mỗi lệnh SELECT trong UNIQUE đều có số cột bằng nhau<br>
- Các cột cũng có kiểu dữ liệu giống<br>
- Các cột trong mỗi câu lệnh SELECT phải sắp thứ tự<br><br>

**SELECT** _column_name(s)_ **FROM** _table_1_<br>
**UNION**<br>
**SELECT** _column_name(s)_ **FROM** _table_2_;<br><br>

**SELECT** _column_name(s)_ **FROM** _table_1_<br>
**UNION ALL**<br>
**SELECT** _column_name(s)_ **FROM** _table_2_;
