Truy vấn với điều kiện

Toán tử:
- AND, OR, IN, NOT IN, BETWEEN, NOT BETWEEN, IS NULL, IS NOT NULL
- =, >, <, >=, <=, <> (Not equal to)

=================================================
=== SELECT * FROM table_name WHERE condition; ===
=================================================

	Ví dụ: lấy ra nhân viên lơn hơn 40 tuổi

	====================================================
	=== SELECT * FROM employees                      ===
	=== WHERE YEAR(GETDATE()) - YEAR(birthday) > 40; ===
	====================================================

		- YEAR() 	-> hàm lấy ra năm
		- GETDATE()	-> hàm trả ngày tháng năm hiện tại (mssql) === CURDATE() --> (mysql)

	Ví dụ: lấy ra tên, ngày sinh, tuổi nhân viên nhỏ hơn 40 tuổi

	=======================================================================
	=== SELECT name, birtday, YEAR(GETDATE()) - YEAR(birthday) AS 'age' ===
	=== FROM employees                                                  ===
	=== WHERE YEAR(GETDATE()) - YEAR(birthday) < 40;                    ===
	=======================================================================

Truy vấn với nhiều điều kiện

//Thoả mãn 2 điều kiện mới được
=================================================================
=== SELECT * FROM table_name WHERE condition1 AND condition2; ===
=================================================================

	Ví dụ: lấy ra màu sắc liên quan đến sản phẩm đó

	==================================================================
	=== SELECT p.name AS 'Product', c.name AS 'Color', p.'price'   ===
	=== FORM products AS p, product_color AS pc, colors AS c.      ===
	=== WHERE p.id = pc.product_id                                 ===
	=== AND c.id = pc.color_id                                     ===
	==================================================================

	Ví dụ: lấy số lượng sản phẩm A001 đã bán

	==================================================
	=== SELECT COUNT(*) AS 'Sản phẩm A Đã Bán'     ===
	=== FROM products AS p, order_detail AS od     ===
	=== WHERE p.id = od.product_id                 ===
	=== AND p.name = 'A001'                        ===
	==================================================

		- Hàm COUNT() trả về số dòng
			+ COUNT(*)        -> đếm tất cả các dòng
			+ COUNT(column)   -> đếm số dòng của cột

//Thoả mãn 1 trong 2 điều kiện đều được
==============================================================
=== SELECT * FROM tbl_name WHERE condition1 OR condition2; ===
==============================================================

// Cú pháp ngắn gọn hơn lệnh OR => IN
// IN, NOT IN
========================================================================
=== SELECT * FROM tbl_name WHERE col_name IN (val_1, val_2,..val_n); ===
========================================================================
https://www.w3schools.com/sql/sql_in.asp

// BETWEEN, NOT BETWEEN
======================================================================
=== SELECT * FROM tbl_name WHERE col_name BETWEEN val_1 AND val_2; ===
======================================================================
https://www.w3schools.com/sql/sql_between.asp

// IS NULL, NOT IS NULL
==========================================================
=== SELECT * FROM tbl_name WHERE col_name IS NULL;     ===
=== SELECT * FROM tbl_name WHERE col_name IS NOT NULL; ===
==========================================================
https://www.w3schools.com/sql/sql_null_values.asp

BÀI TẬP:
	1. lấy ra danh mục con thuộc danh mục cha trong bảng categories

		===============================================
		=== SELECT c1.name, c2.name                 ===
		=== FORM categories AS c1, categories AS c2 ===
		=== WHERE c1.id = c2.parent_id              ===
		===============================================


??? Bài toán: lấy ra sản phẩm đã bán ít 10 lần
-> để giải quyết bài toàn dùng Truy vần lồng