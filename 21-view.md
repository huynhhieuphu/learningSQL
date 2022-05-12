VIEW -> bảng chỉ xem

- Cập nhật dữ liệu theo bảng mà VIEW truy vấn, tới khi lấy gọi VIEW

***Tạo VIEW***

==================================== 
=== CREATE VIEW view_name AS     ===
=== SELECT column1, column2, ... ===
=== FROM table_name              ===
=== WHERE condition;             ===
====================================

	Ví dụ:

	================================
	===	CREATE VIEW vProducts AS ===
	===	SELECT * FROM products;  ===
	================================

***Sử dụng VIEW***

=======================================
=== SELECT column(s) FROM view_name ===
=======================================
	
	Ví dụ:

	================================
	===	SELECT * FROM vProducts; ===
	================================

***Xoá VIEW***

===========================
=== DROP VIEW view_name ===
===========================

	Ví dụ:

	============================
	=== DROP VIEW vProducts; ===
	============================

***Sửa VIEW***

====================================
=== ALTER VIEW view_name AS.     ===
=== SELECT column1, column2,...  ===
=== FROM table_name              ===
=== WHERE condition;             ===
====================================

	Ví dụ:

	========================================= 
	===	ALTER VIEW vProducts AS           ===
	===	SELECT name, price FROM products; ===
	=========================================

***Tạo view có UNICODE***

==========================================
=== CREATE VIEW [view name unicode] AS ===
=== SELECT column1, column2,...        === 
=== FROM table_name                    ===
=== WHERE condition;                   ===
==========================================

=================================================
=== SELECT column(s) FROM [view name unicode] ===
=================================================

	Ví dụ:

	===========================================
	===	CREATE VIEW [Danh Sách Sản Phẩm] AS ===
	===	SELECT * FROM products;             ===
	===========================================

	===========================================
	===	SELECT * FROM [Danh Sách Sản Phẩm]; ===
	===========================================
