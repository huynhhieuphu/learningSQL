STORE PROCEDURE trong sql

- là chương trình hay thủ tục -> thực thi lệnh
- Ta có thể dùng Transaction-SQL EXECUTE|EXEC để thực thi các STORED PROCEDURE
- STORE PROCEDURE khác với các FUNCTION (hàm) là FUNCTION có giá trị trả về
- Không chứa trong tên và chúng không được sử dụng trực tiếp trong biểu thức

- Linh hoạt: Có thể chỉnh sửa khối lệnh, tái sử dụng nhiều lần
- Nhanh: Tự phân tích cú pháp cho tối ưu. Và tạo bản sao để lần sau chạy không cần thực thi lại từ đầu
- Bảo mật: Giới hạn quyền cho user nào sử dụng user nào không
- Giảm bandwidth: Với các gói transaction lớn. Vài ngàn dòng lệnh lúc thì STORE sẽ đảm bảo

***Tạo PROCEDURE***

=========================================================
=== CREATE PROCEDURE|PROC procedure_name              ===
=== parameter1 data_type, parameter2 data_type,... AS ===
=== BEGIN                                             ===
=== 	do something...                               ===
=== END                                               ===
=========================================================

	- Nếu dùng để truy vấn thì không cần BEGIN và END

***Sửa PROCEDURE***	

THAY CREATE thành ALTER

=========================================================
=== ALTER PROCEDURE|PROC procedure_name               ===
=== parameter1 data_type, parameter2 data_type,... AS ===
=== BEGIN                                             ===
=== 	do something...                               ===
=== END                                               ===
=========================================================

***Xoá PROCEDURE***

======================================
=== DROP PROCEDURE procedure_name; ===
======================================

hoặc

=================================
=== DROP PROC procedure_name; ===
=================================

***Thực thi PROCEDURE***

====================================
=== EXECUTE|EXEC procedure_name; ===
====================================

***Tạo produce không có tham số***
	
	Ví dụ: Sao chép dữ liệu sản phẩm sang bản sao

		CREATE PROCEDURE pBKProducts AS
			SELECT INSERT INTO * FROM productsBK

		EXECUTE pBKProducts;


***Tạo produce có tham số***

	Ví dụ: Tạo nhân viên mới

		CREATE PROC pInsEmployee
			@firstName NVARCHAR(50),
			@birthday DATE,
			@gender BIT
		AS
			BEGIN
				INSERT INTO products(firstName, birthday, gender) 
				VALUES @firstName, @birthday, gender;
			END


	Thực thi PROCEDURE cách truyền tham số:

		-- Truyền tham số theo biến
		EXEC pInsEmployee @firstName = N'Nguyễn Văn A', @birthday = '1991-10-28', @gender = 1;

		hoặc

		-- Truyền tham số phải trình tự
		EXEC pInsEmployee N'Nguyễn Văn A', '1991-10-28',1;