# INSERT INTO SELECT

> dùng để copy dữ liệu bảng sang 1 bảng khác đã tồn tại.
> điều kiện copy -> tên và kiểu dữ liệu cột phải tương đồng

**INSERT INTO SELECT** _clone_table_<br> **FROM** _table_name_;

_Ví dụ:_

1. Bước 1: clone ra 1 bảng mới

**SELECT** _column(s)_ **INTO** _clone_table_ **FROM** _table_name_;

2. Bước 2: copy dữ liệu sang 1 bảng mới clone

**INSERT INTO SELECT** _clone_table_ **FROM** _table_name_;
