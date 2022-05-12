Truy vấn cơ bản

***Lấy tất cả dữ liệu trong bảng***

=================================
=== SELECT * FROM table_name; ===
=================================

***Lấy các cột được chỉ định trong bảng***

====================================================
=== SELECT column1, column2,... FROM table_name; ===
====================================================

***SELECT DISTINCE : Lấy ra các giá trị riêng biệt(khác nhau) và sắp xếp lại thứ tự ASC trong cột***

====================================================
=== SELECT DISTINCE column FROM table_name; ===
====================================================

***Đặt lại tên định danh cho cột trong bảng***

========================================================================
=== SELECT column1 AS 'alias1', column2 AS 'alias2' FROM table_name; ===
========================================================================

***Truy xuất dữ liệu kết hợp từ nhiều bảng***

	- Giả sử: Tổ hợp của 2 bảng, dữ liệu bảng
	bảng 1: 1,2,3
	bảng 2: A,B

	Kết quả:
			1-A
			2-A
			3-A
			1-B
			2-B
			3-B

	=====================================
	=== SELECT * FROM table1, table2; ===
	=====================================

	! Vấn đề: kết hợp nhiều bảng phát sinh có thể trùng tên cột với nhau, nên đặt định danh cho bảng và dùng định danh mới bảng để chỉ định đúng tên cột cần dùng.

***Lấy ra các cột chỉ định từ kết hợp 2 bảng và đặt định danh cho bảng (tương tự INNERJOIN)***

===============================================
=== SELECT column1, column2,...             ===
=== FROM table1 AS alias1, table2 AS alias2 ===
=== WHERE alias1.id = alias2.id             ===     
===============================================

	! Vấn đề: lấy dư dữ liệu và không đúng yêu cầu. Phải có điều kiện WHERE để giải quyết bài toán

	Ví dụ: lấy ra tên sp, tên nhãn hàng, giá sp tương ứng

	===========================================
	=== SELECT p.name, b.name, p.price.     ===
	=== FROM products AS p, brands AS b     ===
	=== WHERE p.id = p.brand_id             ===
	===========================================