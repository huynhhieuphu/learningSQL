Vòng lặp trong T-SQL

===============================
=== WHILE expression        ===
=== 	BEGIN               ===
=== 		do something... ===		
=== 	END                 ===
===============================

Ví dụ:
	
	DECLARE @i INT = 0;
	DECLARE @n INT = 10000;

	WHILE (@i < @n)
		BEGIN
			PRINT @i
			@i += 1
		END


Ví dụ 2: INSERT 10000 record
	
	DECLARE @i INT = 0;
	DECLARE @n INT = 10000;

	WHILE (@i < @n)
		BEGIN
			INSERT INTO products(`name`, price) VALUE 'SP'+@i, 100000;
			@i += 1
		END	