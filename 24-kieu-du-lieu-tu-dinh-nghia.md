Kiểu dữ liệu tự định nghĩa

***Định nghĩa kiểu dữ liệu***

=================================================================
=== EXEC sp_addtype 'dataType_name', 'data_type', 'NOT NULL'; ===
=================================================================

	- sp_addtype 		-> keyword trong sql server
	- 'dataType_name' 	-> tự đặt tên kiểu dữ liệu
	- 'data_type'	 	-> kiểu dữ liệu dành riêng
	- 'NOT_NULL'		-> (tuỳ chọn) không cho phép rỗng

	Ví dụ:

	================================================================= 
	=== EXEC sp_addtype 'NFIRSTNAME', 'NVARCHAR(50)', 'NOT NULL'; ===
	=== EXEC sp_addtype 'NADDRESS', 'NVARCHAR(100)';              ===
	=================================================================

***Áp dụng trong lúc tạo bảng***

======================================
=== CREATE TABLE table_name (      ===
===		column_name dataType_name, ===
===		...                        ===
===)	                           ===
======================================

	Ví dụ:

	=================================
	=== CREATE TABLE customers (  ===
	===		firstName NFIRSTNAME, ===
	===		address NADDRESS,     ===
	===	);                        ===
	=================================

***Xoá định nghĩa kiểu dữ liệu***

- lưu ý: Để xoá được chắc chắn định nghĩa kiểu dữ liệu đó chưa được áp dụng lên bảng nào. Nếu không thì không thể xoá được.

=========================================
=== EXEC sp_droptype 'dataType_name'; ===
=========================================