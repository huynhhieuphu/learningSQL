FUNCTION trong SQL

Sự khác nhau cơ bản của PROCEDURE và FUNCTION

- FUNCTION có cặp dấu ngoặc tròn (dù có tham số hay không có tham số)
- khi tạo FUNCTION phải có khai báo RETURNS kiểu dữ liệu trả về 
- Thực thi FUNCTION trong câu truy vấn (Không dùng được EXEC như PROCDURE)

***Tạo FUNCTION***

===============================================================================
=== CREATE FUNCTION function_name(@param1 data_type, @param2 data_type,...) ===
=== RETUNS data_type                                                        ===
=== AS                                                                      ===
=== 	BEGIN                                                               ===
=== 		do something                                                    ===
=== 		...                                                             ===
===                                                                         ===
=== 		RETURN query_select|variable_name;                              ===
=== 	END                                                                 ===
===============================================================================
	
	Lưu ý:
	- Khai báo RETURNS phải có 's'
	- Khai báo kiểu dữ liệu trả về bao gồm TABLE, VARCHAR, NVARCHAR, INT, FLOAT, DATE...
	- Gần cuối FUNCTION phải có RETURN kèm giá trị trả về

	Ví dụ:

***Sửa FUNCTION***	

THAY CREATE thành ALTER

===============================================================================
=== ALTER FUNCTION function_name(@param1 data_type, @paramr2 data_type,...) ===
=== RETUNS data_type                                                        ===
=== AS                                                                      ===
=== 	BEGIN                                                               ===
=== 		do something                                                    ===
=== 		...                                                             ===
===                                                                         ===
=== 		RETURN query_select|variable_name;                              ===
=== 	END                                                                 ===
===============================================================================

***Sử dụng FUNCTION***

- Dùng FUNCTION tự định nghĩa -> y chang sử dụng các HÀM có sẵn trong SQL.

***Xoá FUNCTION***

====================================
=== DROP FUNCTION function_name; ===
====================================


Ví dụ:

	CREATE FUNCTION GETAGE(@dt DATE)
	RETURNS INT
	BEGIN
		DECLARE @age INT

		SELECT @age = YEAR(dt) -  YEAR(GETDATE())

		RETURN @age
	END


	SELECT id, name, dbo.GETAGE(birthday) FROM employees;


	CREATE FUNCTION kiemTraChanLe(@num INT)
	RETURN NVARCHAR(10)
	BEGIN
		IF(@num % 2 == 0)
			RETURN N'Số Chẵn'
		ELSE
			RETURN N'Số lẻ'

		RETURN N'Không Xác định được'
	END

	SELECT dbo.kiemTraChanLe(dbo.GETAGE(birthday)) FROM employees;
