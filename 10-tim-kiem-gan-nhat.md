Tìm kiếm gần nhất

====================================================
=== SELECT * FROM table_name WHERE LIKE pattern; ===
====================================================

	Ví dụ: tìm sản phẩm có ký tự bắt đầu bằng chữ i

	==============================
	=== SELECT * FROM products ===
	=== WHERE LIKE 'i%'        ===
	==============================

	Ví dụ: tìm sản phẩm có ký tự kết thúc bằng chữ A

	==============================
	=== SELECT * FROM products ===
	=== WHERE LIKE '%A'        ===
	==============================

	Ví dụ: tìm sản phẩm tồn tại chữ m

	==============================
	=== SELECT * FROM products ===
	=== WHERE LIKE '%m%'       ===
	==============================

	Ví dụ: tìm sản phẩm tồn tại chữ có unicode (dành cho MSSQL)

	==============================
	=== SELECT * FROM products ===
	=== WHERE LIKE N'%ế%'      ===
	==============================

	MSSQL Để search được chữ có dấu cần N'search'.
	MYSQL không phân biệt unicode