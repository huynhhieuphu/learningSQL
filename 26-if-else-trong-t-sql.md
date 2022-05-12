IF ELSE trong T-SQL

===============================
=== IF expression           ===
=== 	BEGIN               ===
=== 		do something... ===
=== 	END                 ===
=== ELSE                    ===
=== 	BEGIN               ===
=== 		do something...	===
=== 	END                 ===
===============================

Ví dụ 1: Kiểm tra giá sp có lớn hơn sp trung bình không ?

	DECLARE @AvgPrice INT;
	DECLARE @CountProduct INT;

	SELECT @CountProduct = COUNT(*) FROM Products;
	SELECT @AvgPrice = SUM(price) / @CountProduct FROM Products;

	DECLARE @productID INT = 1001;
	DECLARE @priceProduct INT = 0;

	SELECT @priceProduct = price FROM products
	WHERE id = @productID;

	IF (@priceProduct > @AvgPrice)
		BEGIN
			PRINT @priceProduct
			PRINT N'Lớn hơn'
		END
	ELSE
		BEGIN
			PRINT @vgPrice
			PRINT N'Nhỏ hơn'
		END

Ví dụ 2: Cập nhật lại giá sp nếu sp nhỏ hơn giá trung bình, ngược lại không làm gì hết

	DECLARE @AvgPrice INT;
	DECLARE @CountProduct INT;

	SELECT @CountProduct = COUNT(*) FROM Products;
	SELECT @AvgPrice = SUM(price) / @CountProduct FROM Products;

	DECLARE @productID INT = 1001;
	DECLARE @priceProduct INT = 0;

	SELECT @priceProduct = price FROM products
	WHERE id = @productID;

	IF (@priceProduct < @AvgPrice)
		BEGIN
			UPDATE products SET price = 10000000
		END

		

