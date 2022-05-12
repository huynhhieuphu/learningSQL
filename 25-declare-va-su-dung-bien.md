DECLARE và sử dụng biến

Trường hợp

	1. Tìm mã sản phẩm có giá trị cao nhất

	========================================================
	===	SELECT id FROM products                          ===
	===	WHERE price = (SELECT MAX(price) FROM products); ===
	========================================================

	2. Tìm số lượng sản phẩm bán ra theo mã sản phẩm, lấy id trên câu 1

	==========================================================
	=== SELECT COUNT(*) FROM order_details                 ===
	===    WHERE product_id = (                            ===
	===	   SELECT id FROM products                         ===
	===	   WHERE price = (SELECT MAX(price) FROM products) ===
	=== )                                                  ===
	==========================================================

***Khai báo biến***

=========================================
=== DECALRE @variable_name data_type; ===
=========================================

	- DECALRE         : từ khoá khởi tạo biến
	- @variable_name  : tên biến (bắt phải có @)
	- data_type       : thiết lập kiểu dữ liệu cho biến      

	1. Khởi tạo biến

    =========================
	=== DECALRE @age INT; ===
	=========================

	2. Khởi tạo và gán giá trị biến

	===============================
	=== DECALRE @age INT = 30;  ===
	=== DECALRE @count INT = 1; ===
	===============================

	3. Gán giá trị biến

	================================
	=== SET @age = 30;           ===
	=== SET @count = @count + 1; ===
	=== SET @count += 1;         ===
	=== SET @count += @age;      ===
	================================

	4. Gán giá trị trong SELECT

	========================================================
	=== DECALRE @masp INT;                               ===
    ===                                                  ===
	===	SELECT @masp = id FROM products                  ===
	===	WHERE price = (SELECT MAX(price) FROM products); ===
	========================================================

	Giải quyết trường hợp trên dùng biến.

	========================================================
	=== DECALRE @masp INT;                               ===
    ===                                                  ===
	===	SELECT @masp = id FROM products                  ===
	===	WHERE price = (SELECT MAX(price) FROM products); ===
	===                                                  ===
	=== SELECT COUNT(*) FROM order_details               ===
	=== WHERE product_id = @masp                         ===
	========================================================

***Dùng PRINT để xuất ra giá trị của biến***

=============================
=== PRINT @variable_name; ===
=============================

	- PRINT dùng để xuất ra màn hình, hoặc thông báo gì đó... cho người dùng thấy