***FULL OUTER JOIN*** 
- Lấy ra tất cả dữ liệu khoả mãn điều kiện và không khoả mãn điều kiện

===========================================
=== SELECT column1, column2,...         ===
=== FROM table1 INNER OUTER JOIN table2 ===
=== ON table1.id = table2.id            ===     
===========================================

- lưu ý: bên bảng nào không khoả mãn điều kiện sẽ để NULL. 

	Ví dụ: 

	=======================================================
	=== SELECT p.name, b.name, p.price                  ===
	=== FROM products AS p INNER OUTER JOIN brands AS b ===
	=== ON p.id = p.brand_id                            ===
	=======================================================


***CROSS JOIN*** 
- Tổ hợp, mỗi dòng record của bảng A với tất cả record của bảng B (tương tự INNER JOIN)
	
	Tổ hợp của 2 bảng, dữ liệu bảng
	bảng A: 1,2,3
	bảng B: x,y

	Kết quả:
			1-x
			2-x
			3-x
			1-y
			2-y
			3-y

=====================================
=== SELECT column1, column2,...   ===
=== FROM table1 CROSS JOIN table2 ===
=== ON table1.id = table2.id      ===     
=====================================