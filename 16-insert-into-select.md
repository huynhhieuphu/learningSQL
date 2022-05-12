INSERT INTO SELECT
- dùng để copy dữ liệu bảng sang 1 bảng khác đã tồn tại.
- điều kiện copy -> tên và kiểu dữ liệu cột phải tương đồng

======================================
=== INSERT INTO SELECT clone_table ===
=== FROM table_name;               ===
======================================

	Ví dụ:

	Bước 1: clone ra 1 bảng mới

	=========================================
	=== SELECT column(s) INTO clone_table ===
	=== FROM table_name;                  ===
	=========================================

	Bước 2: copy dữ liệu sang 1 bảng mới clone

	======================================
	=== INSERT INTO SELECT clone_table ===
	=== FROM table_name;               ===
	======================================
