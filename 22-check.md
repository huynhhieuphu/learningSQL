CHECK

Ràng buộc CHECK - kiểm tra thoả mãn điều kiện mới cho phép INSERT hoặc UPDATE

***Tạo CHECK***

========================================
=== CREATE TABLE table_name (        ===
=== 	column_name CHECK condition; ===
=== )                                ===
========================================

	Ví dụ:

	=============================================================== 
	=== CREATE TABLE products (                                 ===
	=== 	id INT IDENTITY(1,1) PRIMARY KEY,                   ===
	=== 	name VARCHAR(100),                                  ===
	=== 	price INT CHECK (price >= 3000 AND price <= 100000) ===
	=== )                                                       ===
	===============================================================

***Tạo ràng buộc CHECK***

============================================================ 	
=== CREATE TABLE table_name (                            ===
=== 	...                                              ===
=== 	CONSTRAINT constraint_check_name CHECK condition ===
=== )                                                    ===
============================================================

	Ví dụ:

	==========================================================================
	=== CREATE TABLE products (                                            ===
	=== 	id INT IDENTITY(1,1) PRIMARY KEY,                              ===
	=== 	name VARCHAR(100),                                             ===
	=== 	price INT,                                                     ===
	=== 	CONSTRAINT chk_price CHECK (price >= 3000 AND price <= 100000) ===
	=== )                                                                  ===
	==========================================================================

===============================================================================
=== ALTER TABLE table ADD CONSTRAINT constraint_check_name CHECK condition; ===
===============================================================================

***Xoá ràng buộc CHECK***

================================================================
=== ALTER TABLE table DROP CONSTRAINT constraint_check_name; ===
================================================================