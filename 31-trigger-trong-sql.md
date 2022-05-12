TRIGGER trong sql

Trường hợp: Khi có 1 hành động làm thay đổi thông tin bảng, bạn muốn kiểm tra xem sự thay đổi đó trong bảng thế nào đó ? Cho phép hoặc không cho phép nó thay đổi thông tin bảng đó.

Ví dụ: Thằng A insert 1 dòng vào bảng, nhưng Thằng B sẽ xem dòng insert đó có hợp lệ không mới được phép ghi nhận vào bảng. 

- Trigger sẽ được gọi mỗi khi có tháo tác thay đổi thông tin bảng
	- Các hành động bao gồm INSERT, UPDATE (thực ra là hành động DELETE rồi INSERT), DELETE.
	
	Sau mỗi hành động là trạng thái:
	- INSERTED : là Bảng chứa những record đã INSERT, UPDATE vào bảng
	- DELETED : là Bảng chứa những record đã DELETE ra khỏi bảng

=======================================================
=== CREATE|ALTER TRIGGER trigger_name ON table_name ===
=== FOR event_name1, event_name2                    ===
=== AS                                              ===
=== BEGIN                                           ===
===		do something...                             ===
=== END                                             ===
=======================================================
	
	- event_name : tên sự kiện INSERT, UPDATE, DELETE

Trường hợp 1: trigger sẽ xử lý trước, sau đó mới thay đổi thông tin bảng

	CREATE TRIGGER tgProducts ON products 
	FOR INSERT, UPDATE
	AS
	BEGIN
		PRINT 'do somthing 1'
	END

	INSERT INTO products(`name`, `price`) VALUES 'san pham 01', 20000;

Trường hợp 2: dùng ROLLBACK TRANSACTION để ngăn thay đổi thông tin bảng

	CREATE TRIGGER tgProducts ON products 
	FOR INSERT, UPDATE
	AS
	BEGIN
		ROLLBACK TRAN
		PRINT 'do somthing 2'
	END

	INSERT INTO products(`name`, `price`) VALUES 'san pham 02', 20000;


Lưu ý: Khi dùng TRIGGER cần xem xét mối quan các bảng, tham chiếu giữa các bảng

	CREATE TRIGGER tgProducts ON products
	FOR DELETE
	AS
	BEGIN
		DECLARE @count INT = 0

		SELECT @count = COUNT(*) FROM deleted
		WHERE deleted.price < 1000;

		IF(@count > 0)
		BEGIN
			ROLLBACK TRAN
			PRINT N'Không thể xoá sản phẩm'
		END
	END

	DELETE products WHERE id = 1001; -- price : 1000 -> Không thể xoá sản phẩm
	DELETE products WHERE id = 1002; -- price : 2000 -> XOÁ THÀNH CÔNG

