CURSOR trong T-SQL

Tình huống
	-- khi có nhu cầu duyệt từng record của bảng. Với mỗi record có kết quả xử lý riêng thì dùng CURSOR


Cấu trúc sử dụng chung

==============================================================================
=== DECLARE cursor_name CURSOR FOR sql_statement                           === (1)
===                                                                        === (2)
=== OPEN cursor_name                                                       ===
===		                                                                   ===
===		DECLARE variable1 data_type                                        === (3)
===		DECLARE variable2 data_type                                        === (3)
===		...                                                                ===
===                                                                        ===
=== 	FETCH NEXT FROM cursor_name INTO variable1, variable2,...          === (4)
===                                                                        ===
=== 	WHILE @@FETCH_STATUS =0                                            === (5)
=== 		BEGIN                                                          ===
=== 			                                                           ===
=== 			do something...                                            === (6)
===                                                                        ===
=== 			FETCH NEXT                                                 === (7)
=== 			FETCH NEXT FROM cursor_name INTO variable1, variable2,...  === (7)
=== 		END                                                            ===
===		                                                                   ===
=== CLOSE cursor_name                                                      === (6)
=== DEALLOCATE cursor_name                                                 === (7)
==============================================================================

	cursor_name 			-> tên con chỏ
	sql_statement 			-> câu truy vấn select
	variable1, variable2,...-> Danh sách các biến tương ứng kết quả truy vấn (các trường hiển thị)

	(1) Khởi tạo tên con chỏ dựa trên câu truy vấn (kết quả trả về câu truy vấn)
	(2) Bắt đầu dùng con chỏ
	(3) Khai báo biến
	(4) Đưa dữ liệu con trỏ vào bên trong danh sách các biến tương ứng kết quả truy vấn
	(5) Dùng vòng lặp xử lý từng dòng
	(6) Xử lý dòng đang đứng
	(7) LẶP LẠI dòng kế tiếp -> cho đến hết khi không còn dòng nào...
	(8) Đóng con chỏ
	(9)	Huỷ vùng nhớ cấp phép con chỏ

Ví dụ:

	Từ tuổi nhân viên mà thiết lập lương cơ bản
		- Nếu lớn hơn 40 thì cho lương là 2500
		- Nếu nhỏ hơn 40 và lớn hơn 30 thì cho lương là 2000
		- Ngược lại thì lương là 1500


	DECLARE cEmployees CURSOR FOR SELECT id, YEAR(GETDATE()) - YEAR(BIRTHDAY) FROM employees

	OPEN cEmployees
		DECLARE @empID INT
		DECLARE @ageEmp INT

		FETCH NEXT FROM cEmployees INTO @empID, @ageEmp

		WHILE @@FETCH_STATUS = 0
			BEGIN
				IF(@ageEmp > 40)
					BEGIN
						UPDATE employees SET salary = 2500 WHERE id = @empID
					END
				ELSE IF(@ageEmp > 30)
					BEGIN
						UPDATE employees SET salary = 2000 WHERE id = @empID
					END
				ELSE
					BEGIN
						UPDATE employees SET salary = 1500 WHERE id = @empID
					END

				FETCH NEXT FROM cEmployees INTO @empID, @ageEmp
			END

	CLOSE cEmployees
	DEALLOCATE cEmployees


	- Nếu muốn đi tới từng dòng -> từng dòng trong bảng thì dùng CURSOR (con trỏ)
	- Hạn chế sử dụng CURSOR vì tốc độ truy vấn rất chậm
	- CURSOR hình dung tới vòng lặp for của ngôn ngữ lập trình javascript (each), php (foreach),...