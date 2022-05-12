Truy vấn lồng

***Truy vấn lồng trong WHERE***

===========================================
=== SELECT column(s) FROM table_name    ===
=== WHERE condition(s) (                ===
===	  SELECT column(s) FROM table_name  ===
===   ...                               ===
=== );                                  ===
===========================================

	Ví dụ: Kiểm tra mã nhân viên đó có phải là quản lý nhóm không?

	=============================================
	=== SELECT * FORM employees               ===
	=== WHERE id = '1001' AND id IN (         ===
	===   SELECT manager_id FROM employees; ===
	=== )                                     ===
	=============================================

		- IN     : lấy ra các record có giá trị tồn tại bên trong
		- NOT IN : lấy ra các record không có tồn tại giá trị

***Truy vấn lồng trong FROM***

============================================================================================
=== SELECT column(s) FROM table_bame, (SELECT column(s) FORM table_name) AS table_alias; ===
============================================================================================

	Ví dụ: Kết hợp 2 bảng mà không cần điều kiện (khi truy vấn lồng trong FROM phải ĐỊNH DANH cho truy vấn lồng)

	====================================================================
	=== SELECT * FROM products, (SELECT * FROM order_details) AS od; ===
	====================================================================


Giải bài toán: 

	1. lấy ra sản phẩm đã bán ít 10 sản phẩm

	============================================
	=== SELECT * FROM products AS p          ===
	=== WHERE 10 < (                         ===
	===   SELECT COUNT(*) FROM order_details ===
	===   WHERE product_id = p.id;           ===
	=== )                                    ===
	============================================

	2. Nhãn hàng nào bán nhiều sp nhất

	=======================================================================
	=== SELECT * FROM brands AS b WHERE b.id IN (                       ===
	=== 	SELECT COUNT(*) FROM products AS p JOIN order_details AS od ===
	=== 	ON p.id = od.product_id                                     ===
	=== 	WHERE p.brand_id = b.id                                     ===
	=== );                                                              ===
	=======================================================================