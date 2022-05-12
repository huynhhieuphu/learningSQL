GROUP BY - HAVING

================================
=== SELECT column_name(s)    ===
=== FROM table_name          ===
=== WHERE condition          ===
=== GROUP BY column_name(s)  ===
=== HAVING condition         ===
=== ORDER BY column_name(s); ===
================================

	Lưu ý:
	- Lệnh WHERE không được dùng cho Aggregate Funcion
	- HAVING -> giống như WHERE nhưng dành cho GROUP BY
	- HAVING là lệnh điều kiện của GROUP BY
	- HAVING chỉ dùng cho Agreeate function hoặc các cột của GROUP BY

	Ví dụ: Đếm tất cả sản phẩm đã bán dưới 10 cái

	===============================================================================================
	=== SELECT p.name, COUNT(od.id) AS selled FROM Products AS p INNER JOIN Order_Details AS od ===
	=== ON p.id = od.product_id                                                                 ===
	=== GROUP BY p.name                                                                         ===
	=== HAVING COUNT(od.id) < 10;                                                               ===
	===============================================================================================