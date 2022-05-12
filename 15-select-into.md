SELECT INTO
- dùng để backup bảng, tạo ra nhiều bản sao đều được

==============================================
=== SELECT column_name(s) INTO clone_table ===
=== FROM table_name                        ===
==============================================
	
	Ví dụ: Sao chép 1 bảng mới với bảng có sẵn

	====================================
	=== SELECT * INTO clone_product1 ===
	=== FROM products;               ===
	====================================

	Ví dụ: Sao chép 1 bảng mới với các cột chỉ định

	=======================================================
	=== SELECT column1, column2,... INTO clone_product2 ===
	=== FROM products;                                  ===
	=======================================================

	Ví dụ: Sao chép 1 bảng mới với điều kiện

	=======================================================
	=== SELECT column1, column2,... INTO clone_product3 ===
	=== FROM products WHERE price < 10000000;           ===
	=======================================================

	Ví dụ: Sao chép 1 bảng mới với 2 hoặc nhiều bảng

	=======================================================
	=== SELECT column1, column2,... INTO clone_product4 ===
	=== FROM products AS p, brands AS b                 ===
	=== WHERE p.brand_id = b.id;                        ===
	=======================================================

	Có thể tạo ra 1 bảng mới không có dữ liệu từ điều kiện sai.